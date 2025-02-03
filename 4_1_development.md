# 1) Criar a Estrutura de Coleta de Dados (Preenchimento Automático) 
## ✅ Objetivo: Automatizar o registro de dados das vendas e compras para evitar preenchimentos manuais.     

### Criar um Google Formulário para coletar dados de compra e venda.     
#### 1️⃣ - Formulário de Registro de Compra (quando o vendedor compra um produto para revenda).      
🔸 Produto (Nome ou Tipo) → Pergunta de seleção (baseada nos produtos disponíveis).   
🔸 Chave do Produto → Campo de texto curto.   
🔸 Valor da Compra → Campo numérico.   
🔸 Data da Compra → Campo de data.    
🔸 Fornecedor → Campo de texto curto.    
🔸 Loja onde foi comprado → Campo de texto curto.   

📌 Ative a opção de "Coletar respostas em uma planilha do Google" para salvar automaticamente os dados. Lembre de colocar os tipos de dados que esta tabela dinâmica irá receber.

#### 2️⃣ - Formulário de Registro de Venda (quando o vendedor vende um produto para um cliente).     
🔸 Produto Vendido → Campo de seleção baseado nos produtos disponíveis.
🔸 Chave do Produto → Campo de texto curto.
🔸 Valor da Venda → Campo numérico.
🔸 Data da Venda → Campo de data.
🔸 CPF do Cliente → Campo de texto (para associar o pedido ao cliente).
🔸 Nome do Cliente → Campo de texto curto.
🔸 Vendedor Responsável → Campo de texto curto ou seleção.

📌 Assim como no formulário de compra, configure as respostas para serem salvas automaticamente em uma planilha do Google Sheets.

### Configurar o Google Sheets para armazenar essas informações automaticamente.    
🔸 A criação de Formulários no Google intregra com a Planilha criada automáticamente. 

### Escrever um Google Apps Script para organizar esses dados e evitar erros.    



