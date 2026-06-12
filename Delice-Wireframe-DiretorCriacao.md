# WIREFRAME — DIRETOR DE CRIAÇÃO
## Delicê Confeitaria Gourmet · Byanca Costa · Barra Mansa, RJ
**Etapa 3 do pipeline · alimenta pagina-vendas-04-lovable**

---

## FRASE-NORTE (filtro de toda decisão visual)

> "Essa página precisa fazer a mulher que organiza um momento especial — e tem medo de errar na escolha — sentir que a Delicê é a única confeitaria que vai tratar o SEU evento como se fosse o único que existe — porque cada dobra mostra cuidado artesanal real, não promessa genérica."

**Decisão de luz global:** quente artificial — luz de vela difusa, sombras suaves em bordô, highlights dourados. Aplica-se a TODAS as imagens da página sem exceção.

---

## DOBRA 0 — BARRA TOPO (Topbar)

```
══════════════════════════════════════════════════════
OBJETIVO NA JORNADA:
  Reduzir fricção imediata. Sinalizar disponibilidade antes
  de qualquer argumento. Criar âncora de conversão persistente.

COMPOSIÇÃO:
  Onde o olho entra: texto dourado "Encomendar via WhatsApp →"
  Percurso: leitura linear esquerda → direita
  Ponto de chegada: link/botão dourado à direita
  Espaço para texto: centralizado, linha única

LAYOUT DESKTOP:
  ┌─────────────────────────────────────────────────────┐
  │  [BURGUNDY FIXO · z-index 100 · height: 40px]      │
  │  ✦ Encomendas abertas · Barra Mansa, RJ             │
  │                   Encomendar via WhatsApp →         │
  └─────────────────────────────────────────────────────┘
  position: fixed / top: 0 / padding: 0 48px

LAYOUT MOBILE:
  Texto reduzido: "Encomendas abertas · WhatsApp →"
  Font-size: 11px / padding: 8px 20px

BACKGROUND:
  Cor: #6B1A2A
  Efeito: sólido
  Grain: não

IMAGENS: nenhuma

ÍCONES:
  ✦ ornamento inline (SVG pequeno, 8px, gold) antes do texto
  Seta → inline em texto

ANIMAÇÃO: nenhuma

CTA: "Encomendar via WhatsApp →"
  href: https://wa.me/5524993121791
  cor: #B8924A / hover: underline

PESO: levíssimo — texto puro
══════════════════════════════════════════════════════
```

---

## DOBRA 1 — HERO

```
══════════════════════════════════════════════════════
OBJETIVO NA JORNADA:
  Criar desejo imediato. Responder "estou no lugar certo?" em 3 segundos.
  A persona chega do Instagram — já sabe que é confeitaria — precisa
  sentir que ESSA confeitaria é diferente, que entende o que ela sente.

HEADLINE DESTA DOBRA:
  "Cada encomenda é única — como o momento que ela celebra."

COMPOSIÇÃO COMO NARRATIVA:
  Onde o olho entra: headline em Cormorant Italic — contraste máximo
                     sobre overlay burgundy
  Percurso: badge (acima) → headline → subtítulo → botões
  Ponto de chegada: botão primário gold "Quero encomendar →"
  Espaço para texto: centro, coluna única, max-width 720px

LAYOUT DESKTOP:
  ┌──────────────────────────────────────────────────────────┐
  │  [IMAGEM FULL-WIDTH com overlay rgba(107,26,42,0.55)]    │
  │  min-height: 100vh / display: flex / align: center       │
  │                                                          │
  │         ✦ Confeitaria Artesanal · Barra Mansa ✦         │
  │    [badge outline cream, Cormorant SC, 11px, margin-b]   │
  │                                                          │
  │    Cada encomenda é única —                              │
  │    como o momento que ela celebra.                       │
  │    [Cormorant Garamond Italic 300 / clamp(52,6vw,80px)]  │
  │                                                          │
  │    Doces criados com técnica, afeto e identidade —       │
  │    para os momentos que merecem ser lembrados.           │
  │    [body 17px / cream / max-width 560px / mx-auto]       │
  │                                                          │
  │    [QUERO ENCOMENDAR →]    [Ver catálogo]                │
  │    [btn-primary gold]      [btn-ghost--light]            │
  │                                                          │
  │  ✦ ornamento flutuante canto sup-dir (opacity 0.15)      │
  │  ✦ ornamento flutuante canto inf-esq (opacity 0.12)      │
  └──────────────────────────────────────────────────────────┘
  Container: 1160px / Padding vertical: 0 (min-height 100vh)

LAYOUT MOBILE:
  Mantém estrutura centralizada / headline: clamp(36px,8vw,52px)
  Botões empilhados verticalmente / ornamentos reduzidos (opacity 0.10)

BACKGROUND:
  Cor base: foto hero-bolo-atm.jpg (full-width, object-fit: cover)
  Overlay: linear-gradient(rgba(107,26,42,0.45) 0%, rgba(107,26,42,0.65) 100%)
  Grain: sim — 3% opacity (leve, sobre a foto)
  Ornamentos flutuantes: 2x SVG floral dourado, float-ornamento 6s

IMAGENS DESTA DOBRA:
  Total: 1 imagem (background)

  IMAGEM 1:
    Nome do arquivo: hero-bolo-atmosfera.jpg
    Tipo: 07 — Contexto / Atmosfera
    Função: criar desejo aspiracional antes de qualquer argumento racional.
             A imagem não vende o bolo — vende o sentimento de ter acertado
             na escolha.
    Posição: fundo full-width, object-fit: cover, object-position: center
    Proporção: 16:9 (1440×900px mínimo)
    Tratamento: foto pura + overlay duplo (burgundy gradiente)
    Agrupamento: isolada (background da seção inteira)
    Decisão de luz: vela difusa, sombras quentes em bordô/sépia, não flash
    Mobile: mantém / object-position: center 40%

ÍCONES:
  ✦ ornamento SVG floral (inline, não Iconify) — decorativo
  → seta inline nos botões

ANIMAÇÃO:
  Ornamentos: float-ornamento 6s ease-in-out infinite
  Conteúdo: fade-in on load (opacity 0→1, translateY 16px→0, 800ms)
  Scroll indicator: pulse suave na base (opcional)

CTA:
  Primário: "Quero encomendar →" → wa.me/5524993121791
  Secundário: "Ver catálogo" → âncora #catalogo

PESO: imagem hero é o maior asset — comprimir para <300KB, usar WebP

ALERTA CSS:
  Hero usa layout single-column full-width → h1 global clamp(52px,6vw,80px)
  está correto aqui. NÃO é split — não precisa override.
══════════════════════════════════════════════════════
```

---

## DOBRA 2 — TENSÃO / FRASE DE IMPACTO

```
══════════════════════════════════════════════════════
OBJETIVO NA JORNADA:
  Nomear a dor sem ser negativo. Criar identificação imediata.
  A persona deve pensar "é exatamente isso que eu sinto".
  Esta dobra é o espelho — ela se vê aqui.

HEADLINE DESTA DOBRA:
  "Você já comprou um bolo que veio errado. Que veio seco.
   Que não ficou nem de perto o que você imaginou."

COMPOSIÇÃO COMO NARRATIVA:
  Onde o olho entra: linha ornamental gold no topo — quebra visual
                     depois do hero escuro
  Percurso: ornamento → headline tensão → frase virada → label gold
  Ponto de chegada: label "O padrão Delicê" em Cormorant SC gold
  Espaço para texto: coluna única, max-width 760px, centralizado

LAYOUT DESKTOP:
  ┌──────────────────────────────────────────────────────────┐
  │  [BURGUNDY · grain ativo]                                │
  │  padding: 100px 0                                        │
  │                                                          │
  │         ─────── ✦ ───────                               │
  │         [divisória ornamental gold, SVG central]         │
  │                                                          │
  │    Você já comprou um bolo que veio errado.              │
  │    Que veio seco. Que não ficou nem de perto             │
  │    o que você imaginou.                                  │
  │    [Cormorant Garamond Italic 300 / 48px / cream]        │
  │    [max-width: 760px / text-align: center / mx-auto]     │
  │                                                          │
  │    Na Delicê, isso não acontece.                         │
  │    [Cormorant Garamond Italic 300 / 40px / gold-light]   │
  │    [margin-top: 32px]                                    │
  │                                                          │
  │         ─────── ✦ ───────                               │
  │         [divisória ornamental gold]                      │
  │                                                          │
  │    O PADRÃO DELICÊ                                       │
  │    [Cormorant SC 700 / 13px / gold / letter-spacing .1]  │
  └──────────────────────────────────────────────────────────┘
  Container: 760px (narrower — força leitura vertical confortável)

LAYOUT MOBILE:
  headline: clamp(28px,6vw,40px) / padding: 64px 24px

BACKGROUND:
  Cor: #6B1A2A
  Efeito: sólido
  Grain: sim — 4% opacity
  Grafismo: nenhum (textura só via grain)

IMAGENS DESTA DOBRA:
  Total: 0 — dobra intencionalmente sem imagem
  (a ausência de imagem cria respiro dramático — a dor fica nua)

ÍCONES:
  ✦ ornamento SVG (divisória, não Iconify)

ANIMAÇÃO:
  Reveal scroll: fade-up 700ms, ease-elegant
  Headline tensão: stagger de 2 blocos (delay 100ms entre linhas)

CTA: nenhum

PESO: levíssimo — texto e grain
══════════════════════════════════════════════════════
```

---

## DOBRA 3 — SOBRE BYANCA (Autoridade + Conexão)

```
══════════════════════════════════════════════════════
OBJETIVO NA JORNADA:
  Criar conexão humana. A persona precisa sentir que conhece a Byanca
  antes de encomendar. Esta dobra transforma "confeitaria" em "pessoa
  que vai cuidar do meu momento". É a dobra de confiança.

HEADLINE DESTA DOBRA:
  "Byanca Costa"

COMPOSIÇÃO COMO NARRATIVA:
  Onde o olho entra: foto retrato (lado esquerdo) — face humana
                     domina atenção involuntária
  Percurso: foto → badge (direita) → nome → bio → frase destaque
  Ponto de chegada: frase em itálico gold + botão ghost
  Espaço para texto: coluna direita (~50% largura)

LAYOUT DESKTOP:
  ┌──────────────────────────────────────────────────────────┐
  │  [CREAM] padding: 100px 0                                │
  │  Container: 1160px                                       │
  │                                                          │
  │  ┌────────────────┐  ┌────────────────────────────────┐  │
  │  │                │  │  ✦ Quem está por trás          │  │
  │  │  byanca-       │  │    da Delicê                   │  │
  │  │  retrato.jpg   │  │  [badge gold outline]          │  │
  │  │                │  │                                │  │
  │  │  600×750px     │  │  Byanca Costa                  │  │
  │  │  portrait      │  │  [H2 Italic / 56px / dark]     │  │
  │  │  border-radius │  │                                │  │
  │  │  16px          │  │  [bio 2–3 parágrafos]          │  │
  │  │  shadow-card   │  │  [body 17px / text-dark]       │  │
  │  │                │  │                                │  │
  │  │                │  │  "X anos transformando         │  │
  │  │                │  │   ingredientes em memórias"    │  │
  │  │                │  │  [Italic / 22px / gold]        │  │
  │  │                │  │                                │  │
  │  │                │  │  [Conheça minha história →]    │  │
  │  │                │  │  [btn-ghost]                   │  │
  │  └────────────────┘  └────────────────────────────────┘  │
  │  grid-template-columns: 480px 1fr / gap: 64px            │
  └──────────────────────────────────────────────────────────┘

LAYOUT MOBILE:
  Empilhamento: foto acima (aspect-ratio: 4/3, não portrait)
  border-radius: 12px / texto abaixo

BACKGROUND:
  Cor: #F5EDE4
  Efeito: sólido
  Grain: não
  Grafismo: nenhum

IMAGENS DESTA DOBRA:
  Total: 1

  IMAGEM 1:
    Nome do arquivo: byanca-retrato.jpg
    Tipo: 01 — Especialista / Autoridade
    Função: transferir credibilidade humana. Fazer a persona sentir que
             conhece Byanca antes de falar com ela. Foto de pessoa = 
             confiança antes de qualquer argumento.
    Posição: coluna esquerda, ~41% da largura do container
    Proporção: 4:5 (retrato vertical — 480×600px renderizado)
    Tratamento: foto pura, sem overlay
    Agrupamento: isolada, border-radius 16px, shadow-card
    Decisão de luz: luz natural de janela lateral, quente. Sombras suaves.
                    NÃO flash frontal, NÃO fundo branco neutro puro.
    Se fundo de estúdio neutro (cinza/branco):
      filter: brightness(.82) contrast(1.05)
      overlay em camadas:
        linear-gradient(to right, #F5EDE4 0%, rgba(245,237,228,.55) 45%,
                         rgba(245,237,228,.15) 70%, transparent 100%)
        + linear-gradient(to top, #F5EDE4 0%, transparent 28%)
        + linear-gradient(to bottom, rgba(245,237,228,.4) 0%, transparent 20%)
    Mobile: empilha acima, aspect-ratio: 4/3

ÍCONES: nenhum

ANIMAÇÃO:
  Reveal scroll: fade-up dobra inteira / 700ms / ease-elegant
  Foto: slide-in da esquerda (translateX -24px → 0 / delay 100ms)
  Texto: slide-in da direita (translateX 24px → 0 / delay 200ms)

CTA:
  "Conheça minha história →" — btn-ghost, âncora para seção história
  (se não houver página separada, pode ser removido)

PESO: imagem retrato — comprimir para <200KB, WebP
══════════════════════════════════════════════════════
```

---

## DOBRA 4 — DIFERENCIAIS

```
══════════════════════════════════════════════════════
OBJETIVO NA JORNADA:
  Provar a promessa do hero com argumentos concretos.
  A persona saiu do "quero acreditar" e entra no "entendo por que
  ela é diferente". Cada diferencial destrói uma objeção silenciosa.

HEADLINE DESTA DOBRA:
  "O que faz cada Delicê ser única"

COMPOSIÇÃO COMO NARRATIVA:
  Onde o olho entra: headline centralizado — âncora do bloco
  Percurso: headline → grid de 3 blocos (esquerda → centro → direita)
  Ponto de chegada: ícone + título de cada bloco
  Espaço para texto: dentro de cada coluna do grid

LAYOUT DESKTOP:
  ┌──────────────────────────────────────────────────────────┐
  │  [BURGUNDY · grain ativo] padding: 100px 0               │
  │  Container: 1160px                                       │
  │                                                          │
  │         O que faz cada Delicê ser única                  │
  │         [H2 Italic / cream / centralizado]               │
  │         [margin-bottom: 64px]                            │
  │                                                          │
  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐   │
  │  │  ⬡ ícone    │  │  ⬡ ícone    │  │  ⬡ ícone    │   │
  │  │  gold 32px   │  │  gold 32px   │  │  gold 32px   │   │
  │  │              │  │              │  │              │   │
  │  │  Ingredientes│  │  Cada detalhe│  │  Entrega     │   │
  │  │  selecionados│  │  personaliza-│  │  no prazo,   │   │
  │  │              │  │  do          │  │  sempre      │   │
  │  │  [H3 SC 20px │  │  [H3 SC]     │  │  [H3 SC]     │   │
  │  │   cream]     │  │              │  │              │   │
  │  │              │  │              │  │              │   │
  │  │  [body 15px  │  │  [body]      │  │  [body]      │   │
  │  │   cream/60%] │  │              │  │              │   │
  │  └──────────────┘  └──────────────┘  └──────────────┘   │
  │  grid-template-columns: repeat(3, 1fr) / gap: 40px       │
  │  text-align: center (cada coluna)                        │
  └──────────────────────────────────────────────────────────┘

LAYOUT MOBILE:
  grid: 1 coluna / gap: 40px / cada bloco centralizado

BACKGROUND:
  Cor: #6B1A2A
  Efeito: sólido
  Grain: sim — 4% opacity

IMAGENS DESTA DOBRA:
  Total: 0 — diferenciais são texto + ícone
  (evitar foto aqui — imagem na dobra seguinte terá mais impacto)

ÍCONES:
  Família: Iconify Solar Outline
  Tamanho: 32px / Cor: #B8924A
  Ícone 1: solar:heart-outline (ingredientes/cuidado)
  Ícone 2: solar:pen-new-square-outline (personalização)
  Ícone 3: solar:clock-circle-outline (pontualidade)
  Cada ícone: display block / margin: 0 auto 16px

ANIMAÇÃO:
  Reveal: stagger entre os 3 blocos (delay 0ms / 150ms / 300ms)
  Fade-up 700ms each

CTA: nenhum

PESO: levíssimo — ícones SVG inline
══════════════════════════════════════════════════════
```

---

## DOBRA 5 — CATÁLOGO PREVIEW

```
══════════════════════════════════════════════════════
OBJETIVO NA JORNADA:
  Mostrar o produto. A persona precisa ver o que está comprando antes
  de qualquer conversa de preço. Esta dobra transforma desejo abstrato
  em desejo concreto por um item específico.

HEADLINE DESTA DOBRA:
  "Feito para o seu momento"

COMPOSIÇÃO COMO NARRATIVA:
  Onde o olho entra: headline + badge acima do grid
  Percurso: badge → headline → 3 cards (esquerda → direita)
  Ponto de chegada: botão primário abaixo do grid
  Espaço para texto: dentro de cada card (abaixo da imagem)

LAYOUT DESKTOP:
  ┌──────────────────────────────────────────────────────────┐
  │  [CREAM] padding: 100px 0 / id="catalogo"                │
  │  Container: 1160px                                       │
  │                                                          │
  │         ✦ Nosso Catálogo ✦                              │
  │         [badge gold / Cormorant SC / centralizado]       │
  │                                                          │
  │         Feito para o seu momento                         │
  │         [H2 Italic / text-dark / centralizado]           │
  │         [margin-bottom: 56px]                            │
  │                                                          │
  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐   │
  │  │ [imagem 4:3] │  │ [imagem 4:3] │  │ [imagem 4:3] │   │
  │  │ border-rad   │  │ border-rad   │  │ border-rad   │   │
  │  │ 16px top     │  │ 16px top     │  │ 16px top     │   │
  │  ├──────────────┤  ├──────────────┤  ├──────────────┤   │
  │  │ BOLOS        │  │ DOCES &      │  │ SOBREMESAS   │   │
  │  │ ARTÍSTICOS   │  │ BOMBONS      │  │ NA TAÇA      │   │
  │  │ [label SC]   │  │ [label SC]   │  │ [label SC]   │   │
  │  │              │  │              │  │              │   │
  │  │ Para os gran-│  │ Presentes que│  │ Delicadeza   │   │
  │  │ des momentos │  │ falam por    │  │ em formato   │   │
  │  │ [body 14px]  │  │ você [body]  │  │ de porção    │   │
  │  └──────────────┘  └──────────────┘  └──────────────┘   │
  │  card-produto / grid-3 / gap: 24px / shadow-card         │
  │                                                          │
  │              [VER CATÁLOGO COMPLETO →]                   │
  │              [btn-primary / margin-top: 48px]            │
  └──────────────────────────────────────────────────────────┘

LAYOUT MOBILE:
  grid: 1 coluna / cards empilhados / botão full-width

BACKGROUND:
  Cor: #F5EDE4
  Efeito: sólido
  Cards: background #FAF3EE (--surface)
  Grain: não
  Hover cards: translateY(-4px) + shadow-hover / 400ms ease-elegant

IMAGENS DESTA DOBRA:
  Total: 3 (uma por card)

  IMAGEM 1:
    Nome do arquivo: catalogo-bolos-artisticos.jpg
    Tipo: 03 — Produto destaque
    Função: provar que os bolos são visualmente memoráveis — criar desejo
             pela estética antes de qualquer descrição.
    Posição: topo do card / aspect-ratio: 4:3 / object-fit: cover
    Proporção: 4:3 (600×450px)
    Tratamento: foto pura, sem overlay
    Agrupamento: dentro de card (border-radius 16px apenas topo)
    Decisão de luz: luz lateral quente, sombras suaves. Marble ou madeira
                    clara como superfície. NÃO fundo branco de estúdio.
    Mobile: mantém no topo do card empilhado

  IMAGEM 2:
    Nome do arquivo: catalogo-doces-bombons.jpg
    Tipo: 03 — Produto destaque
    Função: mostrar variedade e o produto de entrada (menor ticket) —
             abrir o catálogo para quem quer começar menor.
    Posição: topo do card central
    Proporção: 4:3 (600×450px)
    Tratamento: foto pura
    Decisão de luz: luz quente, fundo neutro quente (não branco puro)
    Mobile: mantém

  IMAGEM 3:
    Nome do arquivo: catalogo-sobremesas-taca.jpg
    Tipo: 03 — Produto destaque
    Função: mostrar produto diferenciado — sobremesas em taça ampliam
             a percepção do portfólio além de "só bolos".
    Posição: topo do card direito
    Proporção: 4:3 (600×450px)
    Tratamento: foto pura
    Decisão de luz: idem — luz quente, fundo neutro quente
    Mobile: mantém

ÍCONES: nenhum (não compete com as fotos dos produtos)

ANIMAÇÃO:
  Cards: stagger reveal — delay 0ms / 150ms / 300ms / fade-up 700ms
  Hover: translateY(-4px) + shadow-hover / 400ms

CTA: "Ver catálogo completo →" — btn-primary — âncora ou link externo

PESO: 3 imagens de produto — WebP, max 180KB cada
══════════════════════════════════════════════════════
```

---

## DOBRA 6 — DEPOIMENTOS (Prova Social)

```
══════════════════════════════════════════════════════
OBJETIVO NA JORNADA:
  Eliminar o medo de errar. A persona precisa ouvir de outras mulheres
  que já arriscaram e acertaram. Esta dobra converte crença em certeza.

HEADLINE DESTA DOBRA:
  "O que dizem sobre a Delicê"

COMPOSIÇÃO COMO NARRATIVA:
  Onde o olho entra: headline cream sobre burgundy
  Percurso: badge → headline → 2–3 cards de depoimento em coluna
  Ponto de chegada: último card (o mais emocional deve ser o último)
  Espaço para texto: cards centralizados, max-width: 760px

LAYOUT DESKTOP:
  ┌──────────────────────────────────────────────────────────┐
  │  [BURGUNDY · grain ativo] padding: 100px 0               │
  │  Container: 760px (narrower — foco na leitura)           │
  │                                                          │
  │         ✦ O que dizem sobre a Delicê ✦                  │
  │         [badge cream outline / SC / centralizado]        │
  │                                                          │
  │  ┌────────────────────────────────────────────────────┐  │
  │  │  "                                                 │  │
  │  │  [aspas douradas SVG / 40px / gold]                │  │
  │  │                                                    │  │
  │  │  [texto do depoimento — Cormorant Garamond Italic  │  │
  │  │   18px / cream / line-height 1.7]                  │  │
  │  │                                                    │  │
  │  │  ─── [Nome da cliente] · [ocasião]                 │  │
  │  │  [Cormorant SC 12px / gold / letter-spacing .08]   │  │
  │  └────────────────────────────────────────────────────┘  │
  │  [gap: 24px entre cards]                                 │
  │  Cards: bg rgba(245,237,228,0.06) / border-radius 12px   │
  │         border: 1px solid rgba(184,146,74,0.2)           │
  │         padding: 32px 36px                               │
  └──────────────────────────────────────────────────────────┘

LAYOUT MOBILE:
  max-width: 100% / padding cards: 24px / font-size: 16px

BACKGROUND:
  Cor: #6B1A2A
  Efeito: sólido
  Grain: sim — 4% opacity
  Cards: glassmorphism leve (bg com opacity baixa, borda gold sutil)

IMAGENS DESTA DOBRA:
  Total: 0 (sem foto dos clientes por padrão)
  ATENÇÃO: se Byanca tiver prints de WhatsApp com resultado,
  podem entrar como imagem extra — tipo 04 (Prova Social).
  Se sim:
    Nome do arquivo: depoimento-print-wpp-[N].jpg
    Tipo: 04 — Prova Social
    Função: credibilidade visual — print real é mais crível que
             texto formatado.
    Posição: abaixo do texto do depoimento, dentro do card
    Proporção: livre (crop do print) / max-width: 280px
    Tratamento: foto pura (sem overlay)
    Agrupamento: dentro do card, abaixo da citação

ÍCONES:
  " aspas: SVG customizado (não Iconify) / 40px / #B8924A
  Posição: canto superior esquerdo do card, margin-bottom: 16px

ANIMAÇÃO:
  Cards: stagger fade-up / delay 0ms, 150ms, 300ms / 700ms

CTA: nenhum (deixar a prova social falar sozinha)

⚠️ PENDÊNCIA: conteúdo dos depoimentos pendente com Byanca.
   Placeholder até confirmação: italics + cor muted.

PESO: levíssimo se sem imagens
══════════════════════════════════════════════════════
```

---

## DOBRA 7 — COMO FUNCIONA (Processo)

```
══════════════════════════════════════════════════════
OBJETIVO NA JORNADA:
  Eliminar a fricção do "não sei como pedir". Esta dobra transforma
  o processo de encomenda em algo simples e acolhedor. A persona que
  chegou até aqui quer comprar — essa dobra remove o último obstáculo.

HEADLINE DESTA DOBRA:
  "Encomendar é simples"

COMPOSIÇÃO COMO NARRATIVA:
  Onde o olho entra: headline + badge
  Percurso: headline → 3 passos da esquerda para a direita
             conectados por linha dourada
  Ponto de chegada: botão WhatsApp no passo 2 (ponto de ação)
  Espaço para texto: embaixo de cada ícone/número

LAYOUT DESKTOP:
  ┌──────────────────────────────────────────────────────────┐
  │  [CREAM] padding: 100px 0                                │
  │  Container: 1160px                                       │
  │                                                          │
  │         ✦ Como funciona ✦                               │
  │         [badge gold / centralizado]                      │
  │                                                          │
  │         Encomendar é simples                             │
  │         [H2 Italic / text-dark / centralizado]           │
  │         [margin-bottom: 64px]                            │
  │                                                          │
  │  ┌───────┐  ────────────  ┌───────┐  ──────────  ┌──────┐│
  │  │  01   │               │  02   │              │  03  ││
  │  │ ⬡icon │ [linha gold]  │ ⬡icon │ [linha gold] │⬡icon ││
  │  │       │               │       │              │      ││
  │  │Escolha│               │Envie  │              │Receba││
  │  │seu    │               │sua    │              │com   ││
  │  │momento│               │encomen│              │perfei││
  │  │       │               │da     │              │ção   ││
  │  │[body] │               │[body] │              │[body]││
  │  │       │               │       │              │      ││
  │  │       │               │[FALAR │              │      ││
  │  │       │               │NO WPP]│              │      ││
  │  └───────┘               └───────┘              └──────┘│
  │                                                          │
  │  grid-3 / linha conectora: ::before pseudo em gold      │
  │  Número: Cormorant Garamond 72px / Italic / gold / 0.15 │
  └──────────────────────────────────────────────────────────┘

LAYOUT MOBILE:
  grid: 1 coluna / linha conectora: vertical (::before height)
  passos empilhados / linha à esquerda de cada passo

BACKGROUND:
  Cor: #F5EDE4
  Efeito: sólido
  Linha conectora: 1px solid rgba(184,146,74,0.4) / pseudo-elemento
  Grain: não

IMAGENS DESTA DOBRA:
  Total: 0 — processo é ícone + texto
  Opcional: embalagem.jpg como imagem decorativa ao lado do passo 3
    Nome do arquivo: embalagem-entrega.jpg (se usar)
    Tipo: 07 — Contexto/Atmosfera
    Função: concretizar o "receba com perfeição" visualmente
    Posição: canto direito, flutuante, max-width: 240px
    Tratamento: foto pura, border-radius: 12px

ÍCONES:
  Iconify Solar Outline / 32px / #B8924A
  Passo 1: solar:calendar-outline
  Passo 2: solar:chat-round-like-outline
  Passo 3: solar:box-outline
  Números: Cormorant Garamond Italic / 72px / gold / opacity: 0.18
           position: absolute acima do ícone

ANIMAÇÃO:
  Passos: stagger reveal (delay 0, 200ms, 400ms) / fade-up 700ms
  Linha conectora: width 0→100% / 800ms / ease-smooth / triggered on reveal

CTA:
  Dentro do passo 2: "Falar no WhatsApp →" — link dourado (não btn-primary)
  href: https://wa.me/5524993121791

PESO: levíssimo
══════════════════════════════════════════════════════
```

---

## DOBRA 8 — GALERIA

```
══════════════════════════════════════════════════════
OBJETIVO NA JORNADA:
  Confirmar a escolha visualmente. A persona que chegou aqui já quer
  comprar — esta dobra é o "ver para crer" final. Cada foto prova que
  o produto é tão bonito quanto prometido.

HEADLINE DESTA DOBRA:
  "Cada detalhe é intencional"

COMPOSIÇÃO COMO NARRATIVA:
  Onde o olho entra: grid assimétrico — foto grande domina
  Percurso: foto grande (esq) → duas menores (dir-top, right-bottom)
             → foto horizontal (base)
  Ponto de chegada: última foto (bastidores/processo — humaniza)
  Espaço para texto: mínimo — badge + headline acima, grid é o herói

LAYOUT DESKTOP:
  ┌──────────────────────────────────────────────────────────┐
  │  [CREAM] padding: 80px 0 / id="galeria"                  │
  │  Container: 1160px                                       │
  │                                                          │
  │         Cada detalhe é intencional                       │
  │         [H2 Italic / text-dark / centralizado]           │
  │         [margin-bottom: 48px]                            │
  │                                                          │
  │  ┌──────────────────────┐  ┌─────────┐  ┌────────────┐  │
  │  │                      │  │         │  │            │  │
  │  │  detalhe-            │  │ detalhe-│  │ ambiente-  │  │
  │  │  decoracao.jpg       │  │ corte   │  │ mesa.jpg   │  │
  │  │                      │  │ .jpg    │  │            │  │
  │  │  [grande, 2:3]       │  │ [1:1]   │  │ [16:9]     │  │
  │  │  row-span: 2         │  │         │  │            │  │
  │  └──────────────────────┘  └─────────┘  └────────────┘  │
  │                            ┌──────────────────────────┐  │
  │                            │  bastidores.jpg          │  │
  │                            │  [16:9 / span 2 cols]    │  │
  │                            └──────────────────────────┘  │
  │                                                          │
  │  CSS Grid:                                               │
  │  grid-template-columns: 2fr 1fr 1fr                      │
  │  grid-template-rows: auto auto                           │
  │  gap: 12px / border-radius: 12px em cada foto            │
  │                                                          │
  │  Hover: overlay rgba(184,146,74,0.2) + scale(1.02)       │
  │         transition: 400ms ease-elegant                   │
  └──────────────────────────────────────────────────────────┘

LAYOUT MOBILE:
  grid: 1 coluna / todas as fotos empilhadas / aspect-ratio: 16:9
  (simplifica a assimetria que não funciona em mobile)

BACKGROUND:
  Cor: #F5EDE4
  Cards/fotos: sem background próprio (overflow: hidden)
  Grain: não
  Hover: overlay gold 0.2 opacity sobre cada foto

IMAGENS DESTA DOBRA:
  Total: 4

  IMAGEM 1:
    Nome do arquivo: detalhe-decoracao.jpg
    Tipo: 06 — Detalhe / Textura
    Função: provar domínio técnico artístico — a precisão dos detalhes
             é o argumento que justifica o preço e a escolha.
    Posição: coluna esquerda, row-span 2 (ocupa toda a altura)
    Proporção: 2:3 (vertical, ~380×570px no grid)
    Tratamento: foto pura / hover: scale(1.02) + overlay gold
    Decisão de luz: macro, luz suave lateral, dourado natural da decoração
    Mobile: primeira foto empilhada, aspect-ratio: 4:3

  IMAGEM 2:
    Nome do arquivo: detalhe-corte.jpg
    Tipo: 06 — Detalhe / Textura
    Função: mostrar o interior — prova que é bom por dentro, não só bonito.
             Quebra objeção "só é bonito por fora".
    Posição: canto superior direito, 1:1
    Proporção: 1:1 (360×360px)
    Tratamento: foto pura / hover: scale(1.02)
    Decisão de luz: luz direta suave, sombras quentes nos recheios
    Mobile: segunda foto empilhada

  IMAGEM 3:
    Nome do arquivo: ambiente-mesa.jpg
    Tipo: 07 — Contexto / Atmosfera
    Função: mostrar o produto no contexto de uso — a festa, a mesa,
             o momento. Ativa a memória aspiracional da persona.
    Posição: canto inferior direito, 16:9
    Proporção: 16:9 (360×202px no grid)
    Tratamento: foto pura / hover: scale(1.02)
    Decisão de luz: luz quente de evento, velas, dourado ambiente
    Mobile: terceira foto empilhada

  IMAGEM 4:
    Nome do arquivo: bastidores-maos.jpg
    Tipo: 07 — Processo / Atmosfera
    Função: humanizar a marca. Mãos trabalhando = cuidado real, não
             produto de fábrica. É a última imagem da galeria por isso —
             deixa a impressão de artesanalidade como fechamento.
    Posição: segunda linha, colunas 2–3 (span 2), 16:9
    Proporção: 16:9 (~740×416px no grid)
    Tratamento: foto pura / hover: scale(1.02) + overlay gold 0.15
    Decisão de luz: luz quente de cozinha/laboratório, sombras caramelizadas
    Mobile: quarta foto empilhada (última — mantém o fechamento)

ÍCONES: nenhum (não compete com as fotos)

ANIMAÇÃO:
  Grid: stagger reveal — delay 0, 100ms, 200ms, 300ms / fade-up 600ms
  Hover: scale(1.02) + overlay gold / 400ms ease-elegant

CTA: nenhum

PESO: 4 imagens — WebP, max 150KB cada. Total da galeria < 600KB.
══════════════════════════════════════════════════════
```

---

## DOBRA 9 — FAQ

```
══════════════════════════════════════════════════════
OBJETIVO NA JORNADA:
  Eliminar as últimas objeções racionais. A persona que chegou aqui
  está convencida emocionalmente — esta dobra remove as dúvidas
  práticas que ainda travam o clique final.

HEADLINE DESTA DOBRA:
  "Dúvidas frequentes"

COMPOSIÇÃO COMO NARRATIVA:
  Onde o olho entra: headline + badge
  Percurso: perguntas em sequência — cada uma expandida por accordion
  Ponto de chegada: última pergunta (geralmente a mais sensível — preço)
  Espaço para texto: coluna única, max-width: 720px, centralizado

LAYOUT DESKTOP:
  ┌──────────────────────────────────────────────────────────┐
  │  [BURGUNDY · grain ativo] padding: 100px 0               │
  │  Container: 720px (narrow — leitura confortável)         │
  │                                                          │
  │         Dúvidas frequentes                               │
  │         [H2 Italic / cream / centralizado / mb: 56px]    │
  │                                                          │
  │  ┌────────────────────────────────────────────────────┐  │
  │  │  Qual o prazo mínimo para encomendar?          [+] │  │
  │  │  border-bottom: 1px solid rgba(184,146,74,0.3)     │  │
  │  │  padding: 20px 0                                   │  │
  │  │  [Cormorant Garamond 17px / cream / weight 400]    │  │
  │  │  [+] ícone: solar:alt-arrow-down-outline / 20px    │  │
  │  ├────────────────────────────────────────────────────┤  │
  │  │  Vocês entregam em Barra Mansa e região?       [+] │  │
  │  ├────────────────────────────────────────────────────┤  │
  │  │  Como funciona o pagamento e o sinal?          [+] │  │
  │  ├────────────────────────────────────────────────────┤  │
  │  │  Posso personalizar completamente o bolo?      [+] │  │
  │  ├────────────────────────────────────────────────────┤  │
  │  │  E se eu não souber exatamente o que quero?    [+] │  │
  │  └────────────────────────────────────────────────────┘  │
  │                                                          │
  │  Accordion open: resposta em body 15px / cream 80%       │
  │  padding: 0 0 20px / animate: height 300ms ease-smooth   │
  └──────────────────────────────────────────────────────────┘

LAYOUT MOBILE:
  max-width: 100% / padding: 64px 24px
  Perguntas: font-size: 16px

BACKGROUND:
  Cor: #6B1A2A
  Efeito: sólido
  Grain: sim — 4% opacity
  Borda entre items: rgba(184,146,74,0.3) — 1px — não full gold

IMAGENS DESTA DOBRA:
  Total: 0

ÍCONES:
  Iconify Solar Outline: solar:alt-arrow-down-outline / 20px / gold
  Rotação no open: 0deg → 180deg / 300ms / ease-smooth

ANIMAÇÃO:
  Accordion: max-height 0→auto / opacity 0→1 / 300ms ease-smooth
  Ícone: rotate 0→180deg / 300ms

CTA: nenhum (próxima dobra tem o CTA final)

⚠️ PENDÊNCIA: respostas das perguntas pendentes com Byanca.
   Questões: prazo mínimo, área de entrega, política de sinal.

PESO: levíssimo
══════════════════════════════════════════════════════
```

---

## DOBRA 10 — CTA FINAL

```
══════════════════════════════════════════════════════
OBJETIVO NA JORNADA:
  Fechar. Esta é a dobra de conversão máxima — tudo que veio antes
  foi para chegar aqui. O tom muda: de argumento para convite.
  Quente, humano, sem pressão — mas com clareza de ação.

HEADLINE DESTA DOBRA:
  "Pronta para criar juntas?"

COMPOSIÇÃO COMO NARRATIVA:
  Onde o olho entra: ornamento SVG centralizado (quebra visual pós-FAQ)
  Percurso: ornamento → headline → corpo → botão grande
  Ponto de chegada: btn-primary gold (maior da página)
  Espaço para texto: coluna única, max-width: 640px, centralizado

LAYOUT DESKTOP:
  ┌──────────────────────────────────────────────────────────┐
  │  [CREAM + gradiente gold suave]                          │
  │  background: linear-gradient(to bottom,                  │
  │    #F5EDE4 60%, rgba(184,146,74,0.06) 100%)              │
  │  padding: 120px 0                                        │
  │  Container: 640px (estreito — máxima intimidade)         │
  │                                                          │
  │           ✦ [ornamento SVG floral / 40px / gold]         │
  │           [margin-bottom: 32px / centralizado]           │
  │                                                          │
  │         Pronta para criar juntas?                        │
  │         [H2 Italic / text-dark / centralizado]           │
  │         [font-size: clamp(36px,4.5vw,56px)]              │
  │                                                          │
  │    Entre em contato pelo WhatsApp e vamos criar          │
  │    juntas o bolo perfeito para o seu momento.            │
  │    [body 17px / text-dark 70% / text-align: center]      │
  │    [margin: 24px 0 40px]                                 │
  │                                                          │
  │    [FALAR COM BYANCA NO WHATSAPP →]                      │
  │    [btn-primary / padding: 18px 48px / font-size: 16px]  │
  │    [display: block / mx-auto / max-width: fit-content]   │
  │                                                          │
  │    Resposta em até 24h · Barra Mansa, RJ                 │
  │    [Cormorant SC / 11px / text-muted / mt: 16px]         │
  └──────────────────────────────────────────────────────────┘

LAYOUT MOBILE:
  padding: 80px 24px / botão full-width

BACKGROUND:
  Cor: #F5EDE4
  Efeito: gradiente sutil cream → gold 6% (to bottom)
  Grain: não
  Ornamento: SVG floral centralizado, opacity: 0.6, 40px (não flutuante aqui)

IMAGENS DESTA DOBRA:
  Total: 0 — a ausência de imagem mantém foco total no CTA

ÍCONES:
  ✦ SVG ornamental (não Iconify) — decorativo
  Seta → inline no texto do botão

ANIMAÇÃO:
  Reveal: fade-up toda a dobra / 700ms / ease-elegant
  Botão: pulse suave ao entrar no viewport (1x, chama atenção)
         animation: pulse-cta 0.6s ease-out 800ms forwards

CTA:
  "Falar com Byanca no WhatsApp →"
  href: https://wa.me/5524993121791
  btn-primary / maior da página / padding generoso

PESO: levíssimo
══════════════════════════════════════════════════════
```

---

## DOBRA 11 — FOOTER

```
══════════════════════════════════════════════════════
OBJETIVO NA JORNADA:
  Fechar a experiência com consistência de marca. Footer não converte
  — organiza e fecha. Deve parecer o mesmo universo do resto da página.

LAYOUT DESKTOP:
  ┌──────────────────────────────────────────────────────────┐
  │  [BURGUNDY · grain ativo] padding: 56px 0 40px           │
  │  Container: 1160px                                       │
  │                                                          │
  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐   │
  │  │ DELICÊ       │  │ Sobre        │  │ [instagram]  │   │
  │  │ [monograma/  │  │ Catálogo     │  │ [whatsapp]   │   │
  │  │  logotipo    │  │ Encomendas   │  │              │   │
  │  │  cream]      │  │ [links SC    │  │ [ícones gold │   │
  │  │              │  │  12px / muted│  │  Solar 24px] │   │
  │  │ Confeitaria  │  │  cream]      │  │              │   │
  │  │ Artesanal    │  │              │  │              │   │
  │  │ [SC 10px]    │  │              │  │              │   │
  │  └──────────────┘  └──────────────┘  └──────────────┘   │
  │  grid-template-columns: 1.5fr 1fr 1fr                    │
  │                                                          │
  │  ─────────────────────────────────────────────────────   │
  │  [borda top: 1px solid rgba(245,237,228,0.15)]           │
  │                                                          │
  │  © 2024 Delicê Confeitaria · Byanca Costa · Barra Mansa  │
  │  [SC / 10px / cream / opacity: 0.5 / text-center]        │
  └──────────────────────────────────────────────────────────┘

LAYOUT MOBILE:
  grid: 1 coluna / gap: 32px / text-align: center

BACKGROUND:
  Cor: #6B1A2A
  Grain: sim — 4% opacity

IMAGENS: 0

ÍCONES:
  Iconify Solar Outline / 24px / gold
  solar:instagram-outline + solar:chat-round-outline (WhatsApp)
  Hover: opacity 0.7 / transition 200ms

ANIMAÇÃO: nenhuma (footer não precisa de reveal)
══════════════════════════════════════════════════════
```

---

## ENTREGA FINAL

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
RESUMO — DELICÊ CONFEITARIA GOURMET

Total de dobras:           12 (topbar + 10 seções + footer)
Dobras com imagem:         4 (hero, sobre, catálogo, galeria)
Total de imagens:          10 (detalhadas abaixo)
Dobras sem imagem:         8 (intencional — respiro dramático)
Dobras com vídeo:          0
Dobras com CTA:            4 (hero, catálogo, processo, CTA final)
Barra fixa de CTA:         não (topbar já serve esse papel)
Barra de escassez:         não (produto não tem urgência por prazo)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

INVENTÁRIO COMPLETO DE IMAGENS (para skill 04 — Lovable):

  hero-bolo-atmosfera.jpg     — dobra 1  — tipo 07 — criar desejo aspiracional antes de argumentar
  byanca-retrato.jpg          — dobra 3  — tipo 01 — transferir confiança humana via conexão com a Byanca
  catalogo-bolos-artisticos.jpg — dobra 5 — tipo 03 — provar que os bolos são visualmente memoráveis
  catalogo-doces-bombons.jpg  — dobra 5  — tipo 03 — mostrar produto de entrada / variedade
  catalogo-sobremesas-taca.jpg — dobra 5 — tipo 03 — ampliar percepção do portfólio além de bolos
  detalhe-decoracao.jpg       — dobra 8  — tipo 06 — provar domínio técnico / justificar escolha
  detalhe-corte.jpg           — dobra 8  — tipo 06 — mostrar qualidade interna (quebra objeção)
  ambiente-mesa.jpg           — dobra 8  — tipo 07 — contextualizar produto no momento de uso
  bastidores-maos.jpg         — dobra 8  — tipo 07 — humanizar a marca / artesanalidade real
  embalagem-entrega.jpg       — dobra 7  — tipo 07 — [OPCIONAL] concretizar "receba com perfeição"

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

MAPA DE BACKGROUNDS:

  Dobra 0 (Topbar):     #6B1A2A — sólido — grain: não
  Dobra 1 (Hero):       foto + overlay rgba(107,26,42,0.55) — grain: sim 3%
  Dobra 2 (Tensão):     #6B1A2A — sólido — grain: sim 4%
  Dobra 3 (Byanca):     #F5EDE4 — sólido — grain: não
  Dobra 4 (Diferenc.):  #6B1A2A — sólido — grain: sim 4%
  Dobra 5 (Catálogo):   #F5EDE4 — sólido — grain: não
  Dobra 6 (Depoim.):    #6B1A2A — sólido — grain: sim 4%
  Dobra 7 (Processo):   #F5EDE4 — sólido — grain: não
  Dobra 8 (Galeria):    #F5EDE4 — sólido — grain: não
  Dobra 9 (FAQ):        #6B1A2A — sólido — grain: sim 4%
  Dobra 10 (CTA):       #F5EDE4 + gradiente gold 6% — grain: não
  Dobra 11 (Footer):    #6B1A2A — sólido — grain: sim 4%

  Padrão de alternância: burgundy → cream → burgundy → cream (regular)
  Texturas ativas: grain 4% opacity em TODAS as seções burgundy
  Efeito adicional: gradiente gold suave no CTA final (único)
  Ornamentos flutuantes: hero (2x) + CTA final (1x, não animado)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

ALERTAS CSS PARA SKILL 04 (Lovable):

  [ ] Hero single-column → h1 global clamp(52px,6vw,80px) está correto.
      NÃO é split. Não precisa override.

  [ ] Foto retrato Byanca com fundo de estúdio → aplicar:
      filter: brightness(.82) contrast(1.05)
      overlay em camadas (NÃO simples opacity — vaza):
        linear-gradient(to right, #F5EDE4 0%, rgba(245,237,228,.55) 45%,
          rgba(245,237,228,.15) 70%, transparent 100%)
        + to top #F5EDE4 0% → transparent 28%
        + to bottom rgba(245,237,228,.4) 0% → transparent 20%

  [ ] Grain overlay: 4% opacity / seções burgundy apenas (dobras 2,4,6,9,11)
      Implementar via ::after pseudo / SVG noise / pointer-events: none

  [ ] Ornamentos SVG: NÃO usar Iconify para ornamentos florais/decorativos.
      Usar SVG inline customizado. Iconify apenas para ícones funcionais.

  [ ] Ícones funcionais: Iconify Solar Outline exclusivamente.
      solar:heart-outline / solar:pen-new-square-outline /
      solar:clock-circle-outline / solar:calendar-outline /
      solar:chat-round-like-outline / solar:box-outline /
      solar:alt-arrow-down-outline (FAQ accordion) /
      solar:instagram-outline / solar:chat-round-outline

  [ ] Card galeria: grid assimétrico (2fr 1fr 1fr / 2 linhas).
      Mobile: simplifica para 1 coluna — NÃO tentar manter assimetria.

  [ ] WhatsApp href: https://wa.me/5524993121791 (todos os CTAs)

  [ ] Accordion FAQ: max-height animation (não display toggle) para
      transição suave de abertura/fechamento.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PENDÊNCIAS COM BYANCA (bloqueia implementação final):
  → Depoimentos reais (mínimo 2) → dobra 6
  → Prazo mínimo de encomenda → dobra 7 + FAQ
  → Área de entrega (cidades/bairros) → FAQ
  → Política de sinal e pagamento → FAQ
  → Foto retrato Byanca → dobra 3
  → Fotos dos produtos reais → dobra 5 + 8
  → Handle do Instagram → footer

PRÓXIMO PASSO:
  → pagina-vendas-04-lovable:
     leva este wireframe + design system (Delice-DesignSystem.md)
     + copy das 20 peças + inventário de imagens
     → entrega sequência de prompts para construção no Lovable
        + prompts de imagem por arquivo para geração no Freepik
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

*Wireframe gerado pela Etapa 3 do pipeline · pagina-vendas-03-diretor-criacao*
*Design system: Delice-DesignSystem.md · Copy: pagina-vendas-01-copy*
*Ana Carolina Braga / @ana.automacoes · 2024*
