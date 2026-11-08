# Scenara — Frontend

**Interface de simulação financeira e análise de cenários.**

O frontend da Scenara é responsável por oferecer uma experiência visual intuitiva e moderna para criação de projetos, gerenciamento de cenários financeiros, execução de simulações e análise de resultados.

A aplicação permite que usuários explorem diferentes possibilidades financeiras por meio de dashboards, indicadores, gráficos e ferramentas de comparação.

## Tecnologias

| Tecnologia | Utilização |
|---|---|
| React | Construção da interface |
| TypeScript | Tipagem estática |
| Vite | Ambiente de desenvolvimento |
| Tailwind CSS | Estilização |
| shadcn/ui | Componentes de interface |
| React Router | Navegação |
| Recharts | Visualização de dados |
| Axios | Comunicação com a API |
| React Hook Form | Gerenciamento de formulários |
| Zod | Validação de dados |

## Funcionalidades

### Autenticação
- Cadastro de usuários.
- Login.
- Gerenciamento de sessão.
- Proteção de rotas privadas.

### Dashboard
- Visão geral dos projetos.
- Indicadores financeiros.
- Resumo das simulações.
- Acesso rápido aos projetos recentes.

### Projetos
- Listagem de projetos.
- Criação de projetos.
- Visualização de detalhes.
- Edição e exclusão de projetos.

### Cenários
- Criação de cenários financeiros.
- Configuração das premissas.
- Edição de variáveis.
- Gerenciamento de cenários por projeto.

### Simulações
- Execução de simulações financeiras.
- Visualização de projeções mensais.
- Indicadores financeiros.
- Gráficos de receitas, custos e resultados.
- Histórico de execuções.

### Comparação
- Comparação entre cenários.
- Análise de indicadores.
- Visualização de diferenças entre projeções.

### Evolução planejada
- Visualização de contas financeiras conectadas.
- Análise de movimentações bancárias.
- Sugestões de premissas com base em dados históricos.
- Comparação entre resultados reais e projetados.

## Estrutura de diretórios

```text
frontend/
├── public/
│
├── src/
│   ├── assets/
│   │
│   ├── components/
│   │   ├── ui/
│   │   ├── layout/
│   │   ├── charts/
│   │   └── shared/
│   │
│   ├── pages/
│   │   ├── auth/
│   │   ├── dashboard/
│   │   ├── projects/
│   │   ├── scenarios/
│   │   ├── simulations/
│   │   └── comparison/
│   │
│   ├── layouts/
│   ├── routes/
│   ├── hooks/
│   ├── services/
│   ├── contexts/
│   ├── types/
│   ├── schemas/
│   ├── utils/
│   │
│   ├── App.tsx
│   └── main.tsx
│
├── .env.example
├── package.json
├── tsconfig.json
├── vite.config.ts
└── README.md
```

### Responsabilidade das pastas

| Diretório | Responsabilidade |
|---|---|
| `assets/` | Imagens, ícones e arquivos estáticos |
| `components/` | Componentes reutilizáveis |
| `pages/` | Páginas da aplicação |
| `layouts/` | Estruturas visuais compartilhadas |
| `routes/` | Configuração de rotas |
| `hooks/` | Hooks personalizados |
| `services/` | Comunicação com o backend |
| `contexts/` | Contextos globais |
| `types/` | Tipagens TypeScript |
| `schemas/` | Esquemas de validação |
| `utils/` | Funções auxiliares |

## Rotas da aplicação

| Rota | Descrição |
|---|---|
| `/login` | Autenticação |
| `/register` | Cadastro |
| `/app/dashboard` | Dashboard |
| `/app/projects` | Listagem de projetos |
| `/app/projects/new` | Novo projeto |
| `/app/projects/:projectId` | Detalhes do projeto |
| `/app/projects/:projectId/scenarios/new` | Novo cenário |
| `/app/projects/:projectId/scenarios/:scenarioId` | Detalhes do cenário |
| `/app/projects/:projectId/scenarios/:scenarioId/edit` | Edição do cenário |
| `/app/projects/:projectId/scenarios/:scenarioId/simulations` | Histórico de simulações |
| `/app/projects/:projectId/compare` | Comparação de cenários |

## Comunicação com o backend

O frontend consome uma API REST desenvolvida com Java e Spring Boot.

A comunicação é centralizada na pasta `services/`, evitando chamadas HTTP espalhadas pelos componentes.

Exemplo de organização:

```text
services/
├── api.ts
├── auth.service.ts
├── project.service.ts
├── scenario.service.ts
└── simulation.service.ts
```

A URL da API deve ser configurada por variável de ambiente:

```env
VITE_API_URL=http://localhost:8080/api
```

## Design e experiência

A interface da Scenara deve transmitir:

- Clareza na apresentação de informações financeiras.
- Sofisticação e simplicidade.
- Hierarquia visual bem definida.
- Facilidade de navegação.
- Consistência entre componentes.
- Boa experiência em diferentes tamanhos de tela.

Os gráficos devem facilitar a interpretação dos resultados, evitando excesso de informações visuais.

## Instalação e execução

### Pré-requisitos

- Node.js.
- npm.

### 1. Acessar o frontend

```bash
cd frontend
```

### 2. Instalar dependências

```bash
npm install
```

### 3. Configurar variáveis de ambiente

Crie um arquivo `.env`:

```env
VITE_API_URL=http://localhost:8080/api
```

### 4. Executar a aplicação

```bash
npm run dev
```

A aplicação estará disponível no endereço apresentado pelo Vite, normalmente:

```text
http://localhost:5173
```

### 5. Gerar build de produção

```bash
npm run build
```

## Boas práticas

- Utilizar TypeScript em todos os componentes.
- Priorizar componentes reutilizáveis.
- Centralizar as chamadas HTTP.
- Validar formulários antes do envio.
- Evitar duplicação de lógica.
- Separar regras de negócio da apresentação.
- Manter tipagens sincronizadas com os contratos da API.
- Implementar estados de carregamento, erro e ausência de dados.
- Não utilizar dados fictícios como se fossem respostas reais da API.

---

**Scenara — Explore possibilidades. Decida com clareza.**
