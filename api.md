# Documentação da API REST — Academia da Cidade

Esta documentação descreve todos os endpoints disponíveis na API do projeto **Academia da Cidade**, incluindo parâmetros, formatos de requisição, respostas JSON padronizadas, códigos HTTP e exemplos com `curl`.

---

## 🌐 URLs Base

- **Ambiente Local:** `http://localhost:3000`
- **Ambiente de Produção (Vercel):** `https://academia-da-cidade-backend.vercel.app` (substitua pelo domínio final)

---

## 📦 Padrão de Respostas

Todas as respostas da API seguem um formato JSON unificado:

### Resposta de Sucesso
```json
{
  "success": true,
  "data": { ... } // ou array [...]
}
```

### Resposta de Erro
```json
{
  "success": false,
  "error": "Descrição detalhada do erro ocorrido"
}
```

---

## 🩺 1. Health Check

### `GET /api/health`
Verifica a integridade do serviço e o estado da conexão com o banco de dados MongoDB.

- **Códigos HTTP:** `200 OK` (se banco conectado), `503 Service Unavailable` (se banco desconectado).

#### Exemplo de Resposta (200 OK):
```json
{
  "success": true,
  "status": "UP",
  "timestamp": "2026-10-05T12:00:00.000Z",
  "uptime": 124.5,
  "database": {
    "status": "Conectado",
    "connected": true
  },
  "service": "Academia da Cidade API"
}
```

#### Exemplo com `curl`:
```bash
curl -X GET http://localhost:3000/api/health
```

---

## 🏋️ 2. Academias

### 2.1 Listar Todas as Academias
`GET /api/academias`

#### Parâmetros de Query (Opcionais):
- `busca` (string): Busca textual por nome, bairro ou endereço.
- `bairro` (string): Filtra academias de um bairro específico.

#### Códigos HTTP: `200 OK`

---

### 2.2 Obter Academia por ID
`GET /api/academias/:id`

#### Códigos HTTP:
- `200 OK`: Sucesso.
- `400 Bad Request`: ID inválido.
- `404 Not Found`: Academia não encontrada.

---

### 2.3 Cadastrar Academia
`POST /api/academias`

#### Corpo da Requisição (JSON):
| Campo | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `nome` | String | Sim | Nome da academia (mínimo 3 caracteres) |
| `endereco` | String | Sim | Logradouro e número |
| `bairro` | String | Sim | Bairro onde se localiza |
| `telefone` | String | Não | Telefone de contato |
| `descricao` | String | Não | Detalhes e observações sobre a unidade |
| `aparelhos` | Array | Não | Lista inicial de aparelhos (opcional) |

#### Códigos HTTP:
- `201 Created`: Cadastrada com sucesso.
- `400 Bad Request`: Campo obrigatório ausente ou inválido.

---

### 2.4 Atualizar Academia
`PUT /api/academias/:id`

#### Códigos HTTP:
- `200 OK`: Atualizada com sucesso.
- `400 Bad Request`: ID inválido ou campos com valores vazios inválidos.
- `404 Not Found`: Academia não encontrada.

---

### 2.5 Excluir Academia
`DELETE /api/academias/:id`

#### Códigos HTTP:
- `200 OK`: Excluída com sucesso.
- `400 Bad Request`: ID inválido.
- `404 Not Found`: Academia não encontrada.

---

## ⚙️ 3. Aparelhos

### 3.1 Listar Aparelhos de uma Academia
`GET /api/academias/:id/aparelhos`

---

### 3.2 Cadastrar Aparelho em uma Academia
`POST /api/academias/:id/aparelhos`

| Campo | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `nome` | String | Sim | Nome do equipamento |
| `categoria` | String | Sim | Categoria (ex: Musculação, Cardio, Calistenia) |
| `marca` | String | Não | Fabricante / Linha |
| `quantidade` | Number | Sim | Quantidade inteira >= 1 |
| `descricao` | String | Não | Instruções de uso ou músculos trabalhados |

---

### 3.3 Atualizar Aparelho
`PUT /api/academias/:id/aparelhos/:aparelhoId`

---

### 3.4 Excluir Aparelho
`DELETE /api/academias/:id/aparelhos/:aparelhoId`
