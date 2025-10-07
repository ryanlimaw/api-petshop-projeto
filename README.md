# 🐾 API Petshop Simples


API básica para petshop com TypeScript, Prisma e Zod.

## 🚀 Como rodar

```bash
# 1. Instalar dependências
npm install

# 2. Gerar cliente Prisma
npx prisma generate

# 3. Criar banco de dados
npx prisma db push

# 4. Executar servidor
npx ts-node src/server.ts
```

## 📚 Documentação Swagger

Acesse: `http://localhost:3000/api-docs`

## 📋 Endpoints

### Clientes
- `GET /api/clientes` - Listar clientes
- `GET /api/clientes/:id` - Buscar cliente
- `POST /api/clientes` - Criar cliente
- `PUT /api/clientes/:id` - Atualizar cliente
- `DELETE /api/clientes/:id` - Deletar cliente

### Pets
- `GET /api/pets` - Listar pets
- `GET /api/pets/:id` - Buscar pet
- `POST /api/pets` - **Adicionar pet** ⭐
- `PUT /api/pets/:id` - Atualizar pet
- `DELETE /api/pets/:id` - Deletar pet

### Serviços
- `GET /api/servicos` - **Listar serviços** ⭐
- `GET /api/servicos/:id` - Buscar serviço
- `POST /api/servicos` - **Adicionar serviço** ⭐
- `PUT /api/servicos/:id` - Atualizar serviço
- `PUT /api/servicos/:id/realizado` - Marcar como realizado
- `DELETE /api/servicos/:id` - Deletar serviço

## 📝 Exemplos

### Criar Cliente
```json
POST /api/clientes
{
  "nome": "João Silva",
  "email": "joao@email.com",
  "telefone": "11999999999"
}
```

### Adicionar Pet
```json
POST /api/pets
{
  "nome": "Rex",
  "especie": "Cachorro",
  "clienteId": 1
}
```

### Adicionar Serviço
```json
POST /api/servicos
{
  "tipo": "Banho e Tosa",
  "preco": 80.00,
  "clienteId": 1,
  "petId": 1
}
```

### Listar Serviços
```
GET /api/servicos
```
Resposta:
```json
[
  {
    "id": 1,
    "tipo": "Banho",
    "preco": 50.00,
    "realizado": false,
    "clienteId": 1,
    "petId": 1
  },
  {
    "id": 2,
    "tipo": "Tosa",
    "preco": 80.00,
    "realizado": true,
    "clienteId": 1,
    "petId": 1
  }
]
```

Servidor rodará em `http://localhost:3000`