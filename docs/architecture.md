# Architecture Design Document - LocaLift

## 1. Tecnologias Utilizadas

| Tecnologia / Biblioteca | Tipo / Fonte | Finalidade |
| :--- | :--- | :--- |
| **HTML5 / CSS3** | Nativo | Estrutura e estilização base |
| **JavaScript (ES6+)** | Nativo | Lógica do lado do cliente |
| **Bootstrap 5** | CDN | Framework CSS e componentes responsivos |
| **jQuery** | CDN | Manipulação do DOM e eventos |
| **jQuery Mask Plugin** | CDN | Máscaras de entrada (CEP, Telefone, CPF) |
| **ViaCEP API** | API Pública Real | Autocompletado de endereço via CEP |
| **JSON Server** | NPM (DevDependency) | API Fake local na porta 3000 para testes |
| **Sass (SCSS)** | NPM (DevDependency) | Pré-processador CSS para estilização |
| **Node.js / NPM** | Ambiente Local | Gerenciamento de pacotes e dependências |

## 2. APIs e Contratos
- **API Pública Real:** [ViaCEP](https://viacep.com.br/)
  - *Uso:* Requisição assíncrona (Fetch API) para buscar `logradouro`, `bairro`, `localidade` e `uf` a partir do CEP informado no formulário de cadastro.
- **API Fake (JSON Server):**
  - *Uso:* Simulação de backend operando localmente na porta 3000 (arquivo `db.json`).
  - *Entidades:* 
    - `/empilhadeiras` (GET): Retorna o array de máquinas para popular dinamicamente a página do catálogo.
    - `/clientes` (POST/GET): Gerencia os dados dos clientes.
    - `/locacoes` (POST/GET): Registra a relação entre o cliente e a empilhadeira alugada.

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

## 5. Modelo de Relacionamento (Banco de Dados)
O diagrama abaixo representa a estrutura de dados (entidades e relacionamentos) que será simulada através do JSON Server:

```mermaid
erDiagram
    CLIENTE ||--o{ LOCACAO : "realiza"
    EMPILHADEIRA ||--o{ LOCACAO : "é alugada em"

    CLIENTE {
        string id PK
        string nome
        string email
        string telefone
        string cep
        string logradouro
    }

    EMPILHADEIRA {
        string id PK
        string modelo
        float capacidade_kg
        float valor_diaria
        string status
    }

    LOCACAO {
        string id PK
        string cliente_id FK
        string empilhadeira_id FK
        string data_inicio
        string data_fim
        float valor_total
    }
