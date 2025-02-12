# DIGIMRKT - Auxiliador para o Microempreendedor 🔥
Repositório para desenvolvimento do projeto baseado em Dados + Power BI + IA. Projeto desenvolvido para Eletiva da faculdade de Análise e Desenvolviemntos de Sistemas, utilizando também de habilidades desenvolvidas em outros cursos, como:
-   Coursera: Análise de Dados: 
-   Bootcamp Microsoft AI for Tech - Criando Prompts Inteligentes: [Arquivo](https://github.com/DantinhasMD/Bootcamp_Dio---Prompts.git)
-   Bootcamp DIO: Suzano - Análise de Dados com Power BI: [Arquivo](https://github.com/DantinhasMD/Bootcamp_Analise-de-DadosDIO.git})
-   Bootcamp DIO: Heineken - Inteligência Artificial Aplicada a Dados: [Arquivo](https://github.com/DantinhasMD/Bootcamp_Dio---Dados_IA.git)

## Apresentação do Problema 👀 
O nosso projeto enfrenta quatro problemas principais que comprometem a eficiência operacional e o crescimento da loja digital. Abaixo, apresento uma descrição detalhada de cada um desses desafios: [Explicação do Problema](https://github.com/DantinhasMD/ME-DIGIMRKT/blob/main/2_problems.md)

1. Problema no Preenchimento de Dados    
2. Problema para Responder Clientes    
3. Sem Controle de Estoque     
4. Problema de Visualização

Esse fluxo atual, totalmente manual, está repleto de erros e ineficiências. A dependência de planilhas para o registro de dados, a falta de automação no processo de atendimento ao cliente e a gestão desorganizada das compras e vendas são aspectos que dificultam a escalabilidade do negócio.
[Explicação do Fluxo](https://github.com/DantinhasMD/ME-DIGIMRKT/blob/main/1_flow.md)

## Proposta de solução 🚀
- Coleta de dados → Google Forms alimentando o Google Sheets automaticamente.
- Atendimento ao cliente → Chatbot para organizar solicitações e priorizar respostas.
- Controle de estoque → Atualização automática dos dados no Google Sheets e visualização no Google Data Studio.
- Análise de desempenho → Relatórios interativos no Google Data Studio ou Metabase.

[Explicação da Solução](https://github.com/DantinhasMD/ME-DIGIMRKT/blob/main/3_solution.md)

## Desenvolvimento
  1️⃣- Automação do preenchimento de dados (Formulário + Google Sheets + Apps Script).        
  2️⃣- Criação do chatbot para otimizar atendimento e notificações.                  
  3️⃣- Controle de estoque automático vinculado ao formulário de vendas.                    
  4️⃣- Visualização dos dados com gráficos interativos.              
.
.
### 1) Criar a Estrutura de Coleta de Dados (Preenchimento Automático)
#### ✅ Objetivo: Automatizar o registro de dados das vendas e compras para evitar preenchimentos manuais.         
🔹Criar um Google Formulário para coletar dados de compra e venda.      
🔹Configurar o Google Sheets para armazenar essas informações automaticamente.      

💡 Por que começar por aqui? Sem os dados organizados, o chatbot, estoque e relatórios não terão informações estruturadas para funcionar corretamente.
[Explore](https://github.com/DantinhasMD/ME-DIGIMRKT/blob/main/4_1_development.md)
.
.
### 2) Desenvolver o Chatbot para Atendimento Automatizado
#### ✅ Objetivo: Criar um atendimento eficiente e automático para separar dúvidas e solicitações urgentes.      
🔹Escolher uma plataforma gratuita (Tidio, ManyChat, Chatbot.com).      
🔹Configurar as mensagens automáticas e as opções de resposta.    
🔹Integrar notificações para avisar o vendedor sobre compras realizadas e devoluções.      

💡 Por que fazer isso em segundo lugar? Porque as informações do formulário já estarão estruturadas, permitindo ao chatbot acessar dados organizados e facilitar o atendimento.
[Explore](https://github.com/DantinhasMD/ME-DIGIMRKT/blob/main/4_1_development.md)
.
.
### 3) Criar o Sistema de Controle de Estoque Automatizado
#### ✅ Objetivo: Monitorar os produtos vendidos e ajustar o estoque automaticamente.     
🔹Criar uma aba no Google Sheets para armazenar o estoque.       
🔹Usar Google Apps Script para atualizar a planilha sempre que uma venda for registrada.     
🔹Implementar alertas para avisar quando um produto estiver com estoque baixo.      

💡 Por que esse é o terceiro passo? Com o chatbot e os formulários funcionando, já teremos um fluxo de entrada de dados que permitirá atualizar o estoque em tempo real.
[Explore](https://github.com/DantinhasMD/ME-DIGIMRKT/blob/main/4_1_development.md)
.
.
### 4) Criar Relatórios e Visualização de Dados
#### ✅ Objetivo: Melhorar a análise de vendas e finanças para tomar decisões estratégicas.       
🔹Escolher uma ferramenta gratuita como Google Data Studio ou Metabase.      
🔹Conectar o Google Sheets para gerar gráficos dinâmicos.     
🔹Criar dashboards com lucro, gastos, produtos mais vendidos e taxas.    

💡 Por que isso vem por último? Porque os relatórios dependem dos dados estruturados que foram organizados nos passos anteriores.
[Explore](https://github.com/DantinhasMD/ME-DIGIMRKT/blob/main/4_1_development.md)
