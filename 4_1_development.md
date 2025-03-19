# Criar a Estrutura de Coleta de Dados (Preenchimento Automático) 
## ✅ Objetivo: Automatizar o registro de dados das vendas e compras para evitar preenchimentos manuais.     

### 📌 Pré-Desenvolvimento: Compreender os dados que precisamos e o relacionamento entre eles.

![Dados](https://github.com/user-attachments/assets/54547086-85b3-475d-b2e5-e610d4e90a44)

##### Precisamos que essa seja a etapa inicial, pois sem os dados organizados, o chatbot, estoque e relatórios não terão informações estruturadas para funcionar corretamente!

## 1) Formulários Criados
Para estruturar a coleta de dados, foram criados três formulários que enviam automaticamente as respostas para a planilha do Google Sheets. Essa automação evita erros manuais e garante maior eficiência no processamento das informações.

### 1. Formulário de Compras
Este formulário é responsável por coletar informações sobre os produtos adquiridos e enviá-las diretamente para a planilha. Os campos preenchidos no formulário são:

- Produto: Nome do produto comprado.
- Chave do Produto: Chave de ativação ou código do item.
- Valor da Compra: Preço pago pelo produto.
- Data da Compra: Data em que a compra foi realizada.
- Fornecedor: Empresa ou pessoa responsável pela venda do produto.

##### Um detalhe importante é que a lista de produtos disponíveis para seleção é gerada automaticamente a partir da planilha "Compras". Existe um código que captura os nomes dos produtos registrados, de forma que, quando um novo produto é adicionado à planilha, ele passa a aparecer no formulário automaticamente, sem necessidade de edição manual.

📌 Adicionar imagem ilustrativa do formulário de compras.

### 2. Formulário de Vendas
O formulário de vendas é utilizado para registrar cada transação realizada. Os campos são:

- ID Cliente: Identificação do comprador (puxado automaticamente da planilha de clientes).
- Data da Venda: Data em que a venda foi concluída.
- Vendedor: Nome do vendedor responsável.
- ID Produto: Identificação do produto vendido (puxado apenas se o produto estiver em estoque).
- Valor da Venda: Preço do produto (preenchido automaticamente).
- Tarifa: Taxa cobrada na venda (preenchida automaticamente).

##### Neste formulário, foram implementados quatro códigos essenciais:

1️⃣ ID Cliente: Busca automaticamente os clientes registrados na planilha.
2️⃣ ID Produto: Lista apenas os produtos que ainda estão em estoque.
3️⃣ Valor da Venda: Define automaticamente o preço do produto com base nas informações cadastradas.
4️⃣ Tarifa: Obtém automaticamente a taxa correspondente ao produto vendido.

##### Entretanto, encontramos algumas limitações do Google Forms:
🔸 O Google Forms não permite preencher automaticamente campos dentro do formulário. Isso significa que, embora possamos exibir o valor da venda e a tarifa na planilha, não podemos fazer com que esses valores sejam preenchidos automaticamente no formulário quando um produto é selecionado.

🔸O Google Forms não tem uma função de busca para a seleção de produtos, o que poderia facilitar a seleção de itens para venda.

📌 Adicionar imagem ilustrativa do formulário de vendas.

### 3. Formulário de Clientes
Para garantir que os clientes sejam registrados corretamente, criamos um formulário dedicado exclusivamente a eles. Os campos coletados são:

- CPF: Cadastro de Pessoa Física do cliente.
- Nome Completo: Nome do comprador.
- Telefone: Contato do cliente.
- E-mail: Endereço eletrônico do cliente.

##### Um dos desafios enfrentados nesse formulário foi a necessidade de capturar tanto CPF quanto CNPJ. Como o Google Forms não permite validações avançadas de números, foi necessária uma adaptação para garantir que tanto pessoas físicas quanto jurídicas pudessem ser registradas corretamente.

📌 Adicionar imagem ilustrativa do formulário de clientes.














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
🔸 ID da compra é gerado utilizando a função: 
##### =IF(Compras!C2:C<>"", ROW()-1, "")

### 2️⃣ - Funções da Planilha de Vendas preenchidos automáticamente
🔸 O nome do Produto é obtido a partir do ID especificado, utilizando a função: 
##### =INDEX(Compras!C:C, MATCH(Vendas!C3, Compras!B:B, 0))                 

🔸 O valor da Compra é obtido a partir do ID especificado, utiliando a função: 
#### =IFERROR(INDEX(Compras!E2:E, MATCH(Vendas!C3, Compras!B2:B, 0)), "")                      

🔸 A Tarifa de hospedagem é                                                               
🔸 O Lucro é calculado a partir da função: 
#### =D3-H3-I3

### 3️⃣ - Funções da Planilha de Estoque preenchidos automáticamente
🔸 A quatidade de produtos é obtido a partir do nome especificado na coluna anterior, usando a função: 
#### =COUNTIF(Compras!C:C, Estoque!A2) - COUNTIF(Vendas!G:G, Estoque!A2)

