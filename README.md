# Remix Speranza

O **Remix Speranza** é uma aplicação web de e-commerce voltada para o mercado de alta decoração, curadoria de objetos e o conceito de *slow-living*. A plataforma foi projetada para atuar como uma vitrine digital sofisticada e minimalista para produtos de design e artesanais, tais como luminárias, cerâmicas, móveis e vasos.

A finalidade deste programa é unir uma interface de forte influência escandinava — com uso de cores neutras, tipografia elegante e espaçamentos generosos — a uma arquitetura moderna de software, permitindo que a navegação e a simulação de compras ocorram de forma rápida e responsiva.

---

## 🛠️ Tecnologias e Ferramentas

O ecossistema do projeto é baseado em ferramentas focadas em performance e tipagem estática:

* **Linguagem Principal:** TypeScript (garante previsibilidade e segurança no fluxo de dados).
* **Ambiente de Execução e Pacotes:** Bun (utilizado nativamente para o gerenciamento de dependências, geração de travas via `bun.lock` / `bun.lockb` e execução de scripts de infraestrutura).
* **Framework de Construção & Bundler:** Vite (`vite.config.ts`), responsável pelo empacotamento rápido e servidor local de desenvolvimento.
* **Interface e Estilização:** Tailwind CSS (`tailwind.config.ts`), configurado para criar a identidade visual limpa e os fundos texturizados do e-commerce.
* **Componentes de UI:** Bibliotecas integradas sob a estrutura do arquivo `components.json`.

---

## 🚀 Execução e Inicialização

### Pré-requisitos
Para rodar este projeto, é necessário ter o **Bun** instalado em sua máquina. A inicialização e a preparação do ambiente utilizam o executor de pacotes do Bun (`bunx`), impossibilitando a execução exclusiva por meio do Node.js/npm padrão sem este utilitário.

### Passo a Passo para Iniciar o Programa

1. **Clonar o Repositório:**
   Execute o comando abaixo preenchendo com a URL completa do seu repositório:
   ```bash
   git clone https://github.com
   cd remix-speranza
   ```

2. **Configurar as Variáveis de Ambiente:**
   A aplicação requer configurações locais para estabelecer comunicação com os serviços externos. Crie o arquivo `.env` na raiz do projeto:
   ```bash
   touch .env
   ```
   *Nota: O arquivo `.env.development` presente na raiz armazena configurações gerais de escopo de desenvolvimento e não deve ser modificado para chaves privadas.*

3. **Instalar as Dependências:**
   Instale os pacotes necessários utilizando o ecossistema do Bun:
   ```bash
   bun install
   ```

4. **Preparar o Ambiente e Iniciar:**
   Para garantir que todos os componentes e rotinas estejam vinculados antes da execução do servidor local, utilize os seguintes comandos:
   ```bash
   bunx --bun vite
   ```
   O terminal informará o endereço local ativo (ex: `http://localhost:5173`). Abra esta URL no seu navegador para interagir com o programa.

---

## 🛍️ Funcionamento e Fluxo de Uso Principal

A navegação e a interação com o **Remix Speranza** ocorrem de forma visual através dos componentes da interface de usuário:

1. **Navegação e Catálogo:** O usuário explora a página inicial de estilo editorial e entra na listagem de produtos. Os itens são exibidos em uma grade espaçada com fotografias focadas no design das peças.
2. **Interação na Página de Detalhes:** Ao selecionar um objeto, o usuário é direcionado para a página exclusiva do produto, onde encontra descrições focadas no processo de fabricação.
3. **Adicionar Itens à Sacola:** Ao clicar no botão para adicionar um produto à sacola:
   * **O que acontece na tela:** Uma notificação visual de sucesso surge na interface confirmando a inclusão do produto. A aplicação **não** abre painéis ou carrinhos laterais suspensos (*drawers*).
4. **Gerenciamento de Compras (Página da Sacola):** Para visualizar, alterar quantidades ou remover os itens selecionados, o usuário deve navegar até a **página dedicada à sacola de compras**.

### Persistência de Dados e Resultado Esperado
Os produtos adicionados, preferências do usuário e o estado atual da sacola de compras são **salvos e persistidos localmente no navegador**. Embora a estrutura de backend esteja mapeada, a validação imediata das ações da sacola ocorre localmente de forma assíncrona, garantindo que o usuário não perca seus dados ao atualizar a página ou fechar o navegador.
