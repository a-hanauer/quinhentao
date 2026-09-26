# Quinhentos

Um jogo diário de adivinhar palavras de 5 letras, em português brasileiro.

**Jogue:** https://a-hanauer.github.io/quinhentao/

A diferença para os jogos do gênero: o Quinhentos **não diz quais letras você acertou — só quantas**. Deduzir quais é problema seu.

Inspirado no [word500.com](https://word500.com).

---

## Como funciona

Você tem 8 tentativas para descobrir a palavra secreta do dia. Depois de cada palpite, três números aparecem ao lado da linha:

| Cor | Significado |
|---|---|
| 🟩 Verde | quantas letras estão na posição certa |
| 🟨 Amarelo | quantas letras existem na palavra, mas em outra posição |
| 🟥 Vermelho | quantas letras não existem na palavra |

Nenhuma ficha é colorida automaticamente. Cabe a você cruzar as informações entre as linhas e descobrir quais letras são quais.

### Pintar para raciocinar

Toque em qualquer letra de um palpite já enviado para marcá-la. Cada toque avança a cor: vermelho → amarelo → verde → neutro.

As marcações seguem duas regras que refletem a lógica do jogo:

- **Vermelho é absoluto.** Se uma letra não existe na palavra, ela não existe em lugar nenhum — marcar uma ocorrência pinta todas as outras, inclusive em palpites futuros, e a tecla correspondente no teclado.
- **Verde e amarelo são contextuais.** Dependem da posição, então a mesma letra pode ser verde numa linha e amarela em outra. Quando isso acontece, a tecla aparece dividida ao meio com as duas cores. E como você já sabe que essa letra existe na palavra, ela fica protegida: não vira vermelha em lugar nenhum.

O teclado ajuda sozinho: letras já usadas em algum palpite aparecem esmaecidas, para você enxergar rapidamente o que ainda não testou.

### Atalhos

- **Digitação fora de ordem** — toque em qualquer ficha da linha ativa para levar o cursor até ela. Dá para escrever a terceira letra antes da primeira.
- **Tab / Shift+Tab** ou **← →** navegam entre as fichas.
- Depois de digitar, o cursor pula para a próxima ficha **vazia**, o que torna fluido preencher buracos.
- Acentos e cedilha são aceitos: digitar `ç`, `á` ou `ã` equivale a `c`, `a` e `a`.

---

## Modos

- **Diário** — a mesma palavra para todo mundo, trocando à meia-noite. O progresso fica salvo e as estatísticas contam.
- **Jogo livre** — palavras aleatórias, quantas você quiser. Não conta para as estatísticas e sempre começa desligado ao abrir o site.

---

## Sobre o dicionário

São duas listas com papéis diferentes, e isso é proposital:

**Palpites aceitos (~5.500 palavras)** — o mais permissivo possível. Inclui plurais, conjugações verbais, feminino e masculino. Se a palavra existe em português, a ideia é que você consiga digitá-la.

**Candidatas a palavra do dia (~1.180 palavras)** — restrita de propósito, para o jogo ser sempre dedutível:

- apenas palavras comuns, no lema (singular / infinitivo)
- sem letras repetidas
- sem K, W ou Y

Tudo é armazenado sem acento e sem cedilha; a entrada do jogador é normalizada para essa forma.

A palavra do dia é sorteada por um hash da data — determinística (todo mundo joga a mesma), mas sem seguir a ordem da lista.

> O dicionário foi montado à mão e ainda tem lacunas. Se alguma palavra comum for recusada, [abra uma issue](../../issues) que eu adiciono.

---

## Rodando localmente

Não tem build, dependência nem servidor. É um único arquivo HTML:

```bash
git clone https://github.com/a-hanauer/quinhentao.git
cd quinhentao
# abra index.html no navegador, ou:
python3 -m http.server 8000
```

## Detalhes técnicos

- HTML, CSS e JavaScript puros em um arquivo só — sem framework, sem dependências
- Progresso e estatísticas no `localStorage` (nada sai do seu navegador)
- Tema claro/escuro automático, com opção manual
- Responsivo, funciona bem no celular e pode ser adicionado à tela de início

## Licença

MIT
