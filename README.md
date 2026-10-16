# Remix Speranza (Speranza Ateliê)

O **Remix Speranza** é o código-fonte que alimenta a plataforma web do **Speranza Ateliê**, um e-commerce especializado em **porcelanas artesanais**. O programa foi projetado para atuar como uma vitrine digital sofisticada e minimalista, combinando uma identidade visual de forte influência escandinava — com cores neutras, texturas sutis e tipografia elegante — a uma experiência de navegação fluida voltada ao conceito de *slow-living*.

A finalidade deste projeto é fornecer um catálogo interativo e dinâmico onde clientes podem explorar peças exclusivas de cerâmica e porcelana, simulando uma jornada de compras moderna e altamente responsiva.

---

## 🛠️ Tecnologias e Ferramentas

A aplicação foi estruturada utilizando ferramentas modernas que otimizam o desempenho e a manutenção do código:

* **Linguagem Principal:** TypeScript (adicionando tipagem estática e maior previsibilidade ao fluxo de dados).
* **Interface e Estilização:** Tailwind CSS (`tailwind.config.ts`), responsável pela consistência visual limpa e ambientação estética da loja.
* **Componentes de UI:** Bibliotecas modulares organizadas sob as diretrizes do arquivo `components.json`.
* **Banco de Dados & Backend:** **Supabase** (diretório `/supabase`), integrado de forma ativa para gerenciar e fornecer os dados reais do catálogo de produtos exposto na aplicação.

---

## 🚀 Execução e Inicialização

O projeto oferece flexibilidade e pode ser iniciado tanto em ambientes baseados no gerenciador nativo **Bun** quanto no ecossistema tradicional do **Node.js**.

### Passo Prévio: Obtenção do Código e Acesso à Pasta

Se você baixou o projeto como um arquivo compactado (ZIP) ou clonou o repositório oficial, certifique-se de entrar na pasta correta do projeto (`remix-speranza-main`) antes de rodar os comandos de instalação:

```bash
# Caso vá clonar via Git utilizando o endereço oficial do repositório:
git clone https://github.com/sosogfm/remix-speranza.git

# CASO VOCÊ ESTEJA UTILIZANDO A PASTA EXTRAÍDA DIRETAMENTE DA ENTREGA:
cd remix-speranza-main
```

Após garantir que o seu terminal está apontando para a raiz da pasta do projeto, escolha uma das opções abaixo para instalar as dependências e subir o servidor:

### Opção 1: Inicialização Nativa com Bun (Recomendado)
Certifique-se de ter o Bun instalado em sua máquina.

1. Instale as dependências locais:
   ```bash
   bun install
   ```
2. Inicie o servidor de desenvolvimento utilizando o executor integrado do ecossistema:
   ```bash
   bunx --bun vite
   ```

### Opção 2: Inicialização Alternativa com Node.js e npm
Caso prefira operar sem o utilitário `bunx`, o projeto pode ser executado diretamente através do gerenciador de pacotes do Node.js:

1. Instale as dependências mapeadas no `package.json`:
   ```bash
   npm install
   ```
2. Execute diretamente o binário do construtor Vite para subir o servidor local:
   ```bash
   npx vite
   ```

Após rodar o comando de sua escolha, o terminal informará o endereço local ativo (geralmente `http://localhost:5173`). Abra esta URL no seu navegador para interagir com o programa.

---

## 🛍️ Funcionamento e Fluxo de Uso Principal

A interação com a plataforma do Speranza Ateliê ocorre de forma totalmente visual através das rotinas da interface gráfica:

1. **Navegação e Consulta Dinâmica:** Ao acessar a aplicação, o catálogo de porcelanas artesanais realiza uma **consulta direta e em tempo real ao banco de dados do Supabase** para renderizar as informações, imagens e o estoque atualizado das peças na grade editorial.
2. **Seleção de Produtos:** O usuário navega pela listagem e clica em uma peça para acessar sua página de detalhes, onde encontra informações detalhadas sobre o processo de produção artística.
3. **Adicionar Itens à Sacola:** Ao acionar o botão de compra:
   * **O que acontece na tela:** O sistema emite imediatamente uma **notificação visual de sucesso** confirmando a inserção do produto. A interface não abre menus suspensos ou carrinhos laterais automáticos (*drawers*).
4. **Gerenciamento de Compras (Página da Sacola):** Para ajustar as quantidades de itens selecionados, revisar valores ou prosseguir com o pedido, o usuário deve navegar especificamente até a **página dedicada à sacola de compras**.

### Persistência de Dados e Resultado Esperado
Enquanto a listagem de produtos depende ativamente do backend no Supabase, o estado atual e o conteúdo da sacola de compras são **armazenados e persistidos localmente no navegador do cliente**. Isso assegura que a seleção de porcelanas seja mantida de forma assíncrona e segura mesmo se a página for recarregada ou fechada.
