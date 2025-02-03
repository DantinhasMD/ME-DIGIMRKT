# 1) Criar a Estrutura de Coleta de Dados (Preenchimento Automático) 
## ✅ Objetivo: Automatizar o registro de dados das vendas e compras para evitar preenchimentos manuais.     

### 📌 Pré-Desenvolvimento: Compreender os dados que precisamos e o relacionamento entre eles.

![Dados](https://github.com/user-attachments/assets/54547086-85b3-475d-b2e5-e610d4e90a44)

## 1) Criar um Google Formulário para coletar dados de compra e venda.     
#### 1️⃣ - Formulário de Registro de Compra (quando o vendedor compra um produto para revenda).      
🔸 ID do Produto (Número)                                    
🔸 Nome do Produto (Texto curto)                                   
🔸 Chave de Ativação (Texto curto)                                 
🔸 Valor de Compra (Número)                                   
🔸 Data da Compra (Data)                                                    
🔸 idFornecedor (Lista suspensa)                                                           
 
📌 Ative a opção de "Coletar respostas em uma planilha do Google" para salvar automaticamente os dados. Lembre de colocar os tipos de dados que esta tabela dinâmica irá receber.

#### 2️⃣ - Formulário de Registro de Venda (quando o vendedor vende um produto para um cliente).     
🔸 ID da Venda (Número)                                 
🔸 CPF do Cliente (Texto curto)                                 
🔸 Produto Vendido (Lista suspensa)                                 
🔸 Valor da Venda (Número)                                 
🔸 Tarifa da Plataforma (Número)                                 
🔸 Data da Venda (Data)
🔸 Lucro Obtido (Número)                                 
🔸 Nome do Vendedor (Texto curto)                                 

📌 Faça as outras planilhas necessárias.

#### 2️⃣ - Seção: Dados do Cliente (Formulário e Planilha)
🔸 CPF (Texto curto)                                 
🔸 Nome (Texto curto)                                 
🔸 Telefone (Número)                                 
🔸 E-mail (E-mail)                                 

#### 2️⃣ - Seção: Controle de Estoque (Planilha)
🔸 ID do Estoque (Número)                                 
🔸 Produto (Texto curto)                                 
🔸 Quantidade em Estoque (Número)                                 

#### 2️⃣ - Seção: Fornecedores (Formulário e Planilha)
🔸 ID do Fornecedor (Número)                                 
🔸 Nome do Fornecedor (Texto curto)                                 
🔸 País de Origem (Texto curto)                                 
🔸 E-mail do Fornecedor (E-mail)                                 
🔸 Site do Fornecedor (URL)                                 

### Configurar o Google Sheets para armazenar essas informações automaticamente.    
🔸 A criação de Formulários no Google intregra com a Planilha criada automáticamente. 

### Escrever um Google Apps Script para organizar esses dados e evitar erros.    



