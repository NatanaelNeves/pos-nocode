# ⚽ Bolão Copa do Mundo 2026

Sistema web completo de bolão para a FIFA World Cup 2026, desenvolvido como projeto da disciplina de **No Code** do MBA Fullstack.

---

## Sobre o Projeto

Aplicação web single-page (SPA) em um único arquivo HTML com CSS e JavaScript embutidos, sem dependências externas ou backend. Todos os dados são persistidos localmente via `localStorage`.

## Funcionalidades

### Tela de Palpites
- Participante informa seu nome e os placares previstos para cada jogo
- Botão "Carregar" permite editar palpites já registrados pelo mesmo nome
- 16 jogos da fase de grupos distribuídos em 8 grupos (A–H)

### Tela de Resultados *(Administrador)*
- Registro dos placares reais de cada partida
- Indicador visual de jogos pendentes vs. já registrados

### Tela de Ranking
- Classificação em tempo real de todos os participantes
- Destaque de pódio para os três primeiros (ouro, prata, bronze)
- Detalhe expansível por participante: palpite × resultado × pontos de cada jogo
- **Área do Administrador** com botão de reset protegido por senha

### Regras de Pontuação

| Resultado | Pontos |
|---|---|
| Placar exato | 3 pts |
| Acertou o vencedor ou empate | 1 pt |
| Erro | 0 pts |

## Tecnologias

- **HTML5** — estrutura e marcação semântica
- **CSS3** — layout responsivo com Grid e Flexbox, glassmorphism, animações
- **JavaScript (ES6+)** — lógica de negócio, manipulação de DOM, `localStorage`
- **Nenhuma biblioteca externa** — zero dependências

## Como Usar

1. Baixe o arquivo `bolao-copa-2026.html`
2. Abra no navegador (duplo clique ou arraste para o browser)
3. Compartilhe o arquivo com os participantes — cada um abre localmente e registra seus palpites
4. O administrador registra os resultados reais na aba **Resultados** (senha padrão: `copa2026`)
5. O **Ranking** é atualizado automaticamente conforme os resultados são inseridos

> **Nota:** por usar `localStorage`, os dados ficam salvos apenas no navegador de cada participante. Para um bolão compartilhado, recomenda-se que o administrador consolide os palpites em uma única máquina.

## Senha do Administrador

A senha padrão é **`copa2026`**. Para alterá-la, edite a constante no arquivo:

```js
const SENHA_ADMIN = 'copa2026';
```

## Estrutura do Arquivo

```
bolao-copa-2026.html
├── <style>       — Todo o CSS (variáveis, layout, responsividade)
├── <body>        — Estrutura das 3 telas + header + navegação
└── <script>
    ├── JOGOS[]         — Dados dos 16 jogos da fase de grupos
    ├── LS              — Utilitário de localStorage
    ├── trocarTela()    — Navegação entre telas
    ├── renderJogosPalpites() / salvarPalpite()
    ├── renderResultados()    / salvarResultados()
    ├── renderRanking() / calcPontos()
    ├── toggleAdmin()   / resetarBolao()
    └── resultado() / trava() / esc() / toast()
```

---

## Informações Acadêmicas

| | |
|---|---|
| **Curso** | MBA Fullstack |
| **Disciplina** | No Code |
| **Aluno** | Natanael Neves |
| **Ferramenta** | [Claude Code](https://claude.ai/code) — CLI oficial da Anthropic |

---

*Desenvolvido com Claude Code · FIFA World Cup 2026 · USA · Canada · México*
