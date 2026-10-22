# SITE Q'DELÍCIA

Site institucional da Q'Delícia Sorvetes (marca do Bruno, Passo Fundo/RS).

## No ar
- Produção: https://www.qdeliciasorvetes.com.br
- Hospedagem: Vercel, na conta da **agência** (benkeagenciadigital)

## Repositório oficial
- `benkeagenciadigital-tech/qdelicia-site` — branch **main**
- Esta pasta já está clonada e apontando pra ele.
- **Push na `main` publica no site** (deploy automático da Vercel, ~1 min).

## ATENÇÃO — repositório errado
Existe um `brunobenkedaronco-sketch/qdelicia-site`, **arquivado desde 30/07/2026**.
Ele NÃO alimenta o site. Foi onde o site nasceu; hoje é só histórico.
Se for mexer no site, é sempre o repositório da agência.

## Estrutura
Site estático, sem build, sem dependências. Tudo em arquivo único.

- `index.html` — a home inteira (CSS + JS embutidos, ~445 KB)
- `receitas.html` — página de receitas
- `Logo branca.png`, `img_*.png/jpg` — imagens locais
- `video_sorvete.mp4`, `video_maxi.mp4`, `video_sundae.mp4` — vídeos de fundo
  do slider da capa (~10s cada, já comprimidos pra web)

Todos os arquivos ficam na raiz, sem subpastas. Caminhos são relativos.
`Logo branca.png` tem maiúscula e espaço no nome — não renomear (Linux é
case-sensitive e quebra).

## Como editar
Editar `index.html` direto, no ponto específico. **Nunca substituir o arquivo
inteiro** por uma cópia antiga — o arquivo no repositório é sempre a verdade.

Pontos de referência dentro do `index.html`:
- Textos da capa → `<section class="hero">` / `slide-title`
- Empresa → seção `id="sobre"`
- Endereço, telefone, horário → seção `id="contato"` (cards `.contact-card`)
- Produtos e sabores → `const FLAVORS = { ... }` no `<script>` final
- WhatsApp → `wa.me/5554991493204`
- Tempo de troca dos vídeos → constante `FADE` (ms) no script

## Fotos dos produtos
As ~76 fotos de produto NÃO estão no repositório: carregam do Google Drive via
`https://lh3.googleusercontent.com/d/{ID}`. Funciona, mas é frágil (o Google
limita quando muitas carregam juntas, e mudança de permissão derruba todas).
Migrar pro servidor é melhoria pendente.

## Pendência aberta
- Migrar as fotos de produto do Google Drive pro repositório (ver acima).
- (Resolvido em 22/10/2026: a foto do sabor 3 Chocolates, `img_3chocolates.png`, foi adicionada.)

## Fluxo de trabalho
pasta local → commit → push na `main` → Vercel publica sozinha.
Não mexer em domínio, DNS ou configuração da Vercel.
