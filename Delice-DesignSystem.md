# DESIGN SYSTEM — DELICÊ CONFEITARIA GOURMET
### Versão 1.0 · Página de Apresentação + Catálogo
**Referência estrutural:** divosdaia.com.br/clube · **Identidade:** Byanca Costa / Barra Mansa, RJ

---

## 1. CSS VARIABLES — TOKENS GLOBAIS

```css
:root {
  /* ── PALETA ─────────────────────────────────── */
  --cream:       #F5EDE4;   /* bg principal (seções claras) */
  --burgundy:    #6B1A2A;   /* bg seções escuras + títulos hero */
  --marsala:     #8B2942;   /* hover, gradientes, acento profundo */
  --gold:        #B8924A;   /* CTAs, bordas accent, ícones, shimmer */
  --gold-light:  #D4AA6A;   /* hover do gold, ornamentos secundários */
  --surface:     #FAF3EE;   /* cards, superfícies elevadas */
  --text-dark:   #3A1A20;   /* corpo em fundo claro */
  --text-light:  #F5EDE4;   /* texto em fundo burgundy */
  --text-muted:  #9A7A7A;   /* subtextos, labels secundários */

  /* ── TIPOGRAFIA ─────────────────────────────── */
  --font-heading: 'Cormorant Garamond', Georgia, serif;
  --font-caps:    'Cormorant SC', Georgia, serif;
  --font-body:    'Cormorant Garamond', Georgia, serif;

  /* ── ESCALA TIPOGRÁFICA ─────────────────────── */
  --text-hero:    clamp(52px, 6vw, 80px);
  --text-h2:      clamp(36px, 4.5vw, 56px);
  --text-h3:      clamp(20px, 2vw, 26px);
  --text-body:    clamp(15px, 1.2vw, 17px);
  --text-label:   13px;
  --text-micro:   11px;

  /* ── LAYOUT ─────────────────────────────────── */
  --container:    1160px;
  --padding-x:    clamp(20px, 4vw, 48px);
  --section-pt:   clamp(60px, 8vw, 120px);
  --section-pb:   clamp(50px, 6vw, 100px);
  --gap-card:     24px;

  /* ── COMPONENTES ─────────────────────────────── */
  --radius-card:  16px;
  --radius-pill:  50px;
  --radius-sm:    8px;
  --shadow-card:  0 4px 24px rgba(107, 26, 42, 0.08);
  --shadow-hover: 0 8px 40px rgba(107, 26, 42, 0.16);

  /* ── ANIMAÇÕES ───────────────────────────────── */
  --ease-smooth:  cubic-bezier(0.4, 0, 0.2, 1);
  --ease-elegant: cubic-bezier(0.25, 0.46, 0.45, 0.94);
  --duration-fast:   200ms;
  --duration-base:   400ms;
  --duration-slow:   700ms;
  --duration-float:  6000ms;
}
```

---

## 2. TIPOGRAFIA — ESPECIFICAÇÃO COMPLETA

### Importação Google Fonts
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400;1,600&family=Cormorant+SC:wght@400;600;700&display=swap" rel="stylesheet">
```

### Hierarquia

| Elemento | Fonte | Tamanho | Peso | Style | Line-height | Letter-spacing |
|---|---|---|---|---|---|---|
| H1 (hero) | Cormorant Garamond | `--text-hero` | 300 | Italic | 1.05 | -0.01em |
| H2 (seção) | Cormorant Garamond | `--text-h2` | 300 | Italic | 1.1 | -0.01em |
| H3 (card/bloco) | Cormorant SC | `--text-h3` | 600 | Normal | 1.2 | 0.02em |
| Body | Cormorant Garamond | `--text-body` | 400 | Normal | 1.75 | 0 |
| Label/categoria | Cormorant SC | `--text-label` | 600 | Normal | 1.4 | 0.08em |
| Micro/rodapé | Cormorant SC | `--text-micro` | 400 | Normal | 1.5 | 0.06em |
| CTA botão | Cormorant SC | 14px | 700 | Normal | 1 | 0.06em |
| Frase destaque | Cormorant Garamond | `--text-h2` | 300 | Italic | 1.2 | 0 |

### Classes CSS base
```css
.heading-hero {
  font-family: var(--font-heading);
  font-size: var(--text-hero);
  font-weight: 300;
  font-style: italic;
  line-height: 1.05;
  letter-spacing: -0.01em;
  color: var(--text-light);
}

.heading-section {
  font-family: var(--font-heading);
  font-size: var(--text-h2);
  font-weight: 300;
  font-style: italic;
  line-height: 1.1;
  color: inherit;
}

.label-caps {
  font-family: var(--font-caps);
  font-size: var(--text-label);
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

.body-text {
  font-family: var(--font-body);
  font-size: var(--text-body);
  font-weight: 400;
  line-height: 1.75;
  color: var(--text-dark);
}
```

---

## 3. GRID E LAYOUT

```css
.container {
  width: 100%;
  max-width: var(--container);
  margin: 0 auto;
  padding: 0 var(--padding-x);
}

.section {
  padding-top: var(--section-pt);
  padding-bottom: var(--section-pb);
}

/* Seções claras */
.section--cream   { background-color: var(--cream); }

/* Seções escuras */
.section--dark    { background-color: var(--burgundy); }

/* Grid 2 colunas (sobre/benefícios) */
.grid-2 {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 48px;
  align-items: center;
}

/* Grid 3 colunas (cards produto/benefícios) */
.grid-3 {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--gap-card);
}

/* Responsivo */
@media (max-width: 768px) {
  .grid-2, .grid-3 { grid-template-columns: 1fr; gap: 32px; }
}
```

---

## 4. COMPONENTES

### 4.1 Botão Primário (CTA)
```css
.btn-primary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background-color: var(--gold);
  color: var(--cream);
  font-family: var(--font-caps);
  font-size: 14px;
  font-weight: 700;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  padding: 14px 32px;
  border-radius: var(--radius-pill);
  border: none;
  cursor: pointer;
  transition: background var(--duration-fast) var(--ease-smooth),
              transform var(--duration-fast) var(--ease-smooth),
              box-shadow var(--duration-fast) var(--ease-smooth);
  text-decoration: none;
}
.btn-primary:hover {
  background-color: var(--gold-light);
  transform: translateY(-1px);
  box-shadow: 0 6px 20px rgba(184, 146, 74, 0.35);
}
```

### 4.2 Botão Ghost
```css
.btn-ghost {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: transparent;
  color: var(--gold);
  font-family: var(--font-caps);
  font-size: 14px;
  font-weight: 700;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  padding: 13px 31px;
  border-radius: var(--radius-pill);
  border: 1px solid var(--gold);
  cursor: pointer;
  transition: all var(--duration-fast) var(--ease-smooth);
}
.btn-ghost:hover {
  background-color: var(--gold);
  color: var(--cream);
}
/* Variante para fundo escuro */
.btn-ghost--light {
  color: var(--cream);
  border-color: var(--cream);
}
.btn-ghost--light:hover {
  background-color: var(--cream);
  color: var(--burgundy);
}
```

### 4.3 Card Produto
```css
.card-produto {
  background-color: var(--surface);
  border-radius: var(--radius-card);
  overflow: hidden;
  box-shadow: var(--shadow-card);
  transition: transform var(--duration-base) var(--ease-elegant),
              box-shadow var(--duration-base) var(--ease-elegant);
}
.card-produto:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-hover);
}
.card-produto__image {
  width: 100%;
  aspect-ratio: 4/3;
  object-fit: cover;
}
.card-produto__body {
  padding: 20px 24px 24px;
}
.card-produto__label {
  /* usa .label-caps */
  color: var(--gold);
  margin-bottom: 8px;
}
.card-produto__nome {
  /* usa .heading-section reduzido */
  font-size: var(--text-h3);
  font-weight: 400;
  font-style: italic;
  margin-bottom: 12px;
  color: var(--text-dark);
}
.card-produto__descricao {
  /* usa .body-text */
  font-size: 14px;
  color: var(--text-muted);
}
```

### 4.4 Barra de Topo (Announcement Bar)
```css
.topbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  background-color: var(--burgundy);
  padding: 10px var(--padding-x);
  text-align: center;
  font-family: var(--font-caps);
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.08em;
  color: var(--text-light);
}
.topbar a {
  color: var(--gold);
  text-decoration: none;
  margin-left: 12px;
}
.topbar a:hover { text-decoration: underline; }
```

### 4.5 Ornamento Decorativo (substitui asterisco da referência)
```css
/* Florzinha/ornamento SVG flutuante */
.ornamento {
  position: absolute;
  pointer-events: none;
  opacity: 0.18;
  animation: float-ornamento var(--duration-float) ease-in-out infinite;
}
.ornamento--gold { color: var(--gold); }
.ornamento--cream { color: var(--cream); }

@keyframes float-ornamento {
  0%, 100% { transform: translateY(0px) rotate(0deg); }
  33%       { transform: translateY(-12px) rotate(5deg); }
  66%       { transform: translateY(-6px) rotate(-3deg); }
}
```

### 4.6 Badge / Tag
```css
.badge {
  display: inline-block;
  font-family: var(--font-caps);
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--gold);
  border: 1px solid var(--gold);
  border-radius: 50px;
  padding: 4px 12px;
  background: transparent;
}
/* Em fundo escuro */
.badge--on-dark {
  color: var(--cream);
  border-color: rgba(245, 237, 228, 0.4);
}
```

### 4.7 Linha Divisória Ornamental
```css
.divider-ornamental {
  display: flex;
  align-items: center;
  gap: 16px;
  margin: 32px auto;
  max-width: 240px;
}
.divider-ornamental::before,
.divider-ornamental::after {
  content: '';
  flex: 1;
  height: 1px;
  background: var(--gold);
  opacity: 0.4;
}
/* O elemento central é um SVG inline de flor/ornamento */
```

---

## 5. ANIMAÇÕES

```css
/* Shimmer — brilho sutil em elementos dourados */
@keyframes shimmer {
  0%   { background-position: -200% center; }
  100% { background-position: 200% center; }
}
.shimmer-gold {
  background: linear-gradient(
    90deg,
    var(--gold) 0%,
    var(--gold-light) 50%,
    var(--gold) 100%
  );
  background-size: 200% auto;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: shimmer 3s linear infinite;
}

/* Grain — textura vintage sobre fundos cream */
@keyframes grain {
  0%, 100% { transform: translate(0, 0); }
  10%       { transform: translate(-2%, -3%); }
  30%       { transform: translate(3%, -1%); }
  50%       { transform: translate(-1%, 2%); }
  70%       { transform: translate(2%, 3%); }
  90%       { transform: translate(-3%, 1%); }
}
.grain-overlay::after {
  content: '';
  position: absolute;
  inset: -50%;
  width: 200%;
  height: 200%;
  background-image: url("data:image/svg+xml,..."); /* SVG noise */
  opacity: 0.04;
  pointer-events: none;
  animation: grain 8s steps(10) infinite;
}

/* Scroll reveal — fade-in das seções */
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity var(--duration-slow) var(--ease-elegant),
              transform var(--duration-slow) var(--ease-elegant);
}
.reveal.is-visible {
  opacity: 1;
  transform: translateY(0);
}
```

---

## 6. WIREFRAME — DOBRA A DOBRA

### Seção 0 — BARRA TOPO
- **BG:** `--burgundy`
- **Conteúdo:** "Encomendas abertas · Barra Mansa, RJ" + link CTA dourado "Encomendar via WhatsApp →"
- **Layout:** texto centralizado, `position: fixed`
- **Altura:** 40px

---

### Seção 1 — HERO
- **BG:** foto atmosférica (img-01) com overlay `rgba(107, 26, 42, 0.55)`
- **Layout:** coluna única, centralizado vertical e horizontal, `min-height: 100vh`
- **Elementos:**
  - Badge: "Confeitaria Artesanal · Barra Mansa"
  - H1 Italic: *"Cada bolo conta uma história"*
  - Subtítulo: "Doces criados com técnica, afeto e identidade — para os momentos que merecem ser lembrados."
  - Btn Primary: "Quero encomendar →"
  - Btn Ghost (abaixo): "Ver catálogo"
  - Ornamentos flutuantes (canto superior direito + inferior esquerdo)
- **Imagem:** img-01 (hero bg)

---

### Seção 2 — TENSÃO / FRASE DE IMPACTO
- **BG:** `--burgundy`
- **Layout:** coluna única, centralizado, padding generoso
- **Elementos:**
  - Linha ornamental dourada acima
  - H2 Italic cream: *"Bolo bom não é só gostoso. É bonito, é pontual, é exatamente o que você pediu."*
  - Label-caps gold: "O padrão Delicê"
  - Linha ornamental dourada abaixo
- **Grain overlay ativo**

---

### Seção 3 — SOBRE BYANCA
- **BG:** `--cream`
- **Layout:** grid-2 (foto esquerda | texto direita)
- **Elementos:**
  - Coluna esquerda: foto retrato Byanca (img-02), border-radius: 16px, sombra suave
  - Coluna direita:
    - Badge: "Quem está por trás da Delicê"
    - H2 Italic: *"Byanca Costa"*
    - Body: bio da confeiteira (2–3 parágrafos)
    - Destaque em itálico gold: *"X anos transformando ingredientes em memórias"*
    - Btn Ghost: "Conheça minha história →"

---

### Seção 4 — DIFERENCIAIS
- **BG:** `--burgundy`
- **Layout:** grid-3 (ícone + título + texto)
- **Elementos:**
  - H2 Italic cream centralizado (acima do grid)
  - 3 blocos com ícone SVG gold, H3 SC cream, body cream/muted
  - Ex: "Ingredientes selecionados" / "Cada detalhe personalizado" / "Entrega no prazo, sempre"
- **Grain overlay ativo**

---

### Seção 5 — CATÁLOGO PREVIEW
- **BG:** `--cream`
- **Layout:** grid-3 de cards produto
- **Elementos:**
  - Badge + H2 Italic (centralizado acima)
  - 3 card-produto: img-03, img-04, img-05
  - Btn Primary centralizado abaixo: "Ver catálogo completo →"

---

### Seção 6 — DEPOIMENTOS
- **BG:** `--burgundy`
- **Layout:** coluna única com quote cards (max-width: 760px, centralizado)
- **Elementos:**
  - Badge: "O que dizem sobre a Delicê"
  - H2 Italic cream
  - 2–3 cards depoimento: aspas douradas, texto cream, nome + badge em SC
  - *(Conteúdo pendente com Byanca)*
- **Grain overlay ativo**

---

### Seção 7 — COMO FUNCIONA (PROCESSO)
- **BG:** `--cream`
- **Layout:** timeline horizontal (3 passos) — desktop; vertical — mobile
- **Elementos:**
  - Badge + H2 Italic
  - Passo 1: "Escolha seu bolo" — ícone + texto
  - Passo 2: "Envie sua encomenda" — link WhatsApp dourado
  - Passo 3: "Receba com perfeição" — ícone entrega
  - Linha conectora dourada entre passos (decorativa)

---

### Seção 8 — GALERIA
- **BG:** `--cream` (pode ter `--surface` nos blocos internos)
- **Layout:** grid assimétrico — 2 fotos grandes + 2 menores (masonry leve)
- **Elementos:**
  - Badge + H2 Italic
  - img-06, img-07, img-08, img-09 — detalhes, texturas, processo
  - Hover suave: overlay dourado semi-transparente com ícone lupa

---

### Seção 9 — FAQ
- **BG:** `--burgundy`
- **Layout:** accordion, max-width 720px, centralizado
- **Elementos:**
  - Badge + H2 Italic cream
  - 4–5 perguntas em accordion: borda bottom gold, ícone + dourado
  - Exemplos: "Qual o prazo mínimo?", "Vocês entregam em Barra Mansa?", "Como funciona o pagamento?"
- **Grain overlay ativo**

---

### Seção 10 — CTA FINAL
- **BG:** `--cream` com gradiente suave cream → `rgba(184, 146, 74, 0.08)` no fundo
- **Layout:** coluna única, centralizado, padding ampliado
- **Elementos:**
  - Ornamento dourado centralizado acima (SVG flor)
  - H2 Italic: *"Pronta para encomendar?"*
  - Body: "Entre em contato pelo WhatsApp e vamos criar juntas o bolo perfeito para o seu momento."
  - Btn Primary grande: "Falar com Byanca no WhatsApp →"
  - Label-micro muted: "Resposta em até 24h · Barra Mansa, RJ"

---

### Seção 11 — FOOTER
- **BG:** `--burgundy`
- **Layout:** 3 colunas — logo | links | redes sociais
- **Elementos:**
  - Coluna 1: Monograma/logo Delicê (cream)
  - Coluna 2: Links âncora (Sobre, Catálogo, Encomenda)
  - Coluna 3: Instagram + WhatsApp (ícones dourados)
  - Rodapé mínimo: "© 2024 Delicê Confeitaria · Byanca Costa · Barra Mansa, RJ"
- **Grain overlay ativo**

---

## 7. INVENTÁRIO DE IMAGENS

| ID | Nome arquivo | Tipo | Função na página | Dimensões | Prompt Freepik |
|---|---|---|---|---|---|
| 01 | `hero-bolo-atm.jpg` | Fotografia atmosférica | Hero background | 1440×900px (landscape) | Artistic luxury wedding cake on marble table, soft candlelight warm tones, bokeh background, champagne cream atmosphere, no people, top-down angle 45°, editorial food photography, film grain, warm burgundy shadows |
| 02 | `byanca-retrato.jpg` | Retrato profissional | Seção Sobre | 600×750px (portrait) | Female pastry chef portrait, elegant home bakery kitchen, natural window light, warm cream and burgundy tones, genuine warm smile, apron, looking slightly off-camera, soft focus background with cakes, editorial style, film grain |
| 03 | `bolo-01-destaque.jpg` | Produto destaque | Card catálogo | 600×450px | Elegant tiered celebration cake, ivory buttercream with gold leaf details, fresh flowers, marble stand, clean white/cream background, editorial food photography, luxury confectionery |
| 04 | `bolo-02-destaque.jpg` | Produto destaque | Card catálogo | 600×450px | Rustic naked cake with berry decoration, wooden table, natural light, artisan aesthetic, warm tones, food photography, soft shadows |
| 05 | `bolo-03-destaque.jpg` | Produto destaque | Card catálogo | 600×450px | Modern minimalist cake with geometric fondant details, gold accents, studio lighting, luxury pastry photography, cream background |
| 06 | `detalhe-decoracao.jpg` | Detalhe / textura | Galeria | 600×600px | Close-up macro of sugar flower decoration on wedding cake, gold dust, soft bokeh, warm light, artisan confectionery detail |
| 07 | `detalhe-corte.jpg` | Produto / processo | Galeria | 600×600px | Cake cross-section showing layered filling, chocolate ganache, fresh fruit, marble surface, warm light, food editorial |
| 08 | `ambiente-mesa.jpg` | Ambiente / atmosfera | Galeria | 800×600px | Elegant dessert table with cakes and sweets, flowers, golden details, warm candlelight, luxury event styling, champagne tones |
| 09 | `bastidores.jpg` | Processo / bastidores | Galeria | 600×600px | Female hands decorating a cake with piping bag, blurred bakery background, warm kitchen light, artisan process, editorial style |
| 10 | `embalagem.jpg` | Produto / entrega | Opcional (FAQ/processo) | 600×400px | Luxury cake box packaging with ribbon, kraft paper, elegant branding, warm tones, product photography |

**Total: 10 imagens (9 obrigatórias + 1 opcional)**

### Tipos de imagem mapeados
- **Tipo 01 — Atmosférica:** hero-bolo-atm.jpg
- **Tipo 02 — Retrato:** byanca-retrato.jpg
- **Tipo 03/04/05 — Produto:** bolos de destaque
- **Tipo 06/07 — Detalhe/textura:** close-ups artísticos
- **Tipo 08 — Ambiente:** mesa, evento, contexto
- **Tipo 09 — Processo:** bastidores, mãos, fazer
- **Tipo 10 — Embalagem:** entrega, produto final

---

## 8. BACKGROUNDS — MAPA COMPLETO

| Seção | BG Token | Efeito adicional | Grain |
|---|---|---|---|
| Topbar | `--burgundy` | — | Não |
| Hero | Foto + overlay `rgba(107,26,42,0.55)` | Ornamentos flutuantes | Sim (leve) |
| Tensão | `--burgundy` | — | Sim |
| Sobre Byanca | `--cream` | — | Não |
| Diferenciais | `--burgundy` | — | Sim |
| Catálogo | `--cream` | `--surface` nos cards | Não |
| Depoimentos | `--burgundy` | — | Sim |
| Processo | `--cream` | Linha gold conectora | Não |
| Galeria | `--cream` | Hover overlay dourado | Não |
| FAQ | `--burgundy` | — | Sim |
| CTA Final | `--cream` + gradiente gold suave | Ornamento SVG | Não |
| Footer | `--burgundy` | — | Sim |

**Padrão:** cream → burgundy → cream → burgundy → ... (alternância constante)
**Grain:** ativo apenas em seções burgundy (toque artesanal/vintage)

---

## 9. PENDÊNCIAS COM BYANCA

Os seguintes conteúdos precisam ser fornecidos pela cliente antes da implementação:

| Item | Uso na página | Urgência |
|---|---|---|
| Depoimentos reais (3 min) | Seção 6 | Alta |
| Prazo mínimo de encomenda | FAQ + seção processo | Alta |
| Cidades/bairros atendidos | FAQ + rodapé | Alta |
| Política de sinal/pagamento | FAQ | Alta |
| Foto retrato (Byanca) | Seção 3 | Alta |
| Fotos dos produtos reais | Cards catálogo | Alta |
| Redes sociais (Instagram handle) | Footer | Média |
| WhatsApp de encomendas | CTAs (já temos: 5524993121791) | ✅ |

---

## 10. PRÓXIMOS PASSOS NO PIPELINE

1. ✅ Análise Estratégica (Analise-Estrategica-Delice.docx)
2. ✅ Copy da página (20 peças — pagina-vendas-01-copy)
3. ✅ **Design System** (este documento)
4. → **Diretor de Criação** (pagina-vendas-03-diretor-criacao): wireframe visual detalhado + nomeação das imagens por dobra
5. → **Implementação Lovable** (pagina-vendas-04-lovable): prompts de construção + prompts de imagem

---

*Design System gerado com base na referência estrutural divosdaia.com.br/clube · Identidade visual: assets fornecidos por Byanca Costa · Construído por Ana Carolina Braga / @ana.automacoes*
