# JCAR Flow - Sistema de Gestão para Oficinas

> Sistema completo de gestão para oficinas mecânicas com controle de ordens de serviço, clientes, veículos, estoque e financeiro.

![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat&logo=supabase&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat&logo=tailwind-css&logoColor=white)

---

## 📋 Sobre o Projeto

JCAR Flow é um sistema moderno e intuitivo para gestão completa de oficinas mecânicas. Desenvolvido com as mais recentes tecnologias web, oferece uma experiência fluida e profissional para controlar todos os aspectos do seu negócio.

### ✨ Principais Funcionalidades

- **📝 Ordens de Serviço**
  - Criação e acompanhamento de OS com numeração automática
  - Kanban board com drag-and-drop para gestão visual
  - 6 status de acompanhamento (A Receber, Aguardando Aprovação, Aguardando Peça, Em Execução, Finalizado, Pronto para Retirada)
  - Vinculação com clientes, veículos e mecânicos
  - Histórico completo de cada serviço

- **👥 Gestão de Clientes**
  - Cadastro completo com dados de contato
  - Histórico de veículos por cliente
  - Busca rápida por nome ou telefone
  - Visualização de todos os serviços realizados

- **🚗 Controle de Veículos**
  - Cadastro detalhado (modelo, placa, ano, cor)
  - Vinculação automática com proprietários
  - Histórico de manutenções
  - Busca por placa ou modelo

- **📦 Gestão de Estoque**
  - Controle de peças e produtos
  - Alertas de estoque baixo
  - Preços de compra e venda
  - Cálculo automático de margem de lucro
  - Código de barras automático

- **👨‍🔧 Gestão de Mecânicos**
  - Cadastro de profissionais
  - Especialidades
  - Atribuição de serviços

- **📊 Dashboard Intuitivo**
  - Estatísticas em tempo real
  - Visão geral do negócio
  - Indicadores de performance

---

## 🚀 Tecnologias

Este projeto foi construído com tecnologias modernas e robustas:

- **Frontend Framework:** [React 18](https://react.dev/) com [TypeScript](https://www.typescriptlang.org/)
- **Build Tool:** [Vite](https://vitejs.dev/) - Build ultrarrápido
- **Estilização:** [Tailwind CSS](https://tailwindcss.com/) + [shadcn/ui](https://ui.shadcn.com/)
- **Banco de Dados:** [Supabase](https://supabase.com/) (PostgreSQL)
- **State Management:** [React Query (TanStack Query)](https://tanstack.com/query)
- **Roteamento:** [React Router v6](https://reactrouter.com/)
- **Formulários:** [React Hook Form](https://react-hook-form.com/) + [Zod](https://zod.dev/)
- **Ícones:** [Lucide React](https://lucide.dev/)
- **Notificações:** [Sonner](https://sonner.emilkowal.ski/)

---

## 📦 Instalação

### Pré-requisitos

- Node.js 18+ ([Instalar com nvm](https://github.com/nvm-sh/nvm))
- npm ou yarn
- Conta no [Supabase](https://supabase.com/) (gratuita)

### Passo a Passo

1. **Clone o repositório**
```bash
git clone https://github.com/davicavalcanti1/sistema-jcar-automaticos.git
cd sistema-jcar-automaticos
```

2. **Instale as dependências**
```bash
npm install
```

3. **Configure as variáveis de ambiente**

Crie um arquivo `.env` na raiz do projeto com suas credenciais do Supabase:

```env
VITE_SUPABASE_URL=sua_url_do_supabase
VITE_SUPABASE_PUBLISHABLE_KEY=sua_chave_publica
```

> 💡 **Como obter as credenciais:**
> 1. Acesse [supabase.com](https://supabase.com)
> 2. Crie um novo projeto (ou use um existente)
> 3. Vá em Settings > API
> 4. Copie a URL e a `anon/public` key

4. **Execute as migrations do banco de dados**

As tabelas necessárias estão em `supabase/migrations/`. Você pode executá-las pelo painel do Supabase ou usando a CLI.

5. **Inicie o servidor de desenvolvimento**
```bash
npm run dev
```

O aplicativo estará disponível em `http://localhost:5173`

---

## 🎯 Como Usar

### Primeira Utilização

1. **Cadastre Mecânicos**
   - Acesse a seção de configurações (em breve)
   - Adicione os mecânicos da sua oficina

2. **Cadastre Clientes**
   - Vá para "Clientes"
   - Clique em "Novo Cliente"
   - Preencha os dados e salve

3. **Cadastre Veículos**
   - Vá para "Veículos"
   - Clique em "Novo Veículo"
   - Selecione o cliente e preencha os dados

4. **Crie Ordens de Serviço**
   - No Dashboard ou em "Ordens de Serviço"
   - Clique em "Nova OS"
   - Selecione cliente, veículo e descreva o serviço
   - O número da OS é gerado automaticamente

5. **Gerencie pelo Kanban**
   - Arraste e solte os cards entre as colunas
   - As mudanças são salvas automaticamente no banco

### Fluxo de Trabalho Recomendado

```
Cliente chega → Criar OS (status: A Receber)
    ↓
Orçamento aprovado → Mover para "Aguardando Aprovação"
    ↓
Peças disponíveis → Mover para "Em Execução"
    ↓
Serviço concluído → Mover para "Finalizado"
    ↓
Cliente notificado → Mover para "Pronto para Retirada"
```

---

## 📁 Estrutura do Projeto

```
jcar-flow-main/
├── src/
│   ├── components/          # Componentes React
│   │   ├── clientes/       # Componentes de clientes
│   │   ├── veiculos/       # Componentes de veículos
│   │   ├── estoque/        # Componentes de estoque
│   │   ├── kanban/         # Board Kanban
│   │   ├── layout/         # Layout e navegação
│   │   └── ui/             # Componentes shadcn/ui
│   ├── hooks/              # Custom React Hooks
│   │   ├── useClientes.ts  # Hook de clientes
│   │   ├── useVeiculos.ts  # Hook de veículos
│   │   ├── useEstoque.ts   # Hook de estoque
│   │   └── useOrdensServico.ts
│   ├── pages/              # Páginas da aplicação
│   ├── integrations/       # Integrações (Supabase)
│   ├── types/              # Definições TypeScript
│   └── lib/                # Utilitários
├── supabase/               # Configuração do Supabase
│   └── migrations/         # Migrations do banco
└── public/                 # Arquivos estáticos
```

---

## 🗄️ Banco de Dados

### Tabelas Principais

- **clientes** - Dados dos clientes
- **veiculos** - Veículos cadastrados
- **ordens_servico** - Ordens de serviço
- **estoque** - Peças e produtos
- **mecanicos** - Profissionais da oficina
- **itens_orcamento** - Itens de cada OS

### Relacionamentos

```
clientes (1) ──→ (N) veiculos
clientes (1) ──→ (N) ordens_servico
veiculos (1) ──→ (N) ordens_servico
mecanicos (1) ──→ (N) ordens_servico
ordens_servico (1) ──→ (N) itens_orcamento
estoque (1) ──→ (N) itens_orcamento
```

---

## 🛠️ Scripts Disponíveis

```bash
# Desenvolvimento
npm run dev          # Inicia servidor de desenvolvimento

# Build
npm run build        # Cria build de produção
npm run build:dev    # Build em modo desenvolvimento

# Qualidade de Código
npm run lint         # Executa ESLint
npm run preview      # Preview do build de produção
```

---

## 🎨 Personalização

### Temas e Cores

As cores do sistema podem ser personalizadas em `tailwind.config.ts`:

```typescript
colors: {
  primary: { ... },    // Cor principal
  secondary: { ... },  // Cor secundária
  success: { ... },    // Verde (sucesso)
  warning: { ... },    // Amarelo (avisos)
  destructive: { ... } // Vermelho (erros)
}
```

### Componentes UI

Todos os componentes UI estão em `src/components/ui/` e podem ser customizados individualmente.

---

## 🤝 Contribuindo

Contribuições são bem-vindas! Para contribuir:

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/MinhaFeature`)
3. Commit suas mudanças (`git commit -m 'Adiciona MinhaFeature'`)
4. Push para a branch (`git push origin feature/MinhaFeature`)
5. Abra um Pull Request

---

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

---

## 👨‍💻 Autor

**Davi Cavalcanti Araújo**

- GitHub: [@davicavalcantiaraujo1-commits](https://github.com/davicavalcantiaraujo1-commits)

---

## 🙏 Agradecimentos

- [shadcn/ui](https://ui.shadcn.com/) pelos componentes lindos
- [Supabase](https://supabase.com/) pelo backend incrível
- [Lovable](https://lovable.dev/) pela plataforma de desenvolvimento

---

## 📞 Suporte

Encontrou um bug ou tem uma sugestão? 

- Abra uma [issue](https://github.com/davicavalcantiaraujo1-commits/sistema-jcar-automaticos/issues)
- Entre em contato através do GitHub

---

<div align="center">

**Feito com ❤️ para oficinas mecânicas**

⭐ Se este projeto foi útil, considere dar uma estrela!

</div>
