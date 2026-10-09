# Casa de Bolo Vovó Leila - Sistema Completo de Gestão e Pedidos 🍰

Sistema moderno para confeitaria e franquia de bolos artesanais com suporte a múltiplas unidades, catálogo dinâmico de produtos, pedidos via WhatsApp com divisão de pagamento, e painel administrativo com controle por loja e visão master do proprietário.

---

## 🚀 Como Executar o Projeto Localmente

### 1. Pré-requisitos
- **Node.js** (versão 18.x ou superior recomendada)
- **NPM** ou **Yarn** ou **Bun** ou **PNPM**

Verifique se possui o Node instalado abrindo o terminal e digitando:
```bash
node -v
npm -v
```

### 2. Instalação das Dependências
No terminal, dentro da pasta descompactada do projeto, execute:
```bash
npm install
```

### 3. Executando em Modo de Desenvolvimento
Para iniciar o servidor local:
```bash
npm run dev
```
O Vite iniciará o projeto em: `http://localhost:3000` (ou porta indicada no terminal). Abra esse endereço no seu navegador!

### 4. Gerando a Versão para Produção (Build)
Para compilar o projeto otimizado para deploy:
```bash
npm run build
```
Os arquivos prontos para publicação estarão na pasta `dist/`.

---

## 🔐 Acessos e Credenciais do Painel Administrativo

O sistema possui dois níveis de acesso com permissões isoladas:

### 1. Painel Master do Dono / Gerente Geral
- **Login:** `admin`
- **Senha:** `123456`
- **Permissões:**
  - Visão global de todas as 4 lojas (vendas, métricas consolidadas, faturamento).
  - Adição e exclusão de produtos em toda a rede.
  - Alteração global e individual de preços.
  - Gerenciamento de cupons de desconto para todas as unidades.
  - Configuração de taxas de entrega e horários de funcionamento de cada filial.

### 2. Painel dos Atendentes por Unidade (Isolado)
Cada filial possui seu próprio login seguro. As alterações feitas (preço local, estoque, ativação/desativação do bolo) afetam **apenas a loja logada**:
- **Loja 1 (Centro - Rua Cel. Oliveira Lima, 450):**
  - Usuário: `loja1` | Senha: `123`
- **Loja 2 (Vila Assunção - Av. Dr. Erasmo, 280):**
  - Usuário: `loja2` | Senha: `123`
- **Loja 3 (Bairro Jardim - Rua das Figueiras, 810):**
  - Usuário: `loja3` | Senha: `123`
- **Loja 4 (Parque das Nações - Rua Oratório, 1420):**
  - Usuário: `loja4` | Senha: `123`

---

## 🛠️ Tecnologias Utilizadas

- **React 19** com **TypeScript**
- **Vite 6 / 8** (Build rápido e otimizado)
- **Tailwind CSS v4** (Estilização moderna e responsiva)
- **Firebase Firestore** (Persistência em tempo real para pedidos, produtos e lojas)
- **Lucide Icons & Material Symbols**
- **Motion / Vaul** (Animações fluidas e drawers responsivos)

---

## 📁 Estrutura de Pastas

```
├── public/                 # Imagens, logotipos e arquivos estáticos
├── src/
│   ├── components/         # Componentes reutilizáveis (Header, Footer, CartDrawer, etc.)
│   ├── contexts/           # Estados globais (AppContext, Carrinho, Loja Selecionada)
│   ├── data/               # Dados iniciais e catálogo padrão de bolos
│   ├── services/           # Integração com Firebase e persistência
│   ├── types/              # Definições de tipos TypeScript
│   ├── views/              # Telas (HomeView, MenuView, StoresView, AdminView, Checkout)
│   ├── App.tsx             # Componente raiz com navegação
│   └── main.tsx            # Ponto de entrada React
├── firebase-applet-config.json
├── package.json
└── vite.config.ts
```

---

## ☁️ Hospedagem / Deploy Recomendado

Este projeto pode ser publicado diretamente em provedores como:
- **Vercel** (`npm run build`, diretório de saída: `dist`)
- **Netlify**
- **Firebase Hosting**
- **Render / Railway / Cloud Run**
