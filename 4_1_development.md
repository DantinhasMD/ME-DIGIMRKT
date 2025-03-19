# Criar a Estrutura de Coleta de Dados (Preenchimento Automático) 
#### ✅ Objetivo: Automatizar o registro de dados das vendas e compras para evitar preenchimentos manuais.     

## 📌 Pré-Desenvolvimento: Compreender os dados que precisamos e o relacionamento entre eles.

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

#### Neste formulário, foram implementados quatro códigos essenciais:

1️⃣ ID Cliente: Busca automaticamente os clientes registrados na planilha.                                                                 
2️⃣ ID Produto: Lista apenas os produtos que ainda estão em estoque.                                                                                  
3️⃣ Valor da Venda: Define automaticamente o preço do produto com base nas informações cadastradas.                                                             
4️⃣ Tarifa: Obtém automaticamente a taxa correspondente ao produto vendido.                                                                           

#### Entretanto, encontramos algumas limitações do Google Forms:
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

# AQUI TEMOS O FORMATARPRODUTOS, SE BASEIAM NESSA TABELA PARA PREENCHER DE VERMELHO EEM COMPRAS - BOTA EM COMPRAS 

📌 Adicionar imagem ilustrativa do formulário de clientes.


## 2) Modelagem do Banco de Dados na Planilha do Google
A estrutura do nosso banco de dados foi construída dentro de uma planilha do Google, organizando as informações de compras, vendas, clientes e produtos de forma automatizada. Abaixo, detalhamos a modelagem das tabelas e os códigos aplicados para garantir o funcionamento correto do sistema.

### 1. Tabela de Compras
Essa tabela armazena todas as compras realizadas e contém as seguintes colunas:

- IdCompra → Identificador único da compra, gerado automaticamente com a fórmula:[ =VALUE(IF(Compras!C2:C<>""; ROW()-1; "")) ]
- Produto → Nome do produto adquirido (preenchido pelo formulário de compras).
- Chave do Produto → Código específico do produto (preenchido pelo formulário).
- Valor da Compra (R$) → Preço pago pelo produto (preenchido pelo formulário).
- Data de Compra → Data em que a compra foi realizada (preenchido pelo formulário).
- Fornecedor → Nome do fornecedor responsável pela venda (preenchido pelo formulário).

#### Automação e Formatação Condicional
1️⃣ Destaque por cor: A linha inteira da compra fica vermelha quando o produto ainda não foi vendido. Após a venda, a formatação condicional remove a cor.         
2️⃣ Filtro no formulário de vendas: Apenas produtos que ainda não foram vendidos (linhas vermelhas) aparecem como opções disponíveis no formulário de vendas.      

📌 Adicionar imagens para demonstrar a tabela e a formatação condicional.

### 2. Tabela de Vendas
Essa tabela armazena os registros de vendas e possui as seguintes colunas:

- IdCliente → Código do cliente que realizou a compra (preenchido automaticamente pelo formulário).
- idProduto → Identificador do produto vendido (preenchido automaticamente pelo formulário).
- Valor da Venda (R$) → Preço de venda do produto (preenchido automaticamente pelo formulário).
- Tarifa (R$) → Taxa cobrada pela plataforma (preenchido automaticamente pelo formulário).
- Data da Venda → Data da transação (preenchido pelo formulário).
- Vendedor → Nome do vendedor responsável (preenchido pelo formulário).
- Valor da Compra → Obtido automaticamente da tabela de compras através do idProduto.
- Lucro → Calculado automaticamente pela fórmula: [ Valor da Venda - Valor da Compra - Tarifa ].Se o lucro for negativo, a célula é formatada em vermelho.
- Conclusão → Lista suspensa para indicar se a venda foi concluída ou devolvida.
🔸 Se for "Devolução a você", a linha fica amarela.                                                                           
🔸Se for "Devolução ao cliente", a célula fica laranja e o lucro é ajustado para [ -(Valor da Compra + Valor da Venda) ]

# AQUI FICA O CODIGO ONEDIT

- Produto e IdCompra → Apenas para organização e para referência nos códigos de automação.
# AQUI TEMOS O FORMATARPRODUTOS, SE BASEIAM NESSA TABELA PARA PREENCHER DE VERMELHO EEM COMPRAS - BOTA EM COMPRAS 

📌 Adicionar imagens das fórmulas e exemplos de vendas com lucro negativo e devoluções.

### 3. Tabela de Clientes
Essa tabela armazena os clientes cadastrados e suas informações de contato:

- idCliente → Identificador único do cliente (preenchido automaticamente pelo formulário).
- CPF → Número do CPF do cliente (preenchido pelo formulário).
- Nome Completo → Nome completo do cliente (preenchido pelo formulário).
- Telefone → Contato do cliente (preenchido pelo formulário).
- Email → Endereço de e-mail (preenchido pelo formulário).
- Problemas → Coluna que contabiliza quantas vezes um cliente teve problemas com compras. Essa informação é obtida automaticamente da tabela de vendas, verificando ocorrências de devolução.
🔸Se o cliente tiver mais de uma ocorrência de problema, a célula fica vermelha.
# AQUI FICA O CODIGO CONTARPROBLEMAS

📌 Adicionar imagens demonstrando a planilha de clientes e o código de contagem de problemas.

### 4. Tabela de Informações
Essa tabela contém informações gerais utilizadas para preenchimento automático dos formulários:

- Lista de Produtos → Todos os produtos disponíveis na loja.
- Valor de Venda → Preço pelo qual cada produto é vendido.
- Tarifa → Taxa aplicada a cada produto.

##### Os dados dessa tabela são utilizados para preencher automaticamente os valores nos formulários de compras e vendas, garantindo que as informações estejam sempre atualizadas.
# AQUI OS CODIGOS FORMATARPRODUTOS E ATUALIZAR OPÇOES

📌 Adicionar imagens demonstrando a tabela de informações e como os dados são puxados para os formulários.

