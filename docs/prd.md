# Product Requirements Document (PRD) - LocaLift

## 1. Escopo e Propósito
O **LocaLift** é uma aplicação web responsiva voltada para a locação de empilhadeiras. O sistema permite que os clientes visualizem um catálogo de equipamentos disponíveis, com suas especificações técnicas, e realizem um pré-cadastro para solicitar a locação. 

## 2. Público-Alvo
Gerentes de logística, donos de armazéns, indústrias e organizadores de eventos que necessitam alugar maquinário de movimentação de carga de forma rápida e intuitiva.

## 3. Estrutura de Páginas (Mínimo de 3)
1. **Página Inicial (Home):** Apresentação da empresa, diferenciais e chamadas para ação.
2. **Catálogo de Equipamentos:** Listagem das empilhadeiras disponíveis (consumindo dados da API fake).
3. **Cadastro/Locação:** Formulário para o cliente registrar seus dados e solicitar o equipamento.

## 4. User Stories e Critérios de Aceitação

### US01 - Visualização do Catálogo
**História:** Como cliente, quero visualizar um catálogo de empilhadeiras em formato de *cards* para escolher a máquina com a capacidade de carga ideal.
**Critérios de Aceitação:**
- O sistema deve exibir as máquinas consumindo os dados de uma API Fake (JSON Server).
- Cada card de empilhadeira deve exibir obrigatoriamente: Imagem, Modelo, Capacidade de Carga (kg) e Valor da Diária.
- O layout dos cards deve ser responsivo (empilhados no mobile e lado a lado no desktop) utilizando o sistema de grid do Bootstrap.

### US02 - Autocompletar Endereço por CEP
**História:** Como cliente, quero digitar meu CEP no formulário de cadastro para que o sistema preencha meu endereço automaticamente, poupando meu tempo.
**Critérios de Aceitação:**
- Ao digitar um CEP válido (8 dígitos), o sistema deve fazer uma requisição assíncrona (Fetch) para a API pública ViaCEP.
- Os campos Logradouro, Bairro, Cidade e Estado devem ser preenchidos automaticamente na tela.
- Se o CEP for inválido ou não encontrado, o sistema deve exibir uma mensagem de erro clara abaixo do campo.

### US03 - Validação e Submissão de Cadastro
**História:** Como administrador, preciso que o sistema valide os dados do formulário antes do envio, garantindo que a base de dados não receba contatos inválidos.
**Critérios de Aceitação:**
- Os campos Nome, E-mail, Telefone e CEP são de preenchimento obrigatório.
- O e-mail e o telefone devem ser validados utilizando Expressões Regulares (Regex) via JavaScript.
- Em caso de erro de validação, o campo deve receber um destaque visual (ex: borda vermelha) e uma mensagem de erro.
- Ao clicar em enviar com os dados corretos, as informações devem ser armazenadas no `localStorage` antes de enviar o POST para a API Fake.

## 5. Regras de Negócio Gerais
- A aplicação deve seguir a abordagem *Mobile-First*.
- Todo o feedback visual de erro ou sucesso deve utilizar os componentes e classes do framework CSS escolhido (Bootstrap 5).
