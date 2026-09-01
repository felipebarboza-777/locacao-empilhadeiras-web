# Architecture Design Document - LocaLift

## 1. Tecnologias Utilizadas
- **Linguagens:** HTML5, CSS3, JavaScript (ES6+ / Vanilla).
- **Framework CSS:** Bootstrap 5 (Sistema de Grid, Flexbox, tipografia e espaçamentos). *Nota: O framework será importado via CDN.*
- **Pré-processador:** Sass (SCSS) para modularização e organização do CSS personalizado.
- **Ferramentas de Qualidade:** ESLint e Prettier para padronização do código.
- **Gerenciamento de Pacotes:** NPM e Node.js.

## 2. APIs e Contratos
- **API Pública Real:** [ViaCEP](https://viacep.com.br/)
  - *Uso:* Requisição assíncrona (Fetch API) para buscar `logradouro`, `bairro`, `localidade` e `uf` a partir do CEP informado no formulário de cadastro.
- **API Fake (JSON Server):**
  - *Uso:* Simulação de backend operando localmente na porta 3000 (arquivo `db.json`).
  - *Entidades:* 
    - `/empilhadeiras` (GET): Retorna o array de máquinas para popular dinamicamente a página do catálogo (ID, modelo, capacidade de carga, imagem, valor da diária).
    - `/clientes` (POST): Recebe e salva os dados validados do formulário de locação.

## 3. Design Tokens (Guia Visual)
*Nota: Estes valores serão extraídos e validados durante a criação do protótipo no Figma/Stitch.*
- **Cores Principais:**
  - Primária (Destaque/Ação): Amarelo Industrial (`#FFC107` - remete a maquinário pesado e alertas).
  - Secundária (Texto principal/Navbar): Cinza Escuro quase preto (`#212529`).
  - Fundo (Background): Branco (`#FFFFFF`) e Cinza Claro (`#F8F9FA`) para alternância de seções.
- **Tipografia:** 
  - Títulos (Headings): `Montserrat` (Forte, geométrica, passa confiança).
  - Corpo de texto (Body): `Roboto` ou `Open Sans` (Foco em alta legibilidade).

## 4. Substituição de Componentes (Integração Bootstrap)
Os seguintes elementos serão desenhados no protótipo e posteriormente implementados no código utilizando os componentes prontos do Bootstrap 5:
1. **Navbar (Navegação):** Menu superior, responsivo, adotando o comportamento de "hamburger menu" (Offcanvas ou Collapse) em telas de dispositivos móveis.
2. **Cards:** Utilizados na página de "Catálogo" para encapsular a foto, título e as especificações de cada empilhadeira.
3. **Modal:** Janela sobreposta (Dialog) para exibir detalhes técnicos expandidos da máquina ou mensagens de confirmação de cadastro.
4. **Formulários (Forms):** Aplicação das classes `form-control` e `form-label` combinadas com o sistema de validação visual do Bootstrap (`is-invalid`, `is-valid`).
