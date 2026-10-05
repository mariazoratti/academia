# Contexto — Academia da Cidade

## 1. Tema do Projeto
**Academia da Cidade** — Plataforma moderna para gerenciamento e consulta pública e administrativa de academias municipais e dos aparelhos esportivos de musculação, calistenia, cardio e alongamento disponíveis em cada unidade.

## 2. Objetivo
Proporcionar aos munícipes e gestores públicos uma interface moderna, visual e intuitiva para consultar academias, verificar aparelhos disponíveis por unidade, cadastrar novas unidades e atualizar o inventário esportivo, promovendo saúde, lazer e atividade física em toda a cidade.

## 3. Funcionalidades Principais
### Academias
- Cadastrar nova academia (nome, endereço, bairro, telefone, descrição)
- Listar todas as academias cadastradas com busca em tempo real por nome/bairro/endereço
- Visualizar detalhes de uma academia e sua lista de aparelhos
- Editar dados da academia
- Excluir academia e seus vínculos com confirmação de segurança

### Aparelhos
- Cadastrar aparelho associado a uma academia (nome, categoria, marca, quantidade, descrição)
- Listar aparelhos de uma academia selecionada com filtros por categoria (Musculação, Cardio, Calistenia, Alongamento, Funcional)
- Editar dados e quantidade de um aparelho
- Excluir aparelho

### Sistema / API
- Health check: `GET /api/health`
- Respostas padronizadas no formato `{ "success": boolean, "data": ... }` ou `{ "success": boolean, "error": string }`
- Tratamento robusto de códigos HTTP (200, 201, 400, 404, 500, 503)

## 4. Tecnologias
- **Backend:** Node.js, Express, MongoDB com Mongoose, CORS, dotenv
- **Frontend:** HTML5 semântico, CSS3 moderno (Vanilla CSS com Design System Fitness, Glassmorphism, CSS Grid/Flexbox), JavaScript puro (ES6+, Fetch API)
- **Hospedagem & Versionamento:** GitHub (repositórios separados) e Vercel (deploys separados)

## 5. Arquitetura
```
academia-da-cidade/
├── backend/
│   ├── src/
│   │   ├── config/       (conexão com MongoDB com cache serverless e fallback de desenvolvimento)
│   │   ├── controllers/  (regras de negócio de academias e aparelhos)
│   │   ├── models/       (schemas Mongoose)
│   │   ├── routes/       (rotas Express)
│   │   ├── middleware/   (tratamento centralizado de erros e 404)
│   │   ├── app.js        (configuração da aplicação Express)
│   │   └── server.js     (servidor HTTP local)
│   ├── tests/            (suite com 20 testes automatizados Node Test Runner)
│   ├── .env.example
│   ├── .gitignore
│   ├── package.json
│   ├── vercel.json
│   ├── api.md
│   └── README.md
├── frontend/
│   ├── index.html        (estrutura HTML5 semântica e acessível)
│   ├── style.css         (design system esportivo e responsivo)
│   ├── script.js         (lógica da aplicação, estado e consumo REST)
│   ├── .gitignore
│   └── README.md
├── Roadmap.md
├── Contexto.md
└── api.md
```

## 6. Identidade Visual
- **Conceito:** Fitness de alto impacto, performance esportiva e bem-estar municipal.
- **Paleta de Cores:**
  - Fundo escuro esportivo: Grafite escuro / Slate (`#0A0E17`, `#121826`, `#161E31`)
  - Acento Primário: Laranja Energético (`#FF5722` / `#FF7043`) simbolizando força e movimento
  - Acento Secundário: Verde Vitalidade (`#10B981`) simbolizando saúde e dinamismo
  - Texto e contraste: Branco Puro (`#F8FAFC`) e Cinza Suave (`#94A3B8`)
- **Tipografia:** Fontes Google *Outfit* (títulos de impacto) e *Plus Jakarta Sans* (legibilidade).
- **Elementos:** Cards com detalhes de gradiente, badges temáticas para categorias, micro-interações, spinner animado haltere, notificações toast e modais interativos.

## 7. Alterações Realizadas
- Construção completa do Backend com Node.js, Express e Mongoose.
- Criação dos Models, Controllers, Middlewares de validação/erros e Rotas REST completas.
- Criação e execução de 20 testes automatizados cobrindo todos os fluxos e casos de borda com 100% de aprovação.
- Construção completa do Frontend em HTML5, CSS3 moderno e JavaScript puro consumindo a API via `fetch()`.
- Criação de todas as telas, modais, formulários com validações, filtros e estados de interface (carregando, vazio, erro, sucesso).
- Documentação técnica exaustiva: `Roadmap.md`, `Contexto.md`, `api.md` e `README.md` no backend e frontend.
- Inicialização de repositório Git local no backend.

## 8. Estado Atual
- Backend: Concluído e testado.
- Frontend: Concluído e integrado.
- MongoDB: Configurado com ODM Mongoose, cache para Vercel e suporte a string Atlas.
- API REST: 100% implementada com documentação completa.
- Identidade Visual: Aplicada com tema exclusivo Academia da Cidade.

## 9. URLs de Produção e Repositórios
- **GitHub Backend:** [Pendente de autorização/criação remota via gh/token do usuário]
- **GitHub Frontend:** [Pendente de autorização/criação remota via gh/token do usuário]
- **Vercel Backend:** [Pendente de deploy/token Vercel]
- **Vercel Frontend:** [Pendente de deploy/token Vercel]
