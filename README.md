# 🏙️ Cidade Acessível

Jogo educativo infantil (5 a 11 anos, inclusive para quem ainda não lê) sobre uma cidade em que **todas as pessoas podem chegar, entrar, brincar e participar**.

A criança **observa → escolhe → experimenta → vê a consequência → reflete**. Não há prova, nem ranking, nem “resposta errada”.

**Criado por Leonardo Graciano**

---

## ✨ O que mudou nesta versão

- **Sem emoji**: todos os personagens, prédios, objetos e ícones agora são **imagens (SVG)** desenhadas em estilo flat, com traço e paleta consistentes.
- **Direção corrigida**: as artes foram desenhadas olhando para a **direita** e o jogo espelha o desenho (`scaleX`) conforme o sentido do movimento. Ninguém mais anda de trás para frente.
- **Caminhada fluida**: motor próprio em `requestAnimationFrame`, com posição interpolada por tempo (não por passos fixos), ciclo de 4 quadros (1‑2‑3‑2) e leve balanço do corpo.
- **Cidade viva automática**: basta **arrastar/colocar os ícones**. As pessoas aparecem sozinhas, caminham e vão até as peças que a criança colocou. O botão “Cidade viva” não existe mais.
- **Visual mais clean**: mais respiro, cantos arredondados, sombras suaves, paleta clara, botões grandes e tipografia maior.
- **Tela de carregamento** de 10 segundos, com a logo, barra de progresso, mini cidade animada e o crédito **Criado por Leonardo Graciano**.
- **Logo própria** (`assets/images/logo.svg`, `logomark.svg`, `favicon.svg`).

---

## ▶️ Como jogar

1. Escreva o nome (um adulto pode escrever) e toque em **COMEÇAR**.
2. **JOGAR** → mapa da cidade. Toque em um lugar (escola, ponto de ônibus, travessia, praça, saúde, comércio, parque, bairro).
3. Veja a cena, entenda a barreira e escolha uma solução entre 2‑3 opções.
   - Se não ajudar: “Hmm… será que isso ajuda? Vamos tentar outra opção.” e pode tentar de novo.
   - Se ajudar: a solução aparece na hora, o personagem consegue passar e **outras pessoas usam a mesma solução**.
4. **DETETIVE** → encontre o que atrapalha as pessoas nas cenas.
5. **CONSTRUIR** → monte a sua cidade livremente; ela fica viva sozinha.
6. **PRONTO** → tela final com a sua cidade e o botão **GUARDAR MINHA CIDADE** (gera um PNG no próprio aparelho).

---

## ♿ Acessibilidade

- Botões grandes, ícones e textos curtos; nada depende só de cor.
- Narração (Web Speech API) e botão 🔊 para ouvir de novo.
- Sons de descoberta, escolha, construção e recompensa; podem ser desligados.
- **Alto contraste** e **menos animação** em Ajustes (respeita `prefers-reduced-motion`).
- Funciona com mouse e toque, no computador, tablet e celular (melhor na horizontal).

---

## ⚡ Funciona com apenas 3 arquivos

As imagens ficam **embutidas dentro do `script.js`** (em formato data-URI). Ou seja:

- Para o jogo rodar bastam **`index.html`**, **`style.css`** e **`script.js`**.
- A pasta `assets/` é **opcional**: ela guarda os SVGs originais, para editar ou trocar as imagens.
- Existe também o **`cidade-acessivel-completo.html`**: um único arquivo com tudo dentro (HTML + CSS + JS + imagens). Dá para abrir com dois cliques ou mandar por WhatsApp.

> Se enviar tudo para o GitHub (recomendado), melhor ainda — mas se a pasta `assets` faltar, o jogo continua funcionando normalmente.

---

## 🗂️ Estrutura

```
cidade-acessivel/
├── index.html
├── style.css
├── script.js
├── assets/
│   ├── sprites.js        (cópia da biblioteca de imagens, opcional)
│   ├── images/           (personagens, prédios, objetos, barreiras, logo)
│   ├── icons/            (ícones de interface)
│   └── audio/            (livre para trilhas opcionais)
└── README.md
```

> As imagens usadas em tempo de execução estão no início do `script.js` (objeto `window.SPRITES`). Isso garante que o jogo funcione offline, em `file://` e no GitHub Pages, e permite gerar a imagem final no canvas sem bloqueio de segurança. Ao trocar um SVG em `assets/`, atualize também a entrada correspondente em `window.SPRITES`.

---

## 🖼️ Imagens e licença

Toda a arte deste jogo é **vetorial própria** (SVG gerado para o projeto), livre para uso, cópia e modificação — inclusive em GitHub Pages.

Se quiser substituir por outro acervo **gratuito**, estes bancos são compatíveis e recomendados:

| Banco | Licença | Bom para |
|---|---|---|
| [Kenney](https://kenney.nl/assets) | CC0 1.0 | cenários, prédios, city/platformer kits |
| [Open Peeps](https://www.openpeeps.com/) | CC0 | pessoas ilustradas |
| [Humaaans](https://www.humaaans.com/) | CC0 | pessoas montáveis |
| [SVG Repo](https://www.svgrepo.com/) | CC0 (seção Vectors) | ícones, cadeira de rodas, bengala |
| [unDraw](https://undraw.co/) | licença própria gratuita | cenas de apoio |
| [Iconoir](https://iconoir.com/) | MIT | ícones de interface |
| [Remix Icon](https://remixicon.com/) | Apache 2.0 | ícones de interface |

Para trocar: coloque o novo arquivo em `assets/images/` com o mesmo nome (ex.: `p-cadeira-1.svg`) e regenere/edite o `sprites.js`. Desenhe/exporte sempre a pessoa **olhando para a direita**, senão a virada fica invertida.

---

## 💾 Salvamento (LocalStorage)

Chave `cidade-acessivel-v1`: nome, estrelas, missões concluídas, barreiras encontradas, conquistas, peças desbloqueadas, cidade construída e ajustes de áudio/contraste.

---

## 🚀 Publicar no GitHub Pages

1. Crie um repositório (ex.: `cidade-acessivel`) e envie os arquivos. O mínimo é `index.html`, `style.css` e `script.js`; enviar a pasta `assets` e o README também é recomendado.
2. No repositório: **Settings → Pages**.
3. Em *Source*, escolha **Deploy from a branch**; em *Branch*, escolha `main` e a pasta `/ (root)`. Salve.
4. Em 1‑2 minutos o link aparece: `https://SEU-USUARIO.github.io/cidade-acessivel/`.

Não há servidor, backend nem instalação: é só HTML, CSS e JavaScript.

---

## 🛠️ Atalhos para o facilitador

Abra direto uma tela com `#qa=` (esses atalhos tambem pulam os 10s da tela de carregamento):

```
index.html#qa=menu     index.html#qa=map       index.html#qa=mission
index.html#qa=detective index.html#qa=build    index.html#qa=final
index.html#qa=achievements  index.html#qa=settings  index.html#qa=credits
```
