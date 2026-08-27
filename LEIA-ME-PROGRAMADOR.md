# Q'Delícia Sorvetes — pacote do site (versão aprovada)

Site estático (HTML + CSS + JS em arquivo único). **Não precisa de build, Node, banco de dados nem servidor especial.** É só subir os arquivos numa pasta e apontar o domínio.

---

## 1. Arquivos do pacote

| Arquivo | O que é |
|---|---|
| `index.html` | A página principal do site — versão aprovada |
| `receitas.html` | Página de receitas (Torta Holandesa, Affogato, Cestinha de Churros) |
| `img_hero_receitas.jpg` | Imagem de capa da página de receitas |
| `img_receita_torta_holandesa.png`, `img_receita_affogato.png`, `img_receita_churros.png` | Fotos das receitas |
| `Logo branca.png` | Logo usada no menu e no rodapé |
| `img_morango.png` | Imagem da linha Frutas |
| `img_napolitano_zero.png` | Imagem da linha Zero Açúcar |
| `video_sorvete.mp4` | Vídeo de fundo 1 (~10s, 1,5 MB) |
| `video_maxi.mp4` | Vídeo de fundo 2 (~10s, 2,1 MB) |
| `video_sundae.mp4` | Vídeo de fundo 3 (~12s, 3,0 MB) |

**Importante:** os arquivos devem ficar **todos na mesma pasta**, sem subpastas. Os caminhos são relativos (`src="video_maxi.mp4"`), então mudar a estrutura quebra imagens e vídeos.

O nome `Logo branca.png` tem **letra maiúscula e espaço**. Em servidor Linux isso é case-sensitive — manter exatamente assim.

---

## 2. Como publicar

1. Subir os arquivos via FTP/painel para a pasta pública (`public_html`, `www`, `htdocs`...)
2. Manter o nome `index.html`
3. Pronto — o domínio já serve a página

Recomendado no servidor: **HTTPS ativo** e **compressão gzip/brotli** para o HTML.

---

## 3. ⚠️ Pontos de atenção

### 3.1 — As fotos dos produtos vêm do Google Drive
As fotos de produtos (categorias e sabores) **não estão neste pacote**. Elas carregam direto do Google Drive:

```
https://lh3.googleusercontent.com/d/{ID_DO_ARQUIVO}
```

Funciona, mas tem risco: o Google **limita o carregamento** quando muitas imagens são pedidas de uma vez (algumas podem não aparecer), e uma mudança de permissão na conta derruba todas.

**Recomendação para o site oficial:** baixar essas imagens e hospedar no próprio servidor, trocando as URLs. No código, os IDs ficam no bloco `const FLAVORS = { ... }` (campo `img:`) e nas tags `<img>` da seção de produtos.

### 3.2 — 1 imagem ainda pendente
Um sabor aponta para um arquivo que não existe:

- `img_3chocolates.png` → sabor **3 Chocolates** (linha Especiais 2L)

Basta colocar a foto na pasta com **esse nome exato** e passa a funcionar. (As outras 3 que estavam quebradas — Sundae Zero, Açaí Zero e Picolé Coco Zero — já foram corrigidas nesta versão.)

### 3.3 — Fontes
Vêm do Google Fonts (`fonts.googleapis.com`). Se quiser 100% local, baixar as fontes e trocar o `<link>`.

### 3.4 — Vídeos de fundo
Rodam em autoplay, **mudos** e com `playsinline` (obrigatório para tocar sozinho no celular). Não remover esses atributos. Já estão comprimidos para web (de ~66 MB para ~6,6 MB no total).

---

## 4. Onde mexer no conteúdo

Tudo dentro do próprio `index.html`:

- **Textos da capa** → bloco `<section class="hero">` / `slide-title`
- **Textos da empresa** → seção `id="sobre"`
- **Endereço, telefone e horário** → seção `id="contato"`
- **Produtos e sabores** → bloco `const FLAVORS = { ... }` no `<script>` no final
- **WhatsApp** → buscar por `wa.me/5554991493204`
- **Tempo de troca dos vídeos de fundo** → constante `FADE` no script (milissegundos)

---

## 5. Referência online

Versão publicada para comparação: https://qdelicia-site.vercel.app
Código-fonte oficial: https://github.com/benkeagenciadigital-tech/qdelicia-site
