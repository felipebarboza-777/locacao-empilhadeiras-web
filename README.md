# LocaLift - README

# 🚜 LocaLift - Sistema de Locação de Empilhadeiras

**Autor:** Felipe Barboza  
**Instituição:** UTFPR  
**Status:** 🟡 Em Desenvolvimento (Entrega 1)

---

## 📝 Descrição do Projeto
O **LocaLift** é uma aplicação web responsiva para a gestão e pré-reserva de locação de empilhadeiras. O sistema permite visualizar modelos de máquinas disponíveis, verificar especificações de carga, autocompletar endereços via CEP (API ViaCEP) e cadastrar solicitações de locação com persistência via JSON Server.

---

## 🔗 Links Úteis
* **Prototipação no Figma:** [Link para o Protótipo no Figma](https://figma.com/)
* **Design System & Arquitetura:** [docs/architecture.md](./docs/architecture.md)
* **Documentação de Requisitos (PRD):** [docs/prd.md](./docs/prd.md)
* **Aplicação em Produção (GitHub Pages):** [LocaLift no GitHub Pages](https://felipebarboza-777.github.io/locacao-empilhadeiras-web/)

---

## 🛠️ Tecnologias e Dependências

### Framework CSS
* **Bootstrap 5** (via CDN)

### Dependências JavaScript & Outras
* **jQuery** (Manipulação do DOM)
* **jQuery Mask Plugin** (Máscaras de formulário)
* **JSON Server** (API Fake backend)
* **Sass (SCSS)** (Estilização modular)
* **ESLint & Prettier** (Padronização e qualidade de código)

---

## 💻 Instruções de Execução (Local)

1. Clonar o repositório:
    ```bash
    git clone [https://github.com/felipebarboza-777/locacao-empilhadeiras-web.git](https://github.com/felipebarboza-777/locacao-empilhadeiras-web.git)
    cd locacao-empilhadeiras-web
    ```

2. Instalar as dependências do projeto:
    ```bash
    npm install
    ```

3. Iniciar o servidor fake (JSON Server):
    ```bash
    npx json-server --watch db/db.json --port 3000
    ```

4. Executar o projeto:
    * Abra o arquivo `index.html` no seu navegador (recomendado utilizar a extensão **Live Server** no VS Code).

---

## 🖼️ Telas da Aplicação

| Home / Apresentação | Catálogo | Formulário de Locação |
| :---: | :---: | :---: |
| ![Home](./src/assets/preview-home.png) | ![Catálogo](./src/assets/preview-catalogo.png) | ![Cadastro](./src/assets/preview-cadastro.png) |

---

## 📋 Checklist de Funcionalidades (RA / ID)

### RA1 - Utilizar Frameworks CSS para estilização de elementos HTML e criação de layouts responsivos
* [ ] **ID 01** - Prototipa interfaces adaptáveis para no mínimo os tamanhos de tela mobile e desktop, usando ferramentas de design tradicionais (Figma, Quant UX ou Sketch) ou IA (Stitch).
* [ ] **ID 02** - Implementa layout responsivo com Framework CSS (Bootstrap, Materialize) usando Flexbox ou Grid do próprio framework.
* [ ] **ID 03** - Implementa layout responsivo com CSS puro, usando Flexbox ou Grid Layout.
* [ ] **ID 04** - Utiliza componentes prontos de um Framework CSS (ex.: card, button) e componentes JavaScript do framework (ex.: modal, carousel).
* [ ] **ID 05** - Cria layout fluido usando unidades relativas (vw, vh, %, em, rem) no lugar de unidades fixas (px).
* [ ] **ID 06** - Aplica um Design System consistente (cores, tipografia, padrões de componentes) em toda a aplicação.
* [ ] **ID 07** - Utiliza Sass (SCSS) com ou sem framework, aplicando variáveis, mixins e funções para modularizar o código.
* [ ] **ID 08** - Aplica tipografia responsiva (media queries mobile first) ou tipografia fluida (função clamp() + unidades relativas).
* [ ] **ID 09** – Aplica técnicas de responsividade de imagens usando CSS (object-fit, containers com unidades relativas).
* [ ] **ID 10** – Otimiza imagens usando formatos modernos (WebP) e carregamento adaptativo (srcset, picture, ou parâmetros do Cloudinary).

### RA2 - Realizar tratamento de formulários e aplicar validações customizadas no lado cliente
* [ ] **ID 11** - Implementa validação HTML nativa (campos obrigatórios, tipos, limites de caracteres) com mensagens de erro/sucesso no lado cliente.
* [ ] **ID 12** - Aplica expressões regulares (REGEX) para validações customizadas (e-mail, telefone, datas, etc.).
* [ ] **ID 13** - Utiliza elementos de seleção em formulários (checkbox, radio, select) para coleta de dados.
* [ ] **ID 14** - Implementa leitura e escrita no Web Storage (localStorage/sessionStorage) para persistir dados localmente.

### RA3 - Aplicar ferramentas para otimização do processo de desenvolvimento web
* [x] **ID 15** - Configura ambiente com Node.js e NPM para gerenciamento de pacotes e dependências.
* [x] **ID 16** - Utiliza boas práticas de versionamento no Git/GitHub (branch main ou branches específicos, uso de .gitignore).
* [x] **ID 17** - Mantém um README.md padronizado, conforme template da disciplina, com checklist preenchido.
* [x] **ID 18** - Organiza arquivos do projeto de forma modular, seguindo padrão de exemplo fornecido.
* [x] **ID 19** - Configura linters e formatadores (ESLint, Prettier) para manter qualidade e padronização do código.

### RA4 - Aplicar bibliotecas de funções e componentes em JavaScript para aprimorar a interatividade de páginas web
* [ ] **ID 20** - Utiliza jQuery para manipulação do DOM e interatividade (eventos, animações, manipulação de elementos).
* [ ] **ID 21** - Integra e configura um plugin jQuery relevante (ex.: jQuery Mask Plugin) ou outra biblioteca de funções.

### RA5 - Efetuar requisições assíncronas para uma API fake e APIs públicas, permitindo a obtenção e manipulação de dados dinamicamente
* [ ] **ID 22** - Realiza requisições assíncronas para uma API fake (ex.: JSON Server) para persistir dados de um formulário.
* [ ] **ID 23** - Realiza requisições assíncronas para uma API fake para exibir dados na página.
* [ ] **ID 24** - Realiza requisições assíncronas para APIs públicas reais (ViaCEP), exibindo os dados e tratando erros.
