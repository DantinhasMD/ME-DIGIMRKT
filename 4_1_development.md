# Criar a Estrutura de Coleta de Dados (Preenchimento Automático) 
## ✅ Objetivo: Automatizar o registro de dados das vendas e compras para evitar preenchimentos manuais.     

### 📌 Pré-Desenvolvimento: Compreender os dados que precisamos e o relacionamento entre eles.

![Dados](https://github.com/user-attachments/assets/54547086-85b3-475d-b2e5-e610d4e90a44)

## 1) Criar um Google Formulário para coletar dados de compra e venda.     
#### 1️⃣ - Formulário de Registro de Compra (quando o vendedor compra um produto para revenda).      
🔸 ID da Compra (Número)                                    
🔸 Nome do Produto (Texto curto)                                   
🔸 Chave de Ativação (Texto curto)                                 
🔸 Valor de Compra (Número)                                   
🔸 Data da Compra (Data)                                                    
🔸 idFornecedor (Texto curto)                                                             
 
📌 Ative a opção de "Coletar respostas em uma planilha do Google" para salvar automaticamente os dados. Lembre de colocar os tipos de dados que esta tabela dinâmica irá receber.

#### 2️⃣ - Formulário de Registro de Venda (quando o vendedor vende um produto para um cliente).                                    
🔸 CPF do Cliente (Texto curto)                                 
🔸 ID da Compra (Número)                                
🔸 Valor da Venda (Número)   
🔸 Data da Venda (Data)       
🔸 Nome do Vendedor (Texto curto)  
🔸 Nome do Produto (Texto curto)                                   
🔸 Valor de Compra (Número)                                   
🔸 Tarifa da Plataforma (Número)                                 
🔸 Lucro Obtido (Número)                                                                                                   

📌 Faça as outras planilhas necessárias que não são ligadas a formulários.

#### 3️⃣ - Seção: Dados do Cliente (Formulário e Planilha)
🔸 CPF (Texto curto)                                 
🔸 Nome (Texto curto)                                 
🔸 Telefone (Número)                                 
🔸 E-mail (E-mail)                                 

#### 4️⃣ - Seção: Controle de Estoque (Planilha)                                
🔸 Produto (Texto curto)                                 
🔸 Quantidade em Estoque (Número)                                 
                           

## 2) Configurar o Google Sheets para armazenar essas informações automaticamente.    
🔸 A criação de Formulários no Google intregra com a Planilha criada automáticamente. 
🔸 Esses dados são recebidos e, através de funções diretas do Excel, são manipulados corretamente.

### 1️⃣ - Funções da Planilha de Compra preenchidos automáticamente
🔸 ID da compra é gerado utilizando a função: =IF(Compras!C2:C<>"", ROW()-1, "")

### 2️⃣ - Funções da Planilha de Vendas preenchidos automáticamente
🔸 O nome do Produto é obtido a partir do ID especificado, utilizando a função: =INDEX(Compras!C:C, MATCH(Vendas!C3, Compras!B:B, 0))
🔸 O valor da Compra é obtido a partir do ID especificado, utiliando a função: =IFERROR(INDEX(Compras!E2:E, MATCH(Vendas!C3, Compras!B2:B, 0)), "")
🔸 A Tarifa de hospedagem é
🔸 O Lucro é calculado a partir da função: =D3-H3-I3

### 3️⃣ - Funções da Planilha de Estoque preenchidos automáticamente
🔸 A quatidade de produtos é obtido a partir do nome especificado na coluna anterior, usando a função: =COUNTIF(Compras!C:C, Estoque!A2) - COUNTIF(Vendas!G:G, Estoque!A2)


## 3) Escrever um Google Apps Script para organizar esses dados e evitar erros.    


