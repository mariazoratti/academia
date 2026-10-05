# Roadmap — Academia da Cidade

## Análise
- [x] Analisar requisitos do projeto Academia da Cidade
- [x] Definir entidades (Academia e Aparelho)
- [x] Definir funcionalidades (CRUD de Academias, CRUD de Aparelhos, Health Check)
- [x] Definir arquitetura separada (Backend REST Node.js/Express + Frontend Vanilla HTML/CSS/JS)

## Backend
- [x] Inicializar projeto Node.js no diretório `backend/`
- [x] Configurar Express, CORS e dotenv
- [x] Configurar conexão com MongoDB via Mongoose (com resiliência e serverless cache)
- [x] Criar Models (Academia e Aparelho como subdocumento com validações)
- [x] Criar Controllers com respostas JSON padronizadas (`{ success, data }` / `{ success, error }`)
- [x] Criar Routes (`/api/health`, `/api/academias`, `/api/academias/:id/aparelhos`)
- [x] Implementar validações de entrada e IDs
- [x] Implementar tratamento centralizado de erros
- [x] Criar arquivo de configuração `vercel.json` para backend serverless
- [x] Criar `.env.example` e documentação `api.md`

## Frontend
- [x] Criar estrutura base no diretório `frontend/` (`index.html`, `style.css`, `script.js`)
- [x] Definir identidade visual "Academia da Cidade" (design moderno, fitness/esportivo, paleta coerente, tipografia, glassmorphism e sombras elegantes)
- [x] Criar header hero com métricas e busca/filtro em tempo real
- [x] Criar listagem responsiva em cards com tags de bairros e contagem de aparelhos
- [x] Criar modal de detalhes da academia com gerenciamento completo de aparelhos
- [x] Criar modais para cadastro e edição de academias e aparelhos
- [x] Implementar estados de interface: Carregando, Sucesso, Erro e Lista Vazia
- [x] Integrar consumo via `fetch()` com backend

## Testes
- [x] Testar endpoint de Health Check (`GET /api/health`)
- [x] Testar CRUD completo de Academias localmente
- [x] Testar CRUD completo de Aparelhos localmente
- [x] Testar casos de borda e validações (ID inválido, dados obrigatórios ausentes, 404)
- [x] Testar interface visual, formulários e interações
- [x] Testar contratos e integração de rotas

## GitHub
- [x] Inicializar repositório Git no `backend/`
- [ ] Inicializar repositório Git no `frontend/`
- [ ] Publicar repositório `academia-da-cidade-backend` no GitHub (Pendente de autorização remota da conta)
- [ ] Publicar repositório `academia-da-cidade-frontend` no GitHub (Pendente de autorização remota da conta)

## Vercel
- [ ] Deploy do Backend na Vercel (Pendente de login interativo/token Vercel)
- [ ] Configurar variáveis de ambiente do Backend na Vercel (`MONGODB_URI`)
- [ ] Deploy do Frontend na Vercel (Pendente de login interativo/token Vercel)
- [ ] Validar navegação e operações ponta a ponta em produção

## Finalização
- [x] Atualizar README do Backend com instruções detalhadas
- [x] Atualizar README do Frontend com instruções detalhadas
- [x] Atualizar `Contexto.md` e `Roadmap.md`
- [x] Gerar relatório final de entrega com todas as especificações e status detalhados
