# Remix Speranza

O **Remix Speranza** é uma plataforma de e-commerce premium voltada para o mercado de alta decoração, curadoria de objetos e o conceito de *slow-living*. O programa foi desenvolvido para oferecer uma experiência de compra digital imersiva, sofisticada e fluida, servindo como uma vitrine e sistema de vendas para produtos artesanais e de design, tais como luminárias, cerâmicas, móveis e vasos.

Sua finalidade é unir uma estética minimalista de forte influência escandinava com uma engenharia de software de alta performance, garantindo que a navegação por peças exclusivas seja tão agradável quanto visitar uma galeria física de design.

---

## 🛠️ Tecnologias e Dependências

A aplicação foi construída utilizando ferramentas modernas do ecossistema de desenvolvimento web focado em tipagem estática, performance e componentização:

* **Linguagem Principal:** TypeScript (fornecendo segurança de tipos e inteligência no desenvolvimento).
* **Ambiente de Execução / Gerenciadores:** Node.js (com suporte nativo e travas via `package.json`) ou Bun (com arquivos de lock dedicados `bun.lock` e `bun.lockb`).
* **Framework de Construção & Bundler:** Vite (`vite.config.ts`), que assegura compilação ultra-rápida e hot-reload durante o desenvolvimento.
* **Interface e Estilização:** Tailwind CSS (`tailwind.config.ts` e `postcss.config.js`), utilizado para aplicar a paleta de cores neutras e texturas de fundo que definem a identidade visual do projeto.
* **Persistência de Dados & Backend:** Supabase (diretório `/supabase`), atuando como infraestrutura para o banco de dados, autenticação de usuários e gerenciamento do catálogo de produtos.
* **Qualidade de Código e Testes:** ESLint (`eslint.config.js`) para padronização de código e Vitest (`vitest.config.ts`) para a execução de testes automatizados.

---

## 🚀 Execução e Uso

### Pré-requisitos
Antes de iniciar, certifique-se de ter instalado em sua máquina o **Node.js** (LTS) e o **npm**, ou alternativamente o **Bun**.

### Passo a Passo para Iniciar o Programa

1. **Clonar e Acessar o Repositório:**
   ```bash
   git clone https://github.com
   cd remix-speranza
   ```

2. **Configurar as Variáveis de Ambiente:**
   Duplique o arquivo de exemplo `.env.development` existente na raiz do projeto, renomeando-o para `.env`:
   ```bash
   cp .env.development .env
   ```
   Abra o arquivo `.env` e insira as chaves de API fornecidas pelo seu painel do **Supabase** (`SUPABASE_URL` e `SUPABASE_ANON_KEY`).

3. **Instalar as Dependências:**
   Instale os pacotes necessários utilizando o gerenciador de sua preferência:
   ```bash
   npm install
   # ou, se preferir usar o Bun:
   bun install
   ```

4. **Iniciar o Servidor de Desenvolvimento:**
   Execute o comando de inicialização contido nos scripts do projeto:
   ```bash
   npm run dev
   # ou, utilizando o Bun:
   bun run dev
   ```

O terminal exibirá um endereço local ativo (ex: `http://localhost:5173`). Abra essa URL em seu navegador de preferência para interagir com o e-commerce.

---

## 🛍️ Fluxo Principal de Uso e Interação

Ao abrir a interface gráfica do **Remix Speranza**, o usuário realiza o fluxo padrão de compra através de interações visuais:

1. **Exploração da Vitrine (Homepage):** O usuário visualiza banners e fotografias em estilo *lifestyle* ambientando os produtos no mundo real, além de coleções selecionadas pelo curador da loja.
2. **Filtragem e Catálogo (Product Listing Page):** Ao navegar para a listagem, o usuário interage com um grid editorial espaçado, projetado para reduzir a fadiga visual, onde pode clicar sobre qualquer objeto (ex: uma luminária ou vaso de cerâmica).
3. **Página de Detalhes (Product Detail Page):** O usuário analisa imagens contextuais ampliadas e lê a história/origem artesanal daquela peça. Nesta seção, ele pode acionar duas interações principais:
   * Clicar no botão da **Wishlist** para salvar o item em sua lista de desejos.
   * Clicar no botão **Adicionar ao Carrinho**.
4. **Gerenciamento do Carrinho (Cart Drawer):** Ao adicionar um produto, um carrinho lateral desliza na tela de forma suave, exibindo a foto do item, quantidade e a atualização em tempo real do valor total do pedido.

### Resultado Esperado
O programa responde a todas as ações por meio de transições de tela altamente fluidas e assíncronas. Os dados das interações (como itens no carrinho ou estado de autenticação) são processados e validados em tempo real junto às APIs do Supabase, garantindo estabilidade e persistência de dados durante toda a sessão do cliente.
