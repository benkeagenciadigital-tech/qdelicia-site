# Contexto — sessão de 22/10/2026 (chat → Code)

Resumo do que foi feito e decidido no chat do Claude, para continuar daqui.

## O que foi publicado hoje

Commit `59a280c` na `main` do repositório da agência:
**Canal de Denúncias** incluído em dois pontos do `index.html`
- link no rodapé (classe `.footer-link`, ao lado do botão do WhatsApp)
- card na seção Contato, depois do card "Horário"
- URL: https://guedesflow.com/denuncias/qdelicia, abre em nova aba
- CSS da `.footer-link` e `.footer-links` adicionado após `.footer-wa:hover`

Já verificado no ar em www.qdeliciasorvetes.com.br — funcionando.

## A confusão que custou a tarde (não repetir)

Passamos horas tentando publicar no repositório errado.

- `brunobenkedaronco-sketch/qdelicia-site` → **arquivado em 30/07/2026**, read-only.
  Foi onde o site nasceu. NÃO é o site. Só histórico.
- `benkeagenciadigital-tech/qdelicia-site` → **é este, o oficial**, conectado à
  Vercel que serve o domínio. É o `origin` desta pasta.

Sintomas de estar no repositório errado: push dá 403, e o GitHub mostra
"Propose changes" em vez de "Commit changes".

## Contas

- GitHub do Bruno: `brunobenkedaronco-sketch` (já é colaborador no repo oficial)
- GitHub da agência: `benkeagenciadigital-tech` (dona do repo)
- A Vercel que serve o domínio é da **agência**, não do Bruno. Ele não tem
  acesso e não precisa — o deploy é automático via push.

## Histórico do site (construído no chat, jun–jul/2026)

- Capa com slider de 3 vídeos de fundo (~10s cada), crossfade de 1.5s
  controlado pela constante `FADE` no script
- Os vídeos foram comprimidos de ~66 MB para ~6,6 MB no total
- Foram testados dois layouts alternativos (v2 vitrine de picolés, v3
  cinematográfico) — **ambos reprovados**. O layout aprovado é o atual.
- Preferência estética do Bruno: moderno, escuro, premium. Rejeita vintage
  e qualquer coisa com cara de template.

## Pendências abertas

1. ~~Foto do sabor "3 Chocolates"~~ — resolvida em 22/10/2026 (`img_3chocolates.png`, commit `a7019f1`).
2. **Fotos dos produtos no Google Drive** — ~76 fotos carregam de
   `lh3.googleusercontent.com`. Funciona, mas é frágil. Migrar para o
   repositório é melhoria recomendada, ainda não feita.

## Como o Bruno trabalha

Direto e objetivo. Quer a coisa pronta, não um leque de opções. Revisa pelo
celular. Não é programador: explicar em português claro, sem jargão, e dar o
passo a passo quando envolver terminal.
