# Portfólio · Video Editor (Gaming)

Site de portfólio simples e leve: seu nome, quatro vídeos em grade 2x2 e seus contatos (Discord, Email e Twitter/X).
É só HTML, CSS e JavaScript puro. Não precisa instalar nada.

## Como ver o site

Dê dois cliques em `index.html`. Ele abre no navegador (Edge, Chrome, Firefox).

## O que editar (só o `config.js`)

Abra o `config.js` com o Bloco de Notas (ou VS Code) e mude:

| Campo | O que é |
|---|---|
| `name` | Seu nome, que aparece grande no topo |
| `tagline` | Linha pequena abaixo do nome |
| `contacts.discord` | Seu ID do Discord |
| `contacts.email` | Seu email |
| `contacts.twitter` | Seu usuário do Twitter/X (com ou sem `@`, ou o link completo) |
| `videos` | Os 4 vídeos, na ordem em que aparecem |

### Como adicionar um vídeo

**Do YouTube:** cole o link (ou só o ID) em `youtube`.

```js
{ title: "Clutch no último round", tag: "Highlights", youtube: "https://youtu.be/XXXXXXXXXXX" }
```

**Um arquivo seu (.mp4):** coloque o arquivo numa pasta `videos/` ao lado do `index.html` e use `file`.

```js
{ title: "Montagem", tag: "Montage", file: "videos/montagem.mp4", poster: "videos/montagem.jpg" }
```

`poster` é a imagem de capa (opcional para YouTube, recomendada para `.mp4`).
Se deixar `youtube` e `file` vazios, aparece um cartão "Seu vídeo aqui".

> Dica: para `.mp4` próprios, prefira vídeos curtos e comprimidos (H.264, até uns 20 MB).
> Para vídeos longos, o YouTube deixa o site bem mais leve.

## Como mudar as cores

No começo do `style.css` ficam as variáveis de cor (`--sky`, `--mid`, `--snow`, `--ink`, `--accent`).
O coral (`--accent`) é usado só no botão de play e nos contornos de foco, como o fone do pinguim.

## Por que o site é leve

- Os vídeos do YouTube só carregam quando você clica. Antes disso, aparece só a miniatura.
- O fundo é um degradê fixo com dois blobs desfocados, sem animação.
- Sem frameworks e sem bibliotecas externas. A fonte (Poppins) está na pasta `fonts/`.
- Animações mínimas (um leve movimento ao passar o mouse), que respeitam a opção "reduzir movimento" do sistema.

## Estrutura

```
index.html      estrutura da página
style.css       visual e cores
config.js       SEUS DADOS (nome, contatos, vídeos)
script.js       monta os vídeos e os contatos a partir do config.js
assets/         avatar (pinguim) e favicon
fonts/          fonte Poppins (licença OFL)
```

## Como publicar de graça

Qualquer um destes serve (arraste a pasta inteira do site):

- **Netlify Drop** (app.netlify.com/drop): arrasta a pasta e já ganha um link.
- **Cloudflare Pages** ou **GitHub Pages**: ótimos se você quiser um endereço fixo.

Depois de publicar, coloque o link na bio do seu Twitter/X.

## Observações

- Em telas bem estreitas (celular em pé) a grade passa para 1 coluna, para os vídeos não ficarem minúsculos.
  Em tablets e computadores, ela é sempre 2x2.
- Vídeos verticais (Shorts) aparecem com faixas nas laterais dentro do cartão 16:9.
- A fonte Poppins é licenciada sob a SIL Open Font License.
