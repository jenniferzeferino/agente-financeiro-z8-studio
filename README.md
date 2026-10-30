# Agente de Gestão Financeira e Alertas Ativos (Z8 Studio de Dança)

## Visão Geral
Solução de Inteligência Artificial e automação *no-code* criada para otimizar o controle financeiro, análise de receita e gestão de inadimplência de um estúdio de dança. O sistema automatiza a leitura de registros operacionais, gera diagnósticos da saúde do caixa e cria mensagens personalizadas de cobrança para envio aos clientes.

## Problema de Negócio
Em pequenos negócios e estúdios de dança, o acompanhamento do fluxo de caixa e a cobrança de mensalidades em atraso costumam ser feitos de forma manual. Isso gera dois gargalos operacionais:
1. **Perda de tempo:** Horas gastas conferindo quem pagou e digitando mensagens individuais no WhatsApp.
2. **Fricção no relacionamento:** Dificuldade em manter um tom profissional, amigável e empático ao cobrar mensalidades pendentes.

## Arquitetura e Tecnologias
- **Base de Dados:** Google Sheets (Controle de alunas, modalidades, vencimentos e status).
- **Orquestrador de Fluxo:** Make.com (Ingestão de dados e roteamento automático).
- **Motor de Inteligência (LLM):** Google AI Studio — API do Gemini 1.5 Flash.
- **Prompt Engineering:** System Prompts focados em análise financeira e tom de voz humanizado/acolhedor.
- **Interface de Saída:** Telegram / E-mail (Relatório executivo + mensagens prontas para copiar e enviar no WhatsApp).

## Fluxo de Funcionamento
1. **Gatilho de Dados:** O Make.com lê periodicamente as linhas da planilha de mensalidades do Google Sheets.
2. **Triagem de Status:** O fluxo identifica transações com status `Atrasado` ou `Pendente`.
3. **Processamento com IA (Gemini):**
   - **Módulo Analítico:** Calcula a taxa de inadimplência do mês e o impacto na receita projetada.
   - **Módulo de Comunicação:** Gera mensagens personalizadas para cada aluna, considerando o nome, a modalidade praticada (ex: Ballet, Jazz, FitDance) e os dias de atraso, mantendo a gentileza adequada ao negócio.
4. **Entrega de Relatório:** O gestor recebe no Telegram/E-mail um resumo executivo com os indicadores do mês e os textos prontos para cópia e envio rápido.

## Impacto de Negócio Medível
- **Redução de 90% no tempo manual** gasto com conferência de caixa e digitação de lembretes.
- **Cobrança humanizada:** Aumento na taxa de recuperação de mensalidades sem desgastar a relação com os alunos.
- **Custo zero de infraestrutura:** Operação montada 100% com planos gratuitos e ferramentas em nuvem.
