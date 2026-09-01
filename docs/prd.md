# Product Requirements Document (PRD) - LocaLift

## 1. Escopo e Propósito
O **LocaLift** é uma aplicação web responsiva voltada para a locação de empilhadeiras. O sistema permite que os clientes visualizem um catálogo de equipamentos disponíveis, com suas especificações técnicas, e realizem um cadastro para solicitar a locação. 

## 2. Público-Alvo
Gerentes de logística, donos de armazéns, indústrias e organizadores de eventos que necessitam alugar maquinário de movimentação de carga de forma rápida e intuitiva.

## 3. Estrutura de Páginas (Mínimo de 3)
1. **Página Inicial (Home):** Apresentação da empresa, diferenciais e chamadas para ação.
2. **Catálogo de Equipamentos:** Listagem das empilhadeiras disponíveis (consumindo dados da API fake).
3. **Cadastro/Locação:** Formulário para o cliente registrar seus dados e solicitar o equipamento.

## 4. User Stories (Histórias de Usuário)
- **Como cliente**, quero visualizar um catálogo de empilhadeiras em formato de *cards* para escolher a máquina com a capacidade de carga ideal.
- **Como cliente**, quero digitar meu CEP no formulário de cadastro para que o sistema preencha meu endereço automaticamente, poupando meu tempo.
- **Como administrador**, preciso que o sistema valide os dados do formulário (e-mail, telefone) antes do envio, para evitar contatos inválidos.

## 5. Regras de Negócio e Requisitos
- O formulário deve conter campos obrigatórios e validação via Regex (Expressões Regulares) usando JavaScript.
- Os dados temporários do formulário devem ser salvos no `localStorage` antes do envio.
- A aplicação deve ser totalmente responsiva (Mobile-First).
