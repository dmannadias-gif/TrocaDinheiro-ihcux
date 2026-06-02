# 💰 TrocaDinheiro

> **Educação financeira em linguagem simples para quem mais precisa.**

<div align="center">

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=for-the-badge&logo=chartdotjs&logoColor=white)
![Netlify](https://img.shields.io/badge/Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white)

[![ODS 1](https://img.shields.io/badge/ODS%201-Erradica%C3%A7%C3%A3o%20da%20Pobreza-16a34a?style=for-the-badge)](https://brasil.un.org/pt-br/sdgs/1)
[![Status](https://img.shields.io/badge/Status-Em%20Produção-16a34a?style=for-the-badge)]()

</div>

---

## 📋 Índice

- [Sobre o Projeto](#-sobre-o-projeto)
- [ODS Vinculada](#-ods-vinculada)
- [Funcionalidades](#-funcionalidades)
- [Demonstração](#-demonstração)
- [Arquitetura do Projeto](#-arquitetura-do-projeto)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Como Executar](#-como-executar)
- [Estrutura de Arquivos](#-estrutura-de-arquivos)
- [Decisões de Design](#-decisões-de-design)
- [Heurísticas de Nielsen Aplicadas](#-heurísticas-de-nielsen-aplicadas)
- [Integrantes](#-integrantes)
- [Instituição](#-instituição)

---

## 📌 Sobre o Projeto

O **TrocaDinheiro** é uma aplicação web de educação financeira desenvolvida como projeto prático da disciplina de **Interação Humano Computador e UX** do Centro Universitário UNA.

O projeto parte de uma problemática real: **pessoas de baixa renda frequentemente tomam decisões financeiras prejudiciais não por falta de disciplina, mas por falta de informação acessível.** Ferramentas de educação financeira existentes foram projetadas para quem já tem estabilidade financeira — com linguagem técnica, exemplos distantes do cotidiano e interfaces que pressupõem renda estável e múltiplas contas bancárias.

O TrocaDinheiro ocupa um espaço que essas ferramentas deliberadamente ignoram: uma plataforma construída **do zero** pensando em quem vive com um salário mínimo, recebe Bolsa Família ou trabalha de forma informal — sem jargão, sem abstração, sem assumir que o usuário tem sobra no orçamento.

---

## 🌍 ODS Vinculada

<div align="center">

| ODS | Meta | Descrição |
|-----|------|-----------|
| **ODS 1 — Erradicação da Pobreza** | **Meta 1.4** | Garantir que todos os indivíduos tenham acesso a serviços financeiros básicos e a recursos econômicos |

</div>

A pobreza não é apenas ausência de renda — é também ausência de acesso à informação financeira de qualidade. O TrocaDinheiro endereça essa dimensão ao democratizar o letramento financeiro para quem mais precisa, reduzindo a desigualdade de conhecimento que perpetua a desigualdade econômica.

**Dados que justificam o projeto:**
- 🇧🇷 **62 milhões** de brasileiros vivem abaixo da linha da pobreza *(IBGE, 2023)*
- 💸 **70%+** das famílias brasileiras estão endividadas *(CNC, 2024)*
- 📉 **400% ao ano** é a taxa média de juros rotativos do cartão de crédito no Brasil
- 📊 O Brasil ocupa posições baixas nos rankings globais de educação financeira *(OCDE, 2023)*

---

## ✨ Funcionalidades

### 🚪 Login Personalizado
- Reconhece o usuário pelo nome na primeira visita
- Nas visitas seguintes, exibe saudação personalizada e resumo do progresso
- Não requer senha, e-mail ou cadastro
- Dados salvos localmente via `localStorage`

### 📋 5 Módulos de Conteúdo Temático
Cada módulo aborda uma situação real do cotidiano financeiro, com linguagem simples, exemplos baseados no salário mínimo vigente e dicas práticas aplicáveis imediatamente:

| Módulo | Tema |
|--------|------|
| 😓 Estou no vermelho | Como mapear dívidas e sair do negativo |
| 💳 Dívida no cartão | Como os juros rotativos funcionam |
| 🏦 Cheque especial | Como sair dessa armadilha |
| 🎁 O que fazer com o 13º | Calculadora com desconto real de INSS |
| 🐷 Quero guardar dinheiro | Como criar uma reserva do zero |

### 🧮 Calculadora de Orçamento
- Campos para renda e gastos principais (aluguel, alimentação, transporte, outros)
- Barra de progresso que conta campos preenchidos em tempo real
- Barras de categoria com percentual de cada gasto sobre a renda
- Gráfico de rosca interativo via Chart.js
- Dica personalizada com base no resultado
- Histórico de cálculos com data e hora, persistido no `localStorage`

### 🐷 Avatar Porquinho Reativo
- Desenhado inteiramente em SVG via código — sem imagem externa
- Reage ao saldo calculado em 3 estados:
  - 😊 **Feliz** — saldo positivo acima de 10% da renda
  - 😐 **Neutro** — saldo positivo, mas abaixo de 10% da renda
  - 😟 **Triste** — gastos superam a renda
- Animação suave de pulso contínuo
- Boca animada via atributo SVG `d` (caminho vetorial)

### 🎯 Calculadora do 13º Salário
- Cálculo proporcional aos meses trabalhados
- Desconto real de INSS baseado na tabela progressiva 2024
- Simulação de quitar dívidas com o valor líquido
- Exibe bruto, desconto e líquido separadamente

### 🏆 Sistema de Conquistas Progressivo
- Registra módulos concluídos no `localStorage`
- Barra de progresso geral (concluídos / total)
- Lista de módulos concluídos com numeração
- Próximos módulos disponíveis como cards clicáveis
- Card de parabéns ao concluir todos os módulos

---

## 🎬 Demonstração

🔗 **[Acessar o TrocaDinheiro ao vivo](https://trocadinheiro.netlify.app/)**

> Acesse pelo celular ou computador — sem instalar nada, sem criar conta.

---

## 🏗️ Arquitetura do Projeto

```
trocadinheiro/
│
├── bemvindo.html       ← Tela de boas-vindas e login simulado
├── index.html          ← Tela principal: cards, calculadora, porquinho e histórico
├── conteudo.html       ← Módulos de conteúdo (5 temas, dinâmico via URL)
├── conquistas.html     ← Progresso, módulos concluídos e próximos passos
└── style.css           ← Estilos globais e responsividade
```

### Fluxo de Navegação

```
bemvindo.html
     │
     ├── Primeiro acesso → digita o nome → salva no localStorage
     └── Retorno → exibe saudação e progresso
              │
              ▼
         index.html
              │
              ├── Cards de situação → conteudo.html?tema=XXXX
              │        │
              │        ├── passos com texto e dica
              │        ├── barra de progresso
              │        ├── calculadora do 13º (apenas tema=decimo)
              │        └── ao concluir → conquistas.html
              │
              └── Calculadora de orçamento
                       ├── porquinho SVG reativo
                       ├── gráfico de rosca (Chart.js)
                       ├── barras de categoria
                       └── histórico (localStorage)
```

### Como o conteudo.html funciona dinamicamente

O arquivo `conteudo.html` serve todos os 5 módulos a partir de um único arquivo HTML. O tema é passado via query string na URL:

```
conteudo.html?tema=vermelho
conteudo.html?tema=cartao
conteudo.html?tema=cheque
conteudo.html?tema=decimo
conteudo.html?tema=poupanca
```

O JavaScript lê o parâmetro com `URLSearchParams`, busca o conteúdo no objeto `temas` e preenche dinamicamente todos os elementos da tela.

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Versão | Uso |
|------------|--------|-----|
| HTML5 | — | Estrutura das 5 telas |
| CSS3 | — | Layout responsivo, animações e visual |
| JavaScript (ES6+) | — | Lógica, cálculos, navegação e localStorage |
| [Chart.js](https://www.chartjs.org/) | CDN | Gráfico de rosca interativo |
| [Google Fonts — Inter](https://fonts.google.com/specimen/Inter) | CDN | Tipografia |
| SVG | — | Avatar porquinho desenhado em código |
| localStorage | API nativa | Persistência de dados sem servidor |
| [Netlify](https://www.netlify.com/) | — | Deploy e hospedagem |

**Nenhuma dependência de servidor, banco de dados ou framework.** O projeto roda inteiramente no lado do cliente (front-end puro).

---

## 🚀 Como Executar

### Opção 1 — Acesso direto (recomendado)

Acesse pelo link do Netlify — nenhuma instalação necessária:

🔗 **[https://seu-link-netlify.netlify.app](https://trocadinheiro.netlify.app/)**

### Opção 2 — Rodar localmente

```bash
# 1. Clone o repositório
git clone https://github.com/seu-usuario/trocadinheiro.git

# 2. Acesse a pasta
cd trocadinheiro

# 3. Abra o arquivo de entrada no navegador
# No Windows: clique duas vezes em bemvindo.html
# No Mac/Linux:
open bemvindo.html
```

> ⚠️ **Importante:** abra sempre pelo `bemvindo.html`, não pelo `index.html` diretamente, para garantir o fluxo correto de login.

### Opção 3 — Extensão Live Server (VS Code)

1. Instale a extensão **Live Server** no VS Code
2. Clique com o botão direito em `bemvindo.html`
3. Selecione **"Open with Live Server"**

---

## 📁 Estrutura de Arquivos

### `bemvindo.html`
Tela de entrada com login simulado. Verifica se há nome salvo no `localStorage`:
- **Primeiro acesso:** exibe campo de nome com animações de entrada em sequência
- **Retorno:** exibe saudação personalizada e resumo do progresso de módulos

### `index.html`
Tela principal do aplicativo. Contém:
- Header fixo com logo e status de sistema
- Grid responsivo de 6 cards de situação (3 colunas no desktop, 1 no mobile)
- Calculadora de orçamento com barra de progresso, porquinho SVG, gráfico de rosca e barras de categoria
- Seção de histórico de cálculos com persistência

### `conteudo.html`
Arquivo único que serve todos os 5 módulos de conteúdo dinamicamente:
- Lê o tema da URL via `URLSearchParams`
- Navega entre passos com animação de slide
- Exibe calculadora do 13º embutida (exclusiva do tema `decimo`)
- Salva módulo como concluído ao completar o último passo

### `conquistas.html`
Tela de progresso do usuário:
- Barra de progresso geral (módulos concluídos / total)
- Lista de módulos concluídos com número e nome
- Cards de próximos módulos disponíveis para continuar
- Card de parabéns ao concluir todos os 5 módulos

### `style.css`
Estilos globais compartilhados entre todas as telas:
- Variáveis de cor e tipografia (fonte Inter via Google Fonts)
- Layout responsivo com breakpoints para tablet e mobile
- Animações: `fadeIn`, `slideIn`, `pulsePig`, `piscar`
- Componentes reutilizáveis: `.card`, `.btn-primary`, `.tip-box`, `.progress-fill`

---

## 🎨 Decisões de Design

### Paleta de cores
A paleta foi definida a partir do público-alvo e do propósito do app:

| Cor | Hex | Uso |
|-----|-----|-----|
| Verde principal | `#16a34a` | Cor de marca, botões, progresso |
| Verde escuro | `#15803d` | Hover, gradientes |
| Verde claro | `#dcfce7` | Fundos de destaque, dicas |
| Cinza fundo | `#f0f4f2` | Background das páginas |
| Preto suave | `#111827` | Textos principais |
| Cinza texto | `#6b7280` | Textos secundários |

O verde foi escolhido por transmitir crescimento, equilíbrio e esperança — valores centrais da proposta do app. O fundo levemente esverdeado cria harmonia com a marca sem pesar visualmente.

### Tipografia
Fonte **Inter** em todos os pesos (400, 500, 600, 700, 800). Escolhida por sua alta legibilidade em telas pequenas — fundamental para um app voltado a usuários com celulares modestos.

### Responsividade
- **Desktop (>900px):** grid de 3 colunas, calculadora em 2 colunas com gráfico ao lado
- **Tablet (560–900px):** grid de 2 colunas
- **Mobile (<560px):** coluna única, padding reduzido, header compacto

### Acessibilidade
- Alto contraste entre texto e fundo
- Botões com área de toque generosa (mínimo 44px de altura)
- Fontes legíveis (mínimo 12px, corpo em 14–15px)
- Placeholders descritivos em todos os campos
- Feedback visual imediato em todas as interações

---

## 🧠 Heurísticas de Nielsen Aplicadas

| # | Heurística | Aplicação no TrocaDinheiro |
|---|-----------|---------------------------|
| 1 | **Feedback do sistema** | Porquinho reage em tempo real · barras de progresso · gráfico atualiza a cada tecla |
| 2 | **Correspondência com o mundo real** | Situações como "Estou no vermelho" · valores do salário mínimo · linguagem do cotidiano |
| 3 | **Controle e liberdade do usuário** | Botão "Anterior" volta um passo sem perder progresso · "Limpar dados" · "Recomeçar do zero" |
| 4 | **Prevenção de erros** | Campos numéricos com placeholders · validação antes de salvar histórico · confirmação antes de resetar |
| 5 | **Design estético e minimalista** | Sem informações desnecessárias · hierarquia visual clara · paleta harmoniosa e consistente |
| 6 | **Reconhecimento em vez de memorização** | Cards com ícones e descrição · progresso sempre visível · nome do usuário reconhecido no retorno |

---

## 👥 Integrantes

| Nome | RA |
|------|-----|
| Anna Vitória Rocha Dias | 325118421 |
| Arthur Felipe Pereira | 325131390 |
| Fernando Ferreira de Oliveira | 325130289 |
| Gustavo Fernandes Rodrigues | 32516340 |
| Kate Santana Reis | 326129995 |

---

## 🏫 Instituição

**Centro Universitário UNA**
Disciplina: Interação Humano Computador e UX
Professor: Daniel Henrique Matos de Paiva
Semestre: 2026/1

---

<div align="center">

**[Acessar o TrocaDinheiro](https://trocadinheiro.netlify.app/)**

</div>
