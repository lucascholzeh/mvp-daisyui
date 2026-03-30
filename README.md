# 🛸 Rick and Morty API Explorer

[![Netlify Status](https://api.netlify.com/api/v1/badges/93541a99-eba7-4a8d-8077-05e8f02eb941/deploy-status)](https://app.netlify.com/projects/mvp-daisyui-lucassc/deploys)
[![Vue 3](https://img.shields.io/badge/Vue.js-3.5+-4fc08d?style=for-the-badge&logo=vue.js&logoColor=white)](https://vuejs.org/)
[![Vite](https://img.shields.io/badge/Vite-6.0+-646cff?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4.0-38bdf8?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

Este é um projeto interativo que consome a [Rick and Morty API](https://rickandmortyapi.com/) para explorar o universo da série. Desenvolvido com foco em performance, código limpo e uma interface moderna utilizando o tema **Nord** do DaisyUI.

**🔗 [Acesse o Projeto Online](https://mvp-daisyui-lucassc.netlify.app/)**

---

## 🛠️ Tecnologias e Ferramentas

O projeto utiliza o que há de mais moderno no ecossistema Front-end:

* **Vue 3 (Composition API):** Utilização de `<script setup>` para uma lógica mais concisa e reativa.
* **Vite:** Build tool de última geração para um desenvolvimento ultra-rápido.
* **Tailwind CSS v4 & DaisyUI:** Estilização baseada em utilitários e componentes, aproveitando o novo motor de alto desempenho do Tailwind.
* **Axios:** Gerenciamento eficiente de requisições HTTP.
* **Vue Router:** Navegação entre páginas em uma Single Page Application (SPA).
* **DX (Developer Experience) Plugins:**
    * `unplugin-auto-import`: Automatiza a importação de APIs do Vue como `ref` e `computed`.
    * `unplugin-vue-components`: Realiza o auto-import de componentes da pasta `src/components`.

---

## ✨ Funcionalidades Principais

* **Listagem de Episódios:** Visualização organizada em cards responsivos.
* **Galeria de Personagens:** Cards que exibem avatares dos personagens com contagem dinâmica de extras.
* **Paginação Inteligente:** Navegação fluida através dos dados da API.
* **Detalhes via Modal:** Carregamento assíncrono de detalhes específicos de cada episódio.
* **SEO Otimizado:** Configuração completa de meta-tags, Open Graph e acessibilidade.
* **Design Responsivo:** Interface totalmente adaptada para todos os tamanhos de tela.

---

## 🚀 Como Rodar o Projeto Localmente

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/lucascholzeh/mvp-daisyui.git](https://github.com/lucascholzeh/mvp-daisyui.git)
    ```

2.  **Instale as dependências:**
    ```bash
    npm install
    ```

3.  **Inicie o servidor de desenvolvimento:**
    ```bash
    npm run dev
    ```

4.  **Acesse no navegador:** `http://localhost:5173`

---

## 🏗️ Estrutura do Projeto

A arquitetura foi organizada para facilitar a manutenção e escalabilidade:
* `src/components`: Componentes atômicos (Cards, Modais, Badges).
* `src/pages`: Views principais da aplicação (HomeView).
* `src/layouts`: Estrutura de layout padrão.
* `src/assets`: Estilização global e definição do tema Nord via variáveis `oklch`.

---

## 🎨 Tematização
O projeto utiliza o tema **Nord** customizado, configurado diretamente no CSS para garantir uma identidade visual consistente e moderna.

---

## 👨‍💻 Autor

**Lucas Scholze**
* LinkedIn: [Lucas Scholze Hoffmann](https://www.linkedin.com/in/lucas-scholze-hoffmann/)
* GitHub: [@lucascholzeh](https://github.com/lucascholzeh)

---
