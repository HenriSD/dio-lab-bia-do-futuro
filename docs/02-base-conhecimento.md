# Base de Conhecimento

## Dados Utilizados

O agente utiliza quatro fontes de dados principais  para contextualizar suas respostas e garantir que as sugestões sejam personalizadas para o perfil do João Silva.

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Utilizado para manter a continuidade do atendimento. |
| `perfil_investidor.json` | JSON | Define o apetite a risco e as metas |
| `produtos_financeiros.json` | JSON | O catálogo oficial de produtos. |
| `transacoes.csv` | CSV | Histórico de entradas e saídas para calcular o saldo|


---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Para este projeto, os dados originais foram mantidos, mas o sistema executa cálculos em tempo real antes de enviar para o LLM:

Cálculo de Fluxo de Caixa: O sistema soma todas as transações de entrada e subtrai as de saída do mês corrente para informar ao agente quanto o João realmente "sobrou" no mês.

Projeção de Metas: O sistema calcula a diferença entre o patrimonio_total (15k) e a meta do apartamento (50k) para que o agente saiba que faltam R$ 35.000.

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

O Agente não lê os arquivos brutos. Utilizamos uma estratégia de Context Injection (Injeção de Contexto):

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

Leitura: No início da aplicação, o Python lê os arquivos CSV e JSON usando as bibliotecas pandas e json.

Serialização: Os dados são transformados em uma string estruturada.

Prompt Enrichment: Essa string é inserida dentro do "System Prompt" como uma seção chamada ### DADOS DO CLIENTE ###.

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

Contexto enviado ao LLM:

Cliente: João Silva (32 anos)

Perfil: Moderado

Reserva de Emergência: R$ 10.000 (Meta: R$ 15.000)

Saldo em conta (Outubro): R$ 2.411,10 (Calculado via transações)

Últimas interações: Tirou dúvidas sobre CDB e Tesouro Selic.

Catálogo: Tesouro Selic, CDB Liquidez Diária, LCI/LCA, Fundo Multimercado e Fundo de Ações.
