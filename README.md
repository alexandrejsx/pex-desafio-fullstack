## Teste Técnico - Vaga Fullstack

### Backend

1. **Criar endpoint POST /payments/:seller_id**

   Este endpoint deve registrar um pagamento com o seguinte payload:

   ```json
   {
     "amount": 15000,  // valor em centavos
     "type": "boleto",  // tipos: "boleto" ou "pix"
     "seller_id": "123",
     "created_at": "2024-06-21T10:00:00Z"
   }
   ```

2. **Criar endpoint GET /payments/:seller_id**

   Este endpoint deve listar todas as vendas de acordo com o `seller_id` e retornar o seguinte payload:

   ```json
   [
     {
       "amount": 15000,  // valor em centavos
       "type": "boleto",
       "seller_id": "123",
       "created_at": "2024-06-21T10:00:00Z"
     },
     {
       "amount": 20000,  // valor em centavos
       "type": "pix",
       "seller_id": "123",
       "created_at": "2024-06-22T11:30:00Z"
     }
   ]
   ```

3. **Criar endpoint GET /summary/:seller_id**

   Este endpoint deve retornar o valor total de todas as vendas e a quantidade de vendas de acordo com o `seller_id`, agrupadas por tipo de venda, com o seguinte payload:

   ```json
   [
     {
       "type": "boleto",
       "total_amount": 15000,  // valor em centavos
       "total_sales": 1
     },
     {
       "type": "pix",
       "total_amount": 20000,  // valor em centavos
       "total_sales": 1
     }
   ]
   ```

### Frontend

1. **Tela Dashboard**

   Após o login, na tela de Dashboard:

   - Consuma os endpoints `/payments/:seller_id` e `/summary/:seller_id` da API Backend.
   - Utilize os dados do endpoint `/summary/:seller_id` para exibir um gráfico, usando a biblioteca de sua preferência.
   - Abaixo do gráfico, exiba uma tabela com as vendas do Seller utilizando os dados do endpoint `/payments/:seller_id`.
