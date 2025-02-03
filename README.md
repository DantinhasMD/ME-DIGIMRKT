# ME-DIGIMRKT - Auxiliador para o Microempreendedor 🔥
Repositório para desenvolvimento do projeto baseado em Dados + Power BI + IA

## Apresentação do Problema 👀 
O nosso projeto enfrenta quatro problemas principais que comprometem a eficiência operacional e o crescimento da loja digital. Abaixo, apresento uma descrição detalhada de cada um desses desafios: {Explicação Completa=[https://github.com/DantinhasMD/ME-DIGIMRKT/blob/main/2_problems.md]

1. Problema no Preenchimento de Dados    
2. Problema para Responder Clientes    
3. Sem Controle de Estoque     
4. Problema de Visualização

Esse fluxo atual, totalmente manual, está repleto de erros e ineficiências. A dependência de planilhas para o registro de dados, a falta de automação no processo de atendimento ao cliente e a gestão desorganizada das compras e vendas são aspectos que dificultam a escalabilidade do negócio.
[Explicação do Fluxo](https://github.com/DantinhasMD/ME-DIGIMRKT/blob/main/1_flow.md)


## Desenvolvimento
  1️⃣- Automação do preenchimento de dados (Formulário + Google Sheets + Apps Script).        
  2️⃣- Criação do chatbot para otimizar atendimento e notificações.                  
  3️⃣- Controle de estoque automático vinculado ao formulário de vendas.                    
  4️⃣- Visualização dos dados com gráficos interativos.              

### 1) Criar a Estrutura de Coleta de Dados (Preenchimento Automático)
#### ✅ Objetivo: Automatizar o registro de dados das vendas e compras para evitar preenchimentos manuais.         
🔹Criar um Google Formulário para coletar dados de compra e venda.      
🔹Configurar o Google Sheets para armazenar essas informações automaticamente.     
🔹Escrever um Google Apps Script para organizar esses dados e evitar erros.    

💡 Por que começar por aqui? Sem os dados organizados, o chatbot, estoque e relatórios não terão informações estruturadas para funcionar corretamente.

### 2) Desenvolver o Chatbot para Atendimento Automatizado
#### ✅ Objetivo: Criar um atendimento eficiente e automático para separar dúvidas e solicitações urgentes.      
🔹Escolher uma plataforma gratuita (Tidio, ManyChat, Chatbot.com).      
🔹Configurar as mensagens automáticas e as opções de resposta.    
🔹Integrar notificações para avisar o vendedor sobre compras realizadas e devoluções.      

💡 Por que fazer isso em segundo lugar? Porque as informações do formulário já estarão estruturadas, permitindo ao chatbot acessar dados organizados e facilitar o atendimento.

### 3) Criar o Sistema de Controle de Estoque Automatizado
#### ✅ Objetivo: Monitorar os produtos vendidos e ajustar o estoque automaticamente.     
🔹Criar uma aba no Google Sheets para armazenar o estoque.       
🔹Usar Google Apps Script para atualizar a planilha sempre que uma venda for registrada.     
🔹Implementar alertas para avisar quando um produto estiver com estoque baixo.      

💡 Por que esse é o terceiro passo? Com o chatbot e os formulários funcionando, já teremos um fluxo de entrada de dados que permitirá atualizar o estoque em tempo real.

### 4) Criar Relatórios e Visualização de Dados
#### ✅ Objetivo: Melhorar a análise de vendas e finanças para tomar decisões estratégicas.       
🔹Escolher uma ferramenta gratuita como Google Data Studio ou Metabase.      
🔹Conectar o Google Sheets para gerar gráficos dinâmicos.     
🔹Criar dashboards com lucro, gastos, produtos mais vendidos e taxas.    

💡 Por que isso vem por último? Porque os relatórios dependem dos dados estruturados que foram organizados nos passos anteriores.
