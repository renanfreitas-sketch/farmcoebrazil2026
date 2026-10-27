# Cup of Excellence Brazil 2026 · Diretório de Fazendas

Site estático com os 40 lotes finalistas da Fase Nacional do COE Brazil 2026.
Endereço final: **https://coebrazil2026.bsca.com.br**

## Estrutura

```
index.html      página única (home + página de cada fazenda via #id-do-lote)
CNAME           domínio personalizado do GitHub Pages
.nojekyll       publica os arquivos como estão (sem processamento Jekyll)
brand/          logo 2026, aquarela, traços dourados, papel, ícone e imagem de compartilhamento (og.jpg)
sp/             logos de realização, promoção e patrocinadores (backdrop oficial)
img/fNN/        fotos de cada fazenda (NN.jpg = 1400 px; tNN.jpg = miniatura 560 px)
```

Os dados dos lotes (nomes, regiões, variedades, processos, altitudes, históricos PT/EN) estão no próprio `index.html`, na constante `DATA`.
Cada fazenda tem endereço próprio, ex.: `https://coebrazil2026.bsca.com.br/#fazenda-baoba-wet`.

## Publicar no GitHub Pages

1. Envie todo o conteúdo desta pasta para a raiz do repositório `BSCA-cafes/farmscoebrazil2026`, branch `main`
   (incluindo os arquivos ocultos `CNAME` e `.nojekyll`).
2. No GitHub: **Settings → Pages**
   - *Source*: **Deploy from a branch**
   - *Branch*: **main** / pasta **/ (root)** → **Save**
   - *Custom domain*: `coebrazil2026.bsca.com.br` (já vem preenchido pelo arquivo CNAME) → **Save**
3. No DNS do domínio **bsca.com.br** (painel de quem gerencia o DNS da BSCA), crie:

   | Tipo  | Nome / Host     | Valor / Destino          | TTL  |
   |-------|-----------------|--------------------------|------|
   | CNAME | `coebrazil2026` | `bsca-cafes.github.io.`  | 3600 |

4. Depois que o DNS propagar (de minutos a algumas horas), volte em **Settings → Pages** e marque **Enforce HTTPS**.

Recomendado: em **Organization settings → Pages → Verified domains**, verifique `bsca.com.br` (registro TXT indicado pelo GitHub) para impedir que outra conta use o subdomínio.

## Atualizar conteúdo

- **Textos e dados de um lote:** editar o objeto correspondente em `DATA` no `index.html`.
- **Pontuações (após 31/10):** o painel "Pontuação" de cada fazenda hoje mostra "Em avaliação"; basta enviar a lista de notas e classificação para preenchimento.
- **Fotos:** substituir `img/fNN/NN.jpg` e a miniatura `img/fNN/tNN.jpg` mantendo os nomes.
