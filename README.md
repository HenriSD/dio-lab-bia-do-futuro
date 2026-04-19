
🤖 FinAI: Agente Financeiro Inteligente com IA Generativa
Bem-vindo ao FinAI, um assistente proativo desenvolvido para o desafio da DIO. Este agente não apenas responde perguntas, mas analisa dados reais para ajudar o cliente (João Silva) a completar sua reserva de emergência e conquistar o sonho da casa própria.

🚀 O Projeto
O FinAI utiliza a técnica de RAG (Retrieval-Augmented Generation) para conectar o poder do Google Gemini 1.5 Flash a uma base de dados local segura (CSV e JSON).

🎯 Caso de Uso: Mentor de Metas e Investimentos
O foco principal é o João Silva, um analista de sistemas com perfil moderado. O agente monitora seus gastos mensais e sugere onde investir o excedente para bater a meta de R$ 50.000 para a entrada de um apartamento até 2027.

🏗️ Arquitetura do Sistema
A solução foi estruturada para garantir que a IA não invente dados (anti-alucinação):

Interface: Desenvolvida em Streamlit para uma experiência de chat fluida.

Cérebro (LLM): Gemini 1.5 Flash via API do Google AI Studio.

Base de Dados: Arquivos na pasta /data que simulam um ambiente bancário real.

[!IMPORTANT]
O diagrama detalhado da arquitetura pode ser encontrado em: docs/01-documentacao-agente.md

Organização do Repositório
data/: Contém os dados de transações, perfil e catálogo de produtos financeiros.

docs/: Documentação completa do projeto (Casos de uso, Prompts, Métricas e Pitch).

src/: 

assets/: Diagramas e imagens do sistema.

📊 Avaliação e Métricas
O FinAI foi testado com base em:

Assertividade: Capacidade de somar gastos corretamente via CSV.

Segurança: Bloqueio de sugestões de ativos de alto risco (Cripto/Ações) enquanto a reserva de emergência não é atingida.

Grounding: Respostas limitadas ao catálogo oficial de produtos.

✍️ Autor
Desenvolvido por Henri como parte do curso do Bradesco de IA Generativa na DIO.