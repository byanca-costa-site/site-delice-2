# PROMPTS LOVABLE — DELICÊ CONFEITARIA GOURMET
### Sequência completa de implementação · Etapa 4 do pipeline
**Use na ordem exata. Aguarde cada execução antes de avançar.**

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT 0 — SETUP COMPLETO
Cole no Lovable como PRIMEIRO prompt. Aguarde executar antes de continuar.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Crie uma landing page de apresentação e catálogo em React com Tailwind CSS.
Mobile-first. Sem menu de navegação. Sem sidebar. Foco em conversão e estética artesanal.
Não adicione nenhum componente além do que for especificado.
Não use Inter, Poppins, Roboto, Arial ou system-ui em nenhuma circunstância.
Não use ícones Lucide em nenhuma circunstância — use apenas Iconify (solar:outline).
Não adicione gradientes roxos, azuis genéricos ou qualquer estética de SaaS/template.
Esta é uma página de confeitaria gourmet artesanal — cada decisão visual deve refletir elegância, calor e artesanalidade.

---

### TAILWIND CONFIG

Substitua completamente o tailwind.config.js por este:

```js
module.exports = {
  content: ['./src/**/*.{js,jsx,ts,tsx}'],
  theme: {
    extend: {
      colors: {
        cream:        '#F5EDE4',
        burgundy:     '#6B1A2A',
        marsala:      '#8B2942',
        gold:         '#B8924A',
        'gold-light': '#D4AA6A',
        surface:      '#FAF3EE',
        'text-dark':  '#3A1A20',
        'text-light': '#F5EDE4',
        'text-muted': '#9A7A7A',
      },
      fontFamily: {
        heading: ['"Cormorant Garamond"', 'Georgia', 'serif'],
        caps:    ['"Cormorant SC"', 'Georgia', 'serif'],
        body:    ['"Cormorant Garamond"', 'Georgia', 'serif'],
      },
      fontSize: {
        hero:  ['clamp(52px, 6vw, 80px)', { lineHeight: '1.05', letterSpacing: '-0.01em' }],
        h2:    ['clamp(36px, 4.5vw, 56px)', { lineHeight: '1.1', letterSpacing: '-0.01em' }],
        h3:    ['clamp(20px, 2vw, 26px)', { lineHeight: '1.2', letterSpacing: '0.02em' }],
        body:  ['clamp(15px, 1.2vw, 17px)', { lineHeight: '1.75' }],
        label: ['13px', { lineHeight: '1.4', letterSpacing: '0.08em' }],
        micro: ['11px', { lineHeight: '1.5', letterSpacing: '0.06em' }],
      },
      spacing: {
        xs:              '8px',
        sm:              '16px',
        md:              '24px',
        lg:              '48px',
        xl:              '80px',
        section:         '120px',
        'section-mobile':'64px',
      },
      maxWidth: {
        container: '1160px',
        narrow:    '760px',
        tight:     '720px',
        intimate:  '640px',
      },
      borderRadius: {
        sm:   '8px',
        md:   '16px',
        pill: '50px',
      },
      boxShadow: {
        card:  '0 4px 24px rgba(107, 26, 42, 0.08)',
        hover: '0 8px 40px rgba(107, 26, 42, 0.16)',
        cta:   '0 6px 20px rgba(184, 146, 74, 0.35)',
      },
      transitionTimingFunction: {
        smooth:  'cubic-bezier(0.4, 0, 0.2, 1)',
        elegant: 'cubic-bezier(0.25, 0.46, 0.45, 0.94)',
      },
      keyframes: {
        'float-ornamento': {
          '0%, 100%': { transform: 'translateY(0px) rotate(0deg)' },
          '33%':      { transform: 'translateY(-12px) rotate(5deg)' },
          '66%':      { transform: 'translateY(-6px) rotate(-3deg)' },
        },
        shimmer: {
          '0%':   { backgroundPosition: '-200% center' },
          '100%': { backgroundPosition: '200% center' },
        },
        grain: {
          '0%, 100%': { transform: 'translate(0, 0)' },
          '10%':      { transform: 'translate(-2%, -3%)' },
          '30%':      { transform: 'translate(3%, -1%)' },
          '50%':      { transform: 'translate(-1%, 2%)' },
          '70%':      { transform: 'translate(2%, 3%)' },
          '90%':      { transform: 'translate(-3%, 1%)' },
        },
        'pulse-cta': {
          '0%':   { transform: 'scale(1)' },
          '50%':  { transform: 'scale(1.04)' },
          '100%': { transform: 'scale(1)' },
        },
      },
      animation: {
        'float-ornamento': 'float-ornamento 6000ms ease-in-out infinite',
        shimmer:           'shimmer 3s linear infinite',
        grain:             'grain 8s steps(10) infinite',
        'pulse-cta':       'pulse-cta 0.6s ease-out 800ms 1 forwards',
      },
    },
  },
}
```

---

### FONTES

Instale via npm:
```
npm install @fontsource/cormorant-garamond
```

Importe no main.tsx:
```tsx
import '@fontsource/cormorant-garamond/300.css'
import '@fontsource/cormorant-garamond/300-italic.css'
import '@fontsource/cormorant-garamond/400.css'
import '@fontsource/cormorant-garamond/400-italic.css'
import '@fontsource/cormorant-garamond/600.css'
import '@fontsource/cormorant-garamond/600-italic.css'
```

Para Cormorant SC, adicione via Google Fonts no index.html:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+SC:wght@400;600;700&display=swap" rel="stylesheet">
```

E adicione no tailwind.config sob fontFamily:
```js
caps: ['"Cormorant SC"', 'Georgia', 'serif'],
```

---

### CSS GLOBAL — adicione em index.css

```css
/* Grain overlay — aplica em seções escuras (burgundy) */
.grain-overlay {
  position: relative;
  overflow: hidden;
}
.grain-overlay::after {
  content: '';
  position: absolute;
  inset: -50%;
  width: 200%;
  height: 200%;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='1'/%3E%3C/svg%3E");
  opacity: 0.04;
  pointer-events: none;
  animation: grain 8s steps(10) infinite;
  z-index: 1;
}

/* Scroll reveal */
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 700ms cubic-bezier(0.25, 0.46, 0.45, 0.94),
              transform 700ms cubic-bezier(0.25, 0.46, 0.45, 0.94);
}
.reveal.is-visible {
  opacity: 1;
  transform: translateY(0);
}
.reveal-delay-1 { transition-delay: 100ms; }
.reveal-delay-2 { transition-delay: 200ms; }
.reveal-delay-3 { transition-delay: 300ms; }
.reveal-delay-4 { transition-delay: 400ms; }

/* Garante que conteúdo sobre grain fique visível */
.grain-overlay > * {
  position: relative;
  z-index: 2;
}

/* Shimmer gold em texto */
.shimmer-gold {
  background: linear-gradient(90deg, #B8924A 0%, #D4AA6A 50%, #B8924A 100%);
  background-size: 200% auto;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: shimmer 3s linear infinite;
}
```

---

### COMPONENTES GLOBAIS — crie TODOS antes de qualquer dobra

#### CTAButton.tsx
```tsx
// src/components/CTAButton.tsx
// Fundo: #B8924A (gold) | Texto: #F5EDE4 (cream)
// Font: font-caps (Cormorant SC) | Peso: 700 | Size: 14px | Letter-spacing: 0.06em | Uppercase
// Padding: 14px 32px | Border-radius: 50px (pill)
// Hover: translateY(-1px) + box-shadow 0 6px 20px rgba(184,146,74,0.35) + bg #D4AA6A
// Active: scale(0.98)
// Transition: all 200ms cubic-bezier(0.4,0,0.2,1)
// Props: href (string), children (ReactNode), className? (string), large? (boolean)
// Se large=true: padding 18px 48px, font-size 16px
```

#### SecondaryButton.tsx (Ghost)
```tsx
// src/components/SecondaryButton.tsx
// Fundo: transparente | Borda: 1px solid #B8924A | Texto: #B8924A
// Font: font-caps | Peso: 700 | Size: 14px | Letter-spacing: 0.06em | Uppercase
// Padding: 13px 31px | Border-radius: 50px
// Hover: bg #B8924A, texto #F5EDE4
// Transition: all 200ms ease
// Variante "--light": borda cream, texto cream / hover: bg cream, texto burgundy
// Props: href, children, variant? ('default' | 'light')
```

#### TopBar.tsx
```tsx
// src/components/TopBar.tsx
// position: fixed top-0 left-0 right-0 z-50
// Fundo: #6B1A2A | Altura: 40px | Padding: 0 48px
// Font: font-caps, 12px, peso 600, letter-spacing 0.08em, texto #F5EDE4
// Conteúdo centralizado: "✦ Encomendas abertas · Barra Mansa, RJ"
// Link à direita: "Encomendar via WhatsApp →" | cor #B8924A | hover: underline
// href do link: https://wa.me/5524993121791
// Mobile: texto reduzido "Encomendas abertas · WhatsApp →" | font-size 11px | padding 8px 20px
```

#### OrnamentoSVG.tsx
```tsx
// src/components/OrnamentoSVG.tsx
// SVG inline de flor/ornamento decorativo (6 pétalas estilizadas ou trevo ornamental)
// Props: size? (number, default 32), color? (string, default '#B8924A'), opacity? (number, default 0.18), animated? (boolean)
// Se animated=true: aplica animation: float-ornamento 6000ms ease-in-out infinite
// NÃO usar Iconify para ornamentos — SVG próprio apenas
// Sugestão de path SVG (flor de 6 pontas): M12 2 L14.5 9.5 L22 9.5 L16 14 L18.5 21.5 L12 17.5 L5.5 21.5 L8 14 L2 9.5 L9.5 9.5 Z
```

#### DivisoriaOrnamental.tsx
```tsx
// src/components/DivisoriaOrnamental.tsx
// display: flex | align-items: center | gap: 16px | max-width: 240px | mx-auto
// ::before e ::after: flex:1, height:1px, bg #B8924A, opacity 0.4
// Centro: <OrnamentoSVG size={14} color="#B8924A" opacity={0.8} />
// Props: color? ('gold' | 'cream') — ajusta cor dos elementos
```

#### useScrollReveal.ts
```tsx
// src/hooks/useScrollReveal.ts
// Intersection Observer com threshold: 0.1
// Ao entrar na viewport: adiciona classe 'is-visible' ao elemento e filhos .reveal
// Stagger: filhos com .reveal-delay-1, .reveal-delay-2, etc. recebem is-visible com delay acumulado
// Cleanup: disconnect no unmount
// Retorna: ref para attachar ao container da seção
```

---

### ÍCONES

```
npm install @iconify/react
```

```tsx
import { Icon } from '@iconify/react'
// Conjunto: solar:outline EXCLUSIVAMENTE
// Nunca lucide-react, nunca heroicons, nunca @radix-ui/react-icons
// Exemplos usados nesta página:
// solar:heart-outline | solar:pen-new-square-outline | solar:clock-circle-outline
// solar:calendar-outline | solar:chat-round-like-outline | solar:box-outline
// solar:alt-arrow-down-outline | solar:instagram-outline | solar:chat-round-outline
```

---

### ESTRUTURA DE ARQUIVOS

```
src/
  components/
    CTAButton.tsx
    SecondaryButton.tsx
    TopBar.tsx
    OrnamentoSVG.tsx
    DivisoriaOrnamental.tsx
    sections/
      Hero.tsx
      Tensao.tsx
      SobreByanca.tsx
      Diferenciais.tsx
      Catalogo.tsx
      Depoimentos.tsx
      Processo.tsx
      Galeria.tsx
      FAQ.tsx
      CTAFinal.tsx
      Footer.tsx
  hooks/
    useScrollReveal.ts
  App.tsx
  main.tsx
```

### REGRAS ABSOLUTAS

1. Copy verbatim — nunca resumir, nunca parafrasear, nunca "simplificar"
2. Wireframe é lei — layout exato, sem interpretação
3. max-w-[65ch] em TODOS os parágrafos de corpo de texto
4. Contraste mínimo 4.5:1 em texto sobre qualquer fundo
5. Touch targets mínimos 44×44px em todos os botões e links
6. Alt text real em todas as imagens — nunca "imagem" ou vazio
7. lang="pt-BR" no root do html
8. Sem header fixo de navegação, sem menu, sem footer de links de produto
9. Imagens com fundo de estúdio: filter brightness(.82) contrast(1.05) + overlay em camadas
10. Nenhuma fonte proibida em nenhum elemento

**Não crie nenhuma dobra ainda. Apenas o setup acima.**
**Confirme quando estiver pronto para a primeira dobra.**

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT 1 — TOPBAR + HERO
Cole após o Prompt 0 ter sido executado e confirmado.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Construa dois componentes: TopBar.tsx (já especificado no setup) e Hero.tsx.
Adicione ao App.tsx na seguinte ordem: <TopBar /> → <Hero />.
O body deve ter padding-top: 40px para compensar a topbar fixa.

---

### TOPBAR

Já especificada no setup. Confirme que está implementada com:
- position: fixed top-0 z-50
- bg-burgundy h-[40px] flex items-center justify-center
- Texto: font-caps text-[12px] font-semibold tracking-[0.08em] text-text-light
- Link WhatsApp com cor gold, hover underline
- href: https://wa.me/5524993121791
- Mobile: font-size 11px, padding horizontal 20px

---

### HERO — src/components/sections/Hero.tsx

#### LAYOUT

Desktop: coluna única, conteúdo centralizado, min-height: 100vh, display flex items-center justify-center
Container interno: max-w-[720px] mx-auto px-md text-center
Posição no App.tsx: segunda seção (após TopBar)

Mobile: mantém estrutura centralizada / headline clamp(36px,8vw,52px) / botões empilhados em flex-col

#### BACKGROUND

- Imagem de fundo: hero-bolo-atmosfera.jpg
- Placeholder até imagem disponível: div com bg-burgundy
- object-fit: cover / object-position: center / inset-0 absolute
- Overlay: linear-gradient(rgba(107,26,42,0.45) 0%, rgba(107,26,42,0.65) 100%)
- Grain overlay: sim — adicionar classe grain-overlay na section
  (grain apenas sobre a foto, opacity 3%)
- Ornamentos: 2x OrnamentoSVG animated=true / opacity 0.15
  - Posição 1: absolute top-[15%] right-[8%] size={48}
  - Posição 2: absolute bottom-[20%] left-[6%] size={36}
- A section precisa ter position: relative e overflow: hidden

#### COPY — use exatamente este texto

BADGE (acima do headline):
"✦ Confeitaria Artesanal · Barra Mansa ✦"
  Componente: badge outline
  Estilo: font-caps text-micro font-semibold tracking-[0.08em] uppercase
  Cor texto: text-text-light
  Borda: border border-[rgba(245,237,228,0.4)] rounded-pill px-sm py-1
  Margin bottom: mb-6

HEADLINE:
"Cada encomenda é única —
como o momento que ela celebra."
  font-family: font-heading
  font-size: clamp(52px, 6vw, 80px) (use text-hero do config)
  font-weight: 300
  font-style: italic
  line-height: 1.05
  letter-spacing: -0.01em
  color: text-text-light
  max-width: 720px / text-align: center
  margin-bottom: mb-6

SUBTÍTULO:
"Doces criados com técnica, afeto e identidade — para os momentos que merecem ser lembrados."
  font-family: font-body
  font-size: clamp(15px, 1.2vw, 17px) (text-body)
  font-weight: 400
  color: rgba(245,237,228,0.85)
  max-width: 560px / mx-auto / text-align: center
  margin-bottom: mb-10

BOTÕES (em linha, gap-4, flex-wrap justify-center):
  Botão 1: <CTAButton href="https://wa.me/5524993121791">Quero encomendar →</CTAButton>
  Botão 2: <SecondaryButton href="#catalogo" variant="light">Ver catálogo</SecondaryButton>
  Mobile: flex-col items-center

#### ANIMAÇÃO

- Conteúdo (badge + headline + subtítulo + botões): fade-in on load
  opacity: 0 → 1 / translateY: 16px → 0 / duration: 800ms / ease-elegant
  Stagger: badge (0ms), headline (150ms), subtítulo (250ms), botões (350ms)
- Ornamentos: animation float-ornamento já no componente OrnamentoSVG

#### IMAGEM

IMAGEM 1:
  Arquivo: hero-bolo-atmosfera.jpg
  Placeholder: div bg-burgundy inset-0 absolute (até imagem disponível)
  Posição: background full-width da section, absolute inset-0
  Proporção: 16:9 mínimo (1440×900px)
  Tratamento: object-fit cover + overlay duplo (gradient)
  fetchpriority="high" loading="eager" (é hero — nunca lazy)
  Mobile: object-position: center 40%

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT 2 — TENSÃO
Cole após Prompt 1 executado e confirmado.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Construa o componente Tensao.tsx em src/components/sections/Tensao.tsx.
Adicione ao App.tsx após <Hero />.

#### LAYOUT

Desktop: coluna única, conteúdo centralizado
Container: max-w-narrow (760px) mx-auto px-md text-center
Padding vertical: py-section (120px desktop / 64px mobile)

Mobile: padding 64px 24px / headline clamp(28px,6vw,40px)

#### BACKGROUND

- Cor: bg-burgundy
- Classe: grain-overlay (grain 4% opacity via CSS global)
- Sem imagem, sem grafismo adicional

#### COPY — use exatamente este texto

DIVISÓRIA acima (componente DivisoriaOrnamental, variante gold):
  margin-bottom: mb-10

HEADLINE TENSÃO:
"Você já comprou um bolo que veio errado.
Que veio seco.
Que não ficou nem de perto o que você imaginou."
  font-family: font-heading
  font-size: clamp(32px, 4vw, 48px)
  font-weight: 300
  font-style: italic
  line-height: 1.2
  color: text-text-light
  max-width: 760px / text-align: center

LINHA DE VIRADA (abaixo, margin-top: mt-8):
"Na Delicê, isso não acontece."
  font-family: font-heading
  font-size: clamp(26px, 3.2vw, 40px)
  font-weight: 300
  font-style: italic
  color: #D4AA6A (gold-light)

DIVISÓRIA abaixo (DivisoriaOrnamental, variante gold):
  margin-top: mt-10

LABEL (abaixo da divisória):
"O padrão Delicê"
  font-family: font-caps
  font-size: text-label (13px)
  font-weight: 700
  letter-spacing: 0.1em
  text-transform: uppercase
  color: gold
  margin-top: mt-4

#### ANIMAÇÃO

Reveal scroll com useScrollReveal:
  - DivisoriaOrnamental superior: reveal (base)
  - Headline tensão: reveal reveal-delay-1
  - Linha virada: reveal reveal-delay-2
  - DivisoriaOrnamental inferior: reveal reveal-delay-3
  - Label: reveal reveal-delay-4

#### IMAGENS: nenhuma (intencional)

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT 3 — SOBRE BYANCA
Cole após Prompt 2 executado e confirmado.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Construa o componente SobreByanca.tsx em src/components/sections/SobreByanca.tsx.
Adicione ao App.tsx após <Tensao />.

#### LAYOUT

Desktop: grid de 2 colunas — [480px auto] gap-[64px] items-center
  Coluna esquerda (480px): imagem retrato
  Coluna direita: badge + nome + bio + destaque + botão
Container: max-w-container (1160px) mx-auto px-md
Padding vertical: py-section

Mobile: flex-col / imagem acima (aspect-ratio 4/3) / texto abaixo / gap 32px

#### BACKGROUND

- Cor: bg-cream
- Sem grain, sem grafismo

#### COPY — use exatamente este texto

BADGE:
"Quem está por trás da Delicê"
  font-caps text-micro font-semibold tracking-[0.08em] uppercase
  color: gold / border: 1px solid gold / rounded-pill / px-3 py-1
  display: inline-block / margin-bottom: mb-4

NOME (H2):
"Byanca Costa"
  font-heading / font-size text-h2 / font-weight 300 / italic
  color: text-dark / margin-bottom: mb-5

PARÁGRAFO 1:
"Byanca Costa é confeiteira artesanal em Barra Mansa, RJ — e cada encomenda que sai da Delicê carrega o mesmo cuidado da primeira."
  font-body / text-body / font-weight 400 / color: text-dark / max-w-[55ch] / margin-bottom: mb-4

PARÁGRAFO 2:
"Formada com dedicação e aperfeiçoada na prática, Byanca desenvolveu uma identidade própria: bolos que são bonitos por fora e surpreendentes por dentro — feitos com ingredientes selecionados e atenção a cada detalhe do pedido."
  font-body / text-body / color: text-dark / max-w-[55ch] / margin-bottom: mb-6

FRASE DESTAQUE (em itálico, cor gold):
"Cada bolo nasce de uma conversa. Cada detalhe é uma intenção."
  font-heading / font-size: 22px / font-weight 300 / italic
  color: gold / max-w-[50ch] / margin-bottom: mb-8

BOTÃO:
<SecondaryButton href="#catalogo">Ver o catálogo →</SecondaryButton>

#### IMAGEM

IMAGEM 1:
  Arquivo: byanca-retrato.jpg
  Placeholder: div bg-surface rounded-md aspect-[4/5] flex items-center justify-center text-text-muted text-label — com texto "byanca-retrato.jpg"
  Posição: coluna esquerda, w-full, aspect-ratio 4/5
  Tratamento com fundo de estúdio (OBRIGATÓRIO se foto tiver fundo neutro):
    Na tag img: style={{ filter: 'brightness(0.82) contrast(1.05)' }}
    Overlay em camadas (div absolute inset-0):
      background: linear-gradient(to right, #F5EDE4 0%, rgba(245,237,228,0.55) 45%, rgba(245,237,228,0.15) 70%, transparent 100%)
    Segundo overlay:
      background: linear-gradient(to top, #F5EDE4 0%, transparent 28%)
    Terceiro overlay:
      background: linear-gradient(to bottom, rgba(245,237,228,0.4) 0%, transparent 20%)
    Cada overlay: div absolute inset-0 pointer-events-none
  border-radius: rounded-md (16px)
  box-shadow: shadow-card
  object-fit: cover
  loading="lazy"
  alt="Byanca Costa, confeiteira artesanal da Delicê em Barra Mansa, RJ"
  Mobile: aspect-ratio 4/3 (não portrait — fica melhor empilhado)

#### ANIMAÇÃO

Reveal scroll:
  - Imagem: reveal (slide from left — translateX: -24px → 0, delay 100ms)
  - Coluna texto: reveal reveal-delay-1 (slide from right — translateX: 24px → 0)
  Obs: ajuste o useScrollReveal para suportar translateX se necessário, ou use classes CSS customizadas

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT 4 — DIFERENCIAIS
Cole após Prompt 3 executado e confirmado.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Construa o componente Diferenciais.tsx em src/components/sections/Diferenciais.tsx.
Adicione ao App.tsx após <SobreByanca />.

#### LAYOUT

Desktop: headline centralizado acima + grid de 3 colunas iguais (1fr 1fr 1fr) gap-[40px]
  Cada coluna: text-align center / ícone + título + corpo
Container: max-w-container mx-auto px-md / py-section
Mobile: grid-cols-1 / gap-[40px] / py-section-mobile

#### BACKGROUND

- Cor: bg-burgundy
- Classe: grain-overlay (grain 4%)

#### COPY — use exatamente este texto

HEADLINE (acima do grid, centralizado, margin-bottom mb-[64px]):
"O que faz cada Delicê ser única"
  font-heading / text-h2 / font-weight 300 / italic / color: text-light

BLOCO 1 — Ícone: solar:heart-outline (32px, #B8924A)
  Título: "Ingredientes selecionados"
    font-caps / text-h3 / font-weight 600 / color: text-light / mt-4 mb-3
  Corpo: "Cada receita usa matéria-prima escolhida com critério — porque o sabor começa antes de qualquer técnica."
    font-body / 15px / color: rgba(245,237,228,0.75) / max-w-[36ch] / mx-auto

BLOCO 2 — Ícone: solar:pen-new-square-outline (32px, #B8924A)
  Título: "Cada detalhe personalizado"
    [mesmas especificações tipográficas]
  Corpo: "Não existe encomenda genérica na Delicê. Cada pedido começa por uma conversa — e termina exatamente como você imaginou."

BLOCO 3 — Ícone: solar:clock-circle-outline (32px, #B8924A)
  Título: "Entrega no prazo, sempre"
    [mesmas especificações]
  Corpo: "Pontualidade faz parte do produto. Você organiza seu evento sem precisar se preocupar com o bolo."

Ícones: <Icon icon="solar:[nome]-outline" width={32} style={{ color: '#B8924A', display: 'block', margin: '0 auto 16px' }} />

#### ANIMAÇÃO

Reveal scroll com stagger nos 3 blocos:
  Bloco 1: reveal (delay 0)
  Bloco 2: reveal reveal-delay-1 (delay 150ms)
  Bloco 3: reveal reveal-delay-2 (delay 300ms)
  Headline: reveal (aplicado separado, antes do grid)

#### IMAGENS: nenhuma

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT 5 — CATÁLOGO PREVIEW
Cole após Prompt 4 executado e confirmado.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Construa o componente Catalogo.tsx em src/components/sections/Catalogo.tsx.
Adicione ao App.tsx após <Diferenciais />. Adicione id="catalogo" na section.

#### LAYOUT

Desktop: headline centralizado + grid 3 colunas (repeat(3,1fr)) gap-[24px] + botão centralizado abaixo
Container: max-w-container mx-auto px-md / py-section
Mobile: grid-cols-1 / botão full-width

#### BACKGROUND

- Cor: bg-cream
- Cards: bg-surface (FAF3EE)
- Sem grain

#### COPY — use exatamente este texto

BADGE (acima do headline, centralizado):
"✦ Nosso Catálogo ✦"
  font-caps / text-micro / font-semibold / tracking-[0.08em] / uppercase / color: gold
  border: 1px solid gold / rounded-pill / px-3 py-1 / inline-block / mb-4

HEADLINE:
"Feito para o seu momento"
  font-heading / text-h2 / font-weight 300 / italic / color: text-dark / text-center / mb-[56px]

CARD 1:
  Imagem: catalogo-bolos-artisticos.jpg (placeholder proporcional aspect-[4/3])
  Label: "BOLOS ARTÍSTICOS"
    font-caps / text-label / font-semibold / tracking-[0.08em] / uppercase / color: gold / mb-2
  Título: "Para os grandes momentos"
    font-heading / 22px / font-weight 400 / italic / color: text-dark / mb-3
  Corpo: "Bolos artísticos personalizados, do design ao sabor — criados para que o bolo seja tão lembrado quanto o evento."
    font-body / 14px / color: text-muted / max-w-[40ch]

CARD 2:
  Imagem: catalogo-doces-bombons.jpg (placeholder proporcional aspect-[4/3])
  Label: "DOCES & BOMBONS"
  Título: "Presentes que falam por você"
  Corpo: "Bombons recheados, camafeus e caixas de doces gourmet — para presentear com intenção e sem complicação."

CARD 3:
  Imagem: catalogo-sobremesas-taca.jpg (placeholder proporcional aspect-[4/3])
  Label: "SOBREMESAS NA TAÇA"
  Título: "Delicadeza em formato de porção"
  Corpo: "Sobremesas individuais para eventos, brunch ou presente especial — praticidade sem abrir mão do artesanal."

ESTRUTURA DE CADA CARD:
  bg-surface / rounded-md / overflow-hidden / shadow-card
  Hover: hover:translate-y-[-4px] hover:shadow-hover / transition-all duration-[400ms] ease-elegant
  Imagem: w-full aspect-[4/3] object-cover (topo do card, sem border-radius próprio)
  Corpo do card: p-[20px_24px_24px]

BOTÃO (centralizado, margin-top mt-[48px]):
<CTAButton href="https://wa.me/5524993121791">Ver catálogo completo →</CTAButton>

#### IMAGENS

IMAGEM 1: catalogo-bolos-artisticos.jpg
  Placeholder: div bg-[#EDE0D4] aspect-[4/3] flex items-center justify-center text-text-muted text-xs — "catalogo-bolos-artisticos.jpg"
  loading="lazy" / alt="Bolo artístico personalizado da Delicê Confeitaria em Barra Mansa"

IMAGEM 2: catalogo-doces-bombons.jpg
  Placeholder similar / alt="Bombons e doces gourmet da Delicê Confeitaria"

IMAGEM 3: catalogo-sobremesas-taca.jpg
  Placeholder similar / alt="Sobremesas na taça da Delicê Confeitaria artesanal"

#### ANIMAÇÃO

Cards: stagger reveal
  Card 1: reveal (0ms)
  Card 2: reveal reveal-delay-1 (150ms)
  Card 3: reveal reveal-delay-2 (300ms)
  Hover: translateY(-4px) + shadow-hover / duration 400ms

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT 6 — DEPOIMENTOS
Cole após Prompt 5 executado e confirmado.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Construa o componente Depoimentos.tsx em src/components/sections/Depoimentos.tsx.
Adicione ao App.tsx após <Catalogo />.

#### LAYOUT

Desktop: coluna única centralizada / max-w-narrow (760px) mx-auto px-md
  Cards de depoimento em flex-col gap-[24px]
  Padding: py-section
Mobile: py-section-mobile / padding horizontal 24px

#### BACKGROUND

- Cor: bg-burgundy
- Classe: grain-overlay

#### COPY — use exatamente este texto

BADGE:
"✦ O que dizem sobre a Delicê ✦"
  font-caps / text-micro / font-semibold / tracking-[0.08em] / uppercase
  color: text-light / border: 1px solid rgba(245,237,228,0.35) / rounded-pill / px-3 py-1
  inline-block / mb-8 / text-center

HEADLINE:
"Cada encomenda importa. Cada cliente volta."
  font-heading / text-h2 / font-weight 300 / italic / color: text-light / text-center / mb-[56px]

CARD DE DEPOIMENTO (estrutura — repetir para 2–3 depoimentos):
  Fundo: bg-[rgba(245,237,228,0.06)]
  Borda: border border-[rgba(184,146,74,0.2)] rounded-[12px]
  Padding: p-[32px_36px]

  Aspas SVG (canto superior esquerdo do card):
    SVG inline: " (guillemet aberto estilizado ou aspas curvas)
    Tamanho: 36px / Cor: #B8924A / margin-bottom: mb-4
    Sugestão de path: aspas tipográficas "curly quotes" em SVG, não elemento HTML

  Texto do depoimento:
    [PLACEHOLDER — aguardando conteúdo de Byanca]
    "Este é o espaço reservado para o depoimento real de uma cliente da Delicê. Adicionar após coleta com Byanca Costa."
    font-heading / 18px / italic / font-weight 300 / color: text-light / line-height 1.7 / max-w-[65ch]

  Assinatura (abaixo do texto, margin-top mt-5):
    "— Nome da Cliente · Ocasião"
    font-caps / 12px / font-weight 600 / tracking-[0.08em] / color: gold

  Nota visual: O card com placeholder deve ter opacity: 0.6 para indicar que é provisório.
  Criar 2 cards com o mesmo placeholder para estabelecer o layout.

#### ANIMAÇÃO

Cards: stagger reveal / fade-up
  Card 1: reveal (0ms)
  Card 2: reveal reveal-delay-1 (150ms)

#### IMAGENS

IMAGEM OPCIONAL — prints de WhatsApp (se Byanca fornecer):
  Arquivo: depoimento-print-wpp-01.jpg
  Posição: dentro do card, abaixo do texto / max-width 280px / rounded-sm
  alt: "Print de mensagem de cliente satisfeita da Delicê Confeitaria"
  Manter como comentário no código até conteúdo disponível

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT 7 — PROCESSO (COMO FUNCIONA)
Cole após Prompt 6 executado e confirmado.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Construa o componente Processo.tsx em src/components/sections/Processo.tsx.
Adicione ao App.tsx após <Depoimentos />.

#### LAYOUT

Desktop: headline centralizado + grid 3 colunas (1fr 1fr 1fr) + linha conectora entre passos
  Linha conectora: pseudoelemento horizontal em gold (opacity 0.3) entre os centros dos passos
  Implementar via: div absolute com border-top 1px dotted #B8924A, top alinhado ao centro dos números, z-index 0
  Container: max-w-container mx-auto px-md / py-section
  Cada coluna: text-align center / position relative / z-index 1

Mobile: flex-col / linha conectora vertical (border-left 1px dotted gold, à esquerda de cada passo)
  Cada passo: flex items-start gap-4 / linha à esquerda

#### BACKGROUND

- Cor: bg-cream
- Sem grain

#### COPY — use exatamente este texto

BADGE:
"✦ Como funciona ✦"
  font-caps / text-micro / tracking-[0.08em] / uppercase / color: gold
  border gold / rounded-pill / px-3 py-1 / inline-block / mb-4 / text-center

HEADLINE:
"Encomendar é simples"
  font-heading / text-h2 / font-weight 300 / italic / color: text-dark / text-center / mb-[64px]

PASSO 1:
  Número: "01"
    font-heading / 72px / italic / font-weight 300 / color: gold / opacity: 0.18
    position: absolute acima do ícone (z-index -1, offset negativo top)
  Ícone: solar:calendar-outline / 32px / #B8924A / display block mx-auto mb-4
  Título: "Escolha seu momento"
    font-caps / text-h3 / font-weight 600 / color: text-dark / mb-3
  Corpo: "Aniversário, casamento, chá de bebê, presente — me conta o que está planejando e o que você imagina."
    font-body / 15px / color: text-muted / max-w-[32ch] / mx-auto

PASSO 2:
  Número: "02" (mesmas specs)
  Ícone: solar:chat-round-like-outline / 32px / #B8924A
  Título: "Envie sua encomenda"
  Corpo: "Entre em contato pelo WhatsApp com a data do evento, o tipo de bolo e o número de convidados."
    [mesma tipografia]
  Link inline após o corpo: "Falar com Byanca →"
    font-caps / 13px / font-semibold / color: gold / hover: underline / tracking-[0.06em]
    href: https://wa.me/5524993121791

PASSO 3:
  Número: "03" (mesmas specs)
  Ícone: solar:box-outline / 32px / #B8924A
  Título: "Receba com perfeição"
  Corpo: "Seu bolo chega exatamente como você pediu — no prazo, bonito, gostoso, pronto para o seu momento."

#### ANIMAÇÃO

Stagger nos 3 passos:
  Passo 1: reveal (0ms)
  Passo 2: reveal reveal-delay-1 (200ms)
  Passo 3: reveal reveal-delay-2 (400ms)
  Linha conectora: width 0% → 100% / transition 800ms ease-smooth / triggered junto com os passos

#### IMAGENS: nenhuma obrigatória

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT 8 — GALERIA
Cole após Prompt 7 executado e confirmado.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Construa o componente Galeria.tsx em src/components/sections/Galeria.tsx.
Adicione ao App.tsx após <Processo />. Adicione id="galeria" na section.

#### LAYOUT

Desktop: CSS Grid assimétrico
  grid-template-columns: 2fr 1fr 1fr
  grid-template-rows: auto auto
  gap: 12px
  
  Posicionamento das imagens:
  - detalhe-decoracao.jpg: coluna 1 / row 1-2 (grid-row: span 2) — imagem grande vertical
  - detalhe-corte.jpg: coluna 2 / row 1 — quadrada
  - ambiente-mesa.jpg: coluna 3 / row 1 — 16:9
  - bastidores-maos.jpg: colunas 2-3 / row 2 (grid-column: span 2) — horizontal

Container: max-w-container mx-auto px-md / py-[80px]
Cada imagem: overflow-hidden rounded-[12px] / w-full h-full object-cover
Hover: scale(1.02) + overlay rgba(184,146,74,0.2) / transition-all duration-[400ms] ease-elegant

Mobile: grid-cols-1 / todas empilhadas / aspect-[16/9] each / gap-3

#### BACKGROUND

- Cor: bg-cream
- Hover: overlay gold sobre cada foto

#### COPY — use exatamente este texto

HEADLINE (centralizado, acima do grid):
"Cada detalhe é intencional"
  font-heading / text-h2 / font-weight 300 / italic / color: text-dark / text-center / mb-[48px]

#### IMAGENS

Implementar cada imagem como wrapper div (position relative overflow-hidden rounded-[12px]) + img interna + overlay div absoluta para o hover:

IMAGEM 1 — detalhe-decoracao.jpg:
  Placeholder: div bg-[#DDD0C4] flex items-center justify-center text-xs text-text-muted — "detalhe-decoracao.jpg"
  grid-row: span 2 / aspect-[2/3] mínimo no desktop / h-full object-cover
  loading="lazy" / alt="Detalhe de decoração artesanal em bolo da Delicê — açúcar, flores e dourado"
  Overlay hover: div absolute inset-0 bg-[rgba(184,146,74,0.2)] opacity-0 hover:opacity-100 transition-opacity duration-400

IMAGEM 2 — detalhe-corte.jpg:
  Placeholder: bg-[#D4C8BE] — "detalhe-corte.jpg"
  aspect-[1/1] / object-cover / object-position: center
  alt="Corte de bolo Delicê mostrando camadas de recheio artesanal"

IMAGEM 3 — ambiente-mesa.jpg:
  Placeholder: bg-[#CBBFB5] — "ambiente-mesa.jpg"
  aspect-[16/9] / object-cover
  alt="Mesa de evento decorada com doces e bolo artesanal da Delicê"

IMAGEM 4 — bastidores-maos.jpg:
  Placeholder: bg-[#BFB4AC] — "bastidores-maos.jpg"
  aspect-[16/9] / object-cover / grid-column: span 2 no desktop
  alt="Mãos de Byanca decorando bolo artesanal — bastidores da Delicê Confeitaria"

Todas: loading="lazy" decoding="async"

#### ANIMAÇÃO

Stagger reveal no grid:
  Imagem 1: reveal (0ms)
  Imagem 2: reveal reveal-delay-1 (100ms)
  Imagem 3: reveal reveal-delay-2 (200ms)
  Imagem 4: reveal reveal-delay-3 (300ms)

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT 9 — FAQ
Cole após Prompt 8 executado e confirmado.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Construa o componente FAQ.tsx em src/components/sections/FAQ.tsx.
Adicione ao App.tsx após <Galeria />.

#### LAYOUT

Desktop + Mobile: coluna única centralizada
  Container: max-w-tight (720px) mx-auto px-md / py-section
  Accordion: flex-col / cada item com border-bottom 1px solid rgba(184,146,74,0.3)

#### BACKGROUND

- Cor: bg-burgundy
- Classe: grain-overlay

#### COPY — use exatamente este texto

HEADLINE:
"Dúvidas frequentes"
  font-heading / text-h2 / font-weight 300 / italic / color: text-light / text-center / mb-[56px]

PERGUNTAS E RESPOSTAS (accordion — 5 itens):

  Item 1:
  Pergunta: "Qual o prazo mínimo para encomendar?"
  Resposta: "[A confirmar com Byanca — prazo mínimo de antecedência para encomendas]"
  Placeholder visual: texto em itálico, opacity 0.5

  Item 2:
  Pergunta: "Vocês entregam em Barra Mansa e região?"
  Resposta: "[A confirmar com Byanca — cidades e bairros atendidos, política de entrega]"

  Item 3:
  Pergunta: "Como funciona o pagamento e o sinal?"
  Resposta: "[A confirmar com Byanca — forma de pagamento, valor do sinal, prazo]"

  Item 4:
  Pergunta: "Posso personalizar completamente o bolo?"
  Resposta: "Sim. Cada encomenda começa por uma conversa — você me conta o que imagina, a data, o número de convidados e qualquer referência visual que tiver. Trabalhamos juntas até o resultado ser exatamente o que você queria."

  Item 5:
  Pergunta: "E se eu não souber exatamente o que quero?"
  Resposta: "Sem problema. Me manda uma mensagem com a data e o tipo de evento. A partir daí, eu te ajudo a construir a ideia — isso faz parte do processo da Delicê."

ESTRUTURA DE CADA ITEM DO ACCORDION:
  Wrapper: div com border-bottom border-[rgba(184,146,74,0.3)]
  Header (button): flex items-center justify-between / py-5 / w-full / cursor-pointer
    Pergunta: font-body / 17px / font-weight 400 / color: text-light / text-left
    Ícone: <Icon icon="solar:alt-arrow-down-outline" width={20} color="#B8924A" />
    Ícone quando aberto: rotate-180 / transition transform 300ms ease-smooth
  Resposta (div colapsável):
    Overflow hidden / max-height: 0 → max-height: 500px (com CSS transition 300ms ease-smooth)
    Conteúdo: font-body / 15px / color: rgba(245,237,228,0.8) / pb-5 / max-w-[65ch]
  Implementar com useState para controlar qual item está aberto
  aria-expanded no button / id no painel / aria-controls para acessibilidade

#### ANIMAÇÃO

- Accordion: max-height transition 300ms ease-smooth (não display:none — quebra a transição)
- Ícone: transform rotate 0 → 180deg / 300ms
- Reveal scroll: toda a seção (não stagger por item — accordion já tem interação)

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT 10 — CTA FINAL
Cole após Prompt 9 executado e confirmado.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Construa o componente CTAFinal.tsx em src/components/sections/CTAFinal.tsx.
Adicione ao App.tsx após <FAQ />.

#### LAYOUT

Desktop + Mobile: coluna única, conteúdo centralizado
  Container: max-w-intimate (640px) mx-auto px-md / text-center
  Padding: py-[120px] desktop / py-[80px] mobile

#### BACKGROUND

- Cor base: bg-cream
- Gradiente sutil: linear-gradient(to bottom, #F5EDE4 60%, rgba(184,146,74,0.06) 100%)
- Aplicar via style no elemento section
- Sem grain

#### COPY — use exatamente este texto

ORNAMENTO (centralizado, margin-bottom mb-8):
  <OrnamentoSVG size={40} color="#B8924A" opacity={0.6} animated={false} />

HEADLINE:
"Pronta para criar juntas?"
  font-heading / font-size clamp(36px,4.5vw,56px) / font-weight 300 / italic
  color: text-dark / text-center / mb-6

CORPO:
"Entre em contato pelo WhatsApp e vamos criar juntas o bolo perfeito para o seu momento."
  font-body / 17px / color: text-dark / opacity: 0.7 / text-center / max-w-[50ch] / mx-auto / mb-10

BOTÃO (centralizado, display block mx-auto):
<CTAButton href="https://wa.me/5524993121791" large={true}>
  Falar com Byanca no WhatsApp →
</CTAButton>

NOTA ABAIXO DO BOTÃO (margin-top mt-4):
"Resposta em até 24h · Barra Mansa, RJ"
  font-caps / text-micro / color: text-muted / text-center

#### ANIMAÇÃO

Reveal scroll (toda a dobra como unidade):
  opacity 0 → 1 / translateY 24px → 0 / 700ms / ease-elegant
  Botão: após entrar na viewport — animation: pulse-cta 0.6s ease-out 800ms 1 forwards
  (chama atenção uma vez, não repetitivo)

#### IMAGENS: nenhuma

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT 11 — FOOTER
Cole após Prompt 10 executado e confirmado.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Construa o componente Footer.tsx em src/components/sections/Footer.tsx.
Adicione ao App.tsx como último elemento.

#### LAYOUT

Desktop: grid 3 colunas (1.5fr 1fr 1fr) / gap-[40px] / items-start
  Container: max-w-container mx-auto px-md / pt-[56px] pb-[40px]
  Rodapé mínimo: borda top + linha de copyright centralizada abaixo do grid

Mobile: flex-col / gap-[32px] / text-align center

#### BACKGROUND

- Cor: bg-burgundy
- Classe: grain-overlay

#### COPY — use exatamente este texto

COLUNA 1 (marca):
  Logo/monograma: "DELICÊ" em font-caps / 24px / font-semibold / tracking-[0.12em] / color: text-light
  Subtítulo: "Confeitaria Artesanal"
    font-caps / text-micro / tracking-[0.08em] / color: gold / mt-1
  Texto: "Barra Mansa · Rio de Janeiro"
    font-body / 13px / color: rgba(245,237,228,0.5) / mt-2

COLUNA 2 (links):
  Título da coluna: "Navegação" — font-caps / text-micro / tracking-[0.08em] / color: gold / mb-3
  Links (cada em linha separada):
    "Sobre Byanca" → âncora seção SobreByanca
    "Catálogo" → #catalogo
    "Como Encomendar" → âncora seção Processo
  Estilo dos links: font-body / 14px / color: rgba(245,237,228,0.65) / hover: color text-light / transition 200ms

COLUNA 3 (redes):
  Título: "Contato" — mesmas specs da coluna 2
  Ícones (flex gap-4 mt-3):
    Instagram: <Icon icon="solar:instagram-outline" width={24} color="#B8924A" />
      href: https://instagram.com/[handle — a confirmar com Byanca]
      Hover: opacity 0.7 / transition 200ms
    WhatsApp: <Icon icon="solar:chat-round-outline" width={24} color="#B8924A" />
      href: https://wa.me/5524993121791

RODAPÉ MÍNIMO (abaixo do grid, borda-top: 1px solid rgba(245,237,228,0.12), padding-top: pt-6, text-center):
"© 2024 Delicê Confeitaria · Byanca Costa · Barra Mansa, RJ"
  font-caps / text-micro / color: rgba(245,237,228,0.4)

#### ANIMAÇÃO: nenhuma (footer não precisa de reveal)

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## PROMPT FINAL — VERIFICAÇÃO GLOBAL
Cole após TODAS as dobras terem sido construídas e confirmadas.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Faça uma revisão completa da página e corrija qualquer item fora do especificado:

**TIPOGRAFIA**
- [ ] Nenhuma instância de Inter, Poppins, Roboto, Arial ou font-sans padrão em qualquer elemento
- [ ] Todos os títulos: font-heading (Cormorant Garamond) italic weight 300
- [ ] Labels e badges: font-caps (Cormorant SC) uppercase
- [ ] Todos os parágrafos de corpo: max-w-[65ch] / line-height 1.75
- [ ] Hierarquia H1→H2→H3→body respeitada em toda a página

**CORES**
- [ ] Nenhuma cor fora da paleta definida no tailwind.config
- [ ] Alternância cream/burgundy respeitada conforme o mapa de backgrounds
- [ ] Nenhum gradiente roxo, azul ou genérico de template
- [ ] CTAs sempre bg-gold text-cream

**ÍCONES**
- [ ] 100% Iconify solar:outline — zero Lucide em qualquer componente
- [ ] Tamanho consistente por categoria (32px nos diferenciais/processo, 24px no footer)

**COMPORTAMENTOS**
- [ ] Topbar fixa aparece em todas as páginas sem cobrir o conteúdo (body tem padding-top: 40px)
- [ ] FAQ accordion funciona com aria-expanded / transição max-height (não display:none)
- [ ] Scroll suave ativado (html { scroll-behavior: smooth; })
- [ ] Todos os botões com hover translateY(-1px) + shadow
- [ ] Ornamentos no hero animados (float-ornamento)

**MOBILE**
- [ ] Nenhuma dobra com overflow horizontal
- [ ] Todos os textos legíveis — nenhum cortado ou ilegível
- [ ] Touch targets mínimos 44×44px em todos os CTAs
- [ ] Grid galeria simplificado para 1 coluna (sem assimetria em mobile)
- [ ] Imagem byanca-retrato muda para aspect-[4/3] em mobile

**IMAGENS**
- [ ] Todas as imagens com alt text real e específico
- [ ] Hero: fetchpriority="high" loading="eager" (nunca lazy)
- [ ] Demais: loading="lazy" decoding="async"
- [ ] Placeholders nomeados com nome exato do arquivo (sem "image1.jpg" ou similar)
- [ ] Wrapper da byanca-retrato.jpg com filter brightness(.82) contrast(1.05) + overlay em 3 camadas

**GRAIN**
- [ ] grain-overlay apenas nas seções burgundy (Topbar, Tensão, Diferenciais, Depoimentos, FAQ, Footer)
- [ ] Seções cream sem grain
- [ ] Conteúdo das seções com grain tem z-index maior que o ::after do grain

**ACESSIBILIDADE**
- [ ] lang="pt-BR" no root html
- [ ] Contraste verificado — texto cream sobre burgundy: 8.5:1 ✓ / texto dark sobre cream: 7.2:1 ✓
- [ ] Focus visible em todos os botões e links

---

## TEMPLATES DE CORREÇÃO

### Tipografia com fonte errada
```
No componente [NomeDaDobra], corrija a tipografia:
Todos os títulos (H1/H2/H3): className deve incluir font-heading — que é 'Cormorant Garamond', Georgia, serif
Todos os labels e badges: font-caps — que é 'Cormorant SC', Georgia, serif
Corpo de texto: font-body — que é 'Cormorant Garamond', Georgia, serif
Remova qualquer referência a font-sans, Inter, Poppins ou Roboto.
```

### Ícone Lucide detectado
```
Substitua todos os ícones Lucide por Iconify no componente [NomeDaDobra]:
import { Icon } from '@iconify/react'
Substituições:
  Check → solar:check-circle-outline
  ArrowRight → solar:arrow-right-outline
  ChevronDown → solar:alt-arrow-down-outline
  Heart → solar:heart-outline
  Clock → solar:clock-circle-outline
  [adaptar conforme os ícones encontrados]
```

### Overlay de foto com fundo de estúdio incorreto
```
Na imagem byanca-retrato.jpg no componente SobreByanca:
O overlay simples com opacity não funciona para fundo de estúdio — o fundo neutro "sangra".
Implemente assim:
1. Na tag img: style={{ filter: 'brightness(0.82) contrast(1.05)' }}
2. Três divs absolutas sobrepostas (não uma só):
   Div 1: background: 'linear-gradient(to right, #F5EDE4 0%, rgba(245,237,228,0.55) 45%, rgba(245,237,228,0.15) 70%, transparent 100%)'
   Div 2: background: 'linear-gradient(to top, #F5EDE4 0%, transparent 28%)'
   Div 3: background: 'linear-gradient(to bottom, rgba(245,237,228,0.4) 0%, transparent 20%)'
   Cada div: className="absolute inset-0 pointer-events-none"
```

### Adição de imagem real (após Freepik)
```
No componente [NomeDaDobra], substitua o placeholder de [nome-exato.jpg]:
1. Adicione o arquivo em /public/images/[nome-exato.jpg]
2. Substitua a div placeholder por:
<img
  src="/images/[nome-exato.jpg]"
  alt="[descrição exata especificada acima]"
  loading="lazy"
  decoding="async"
  className="w-full h-full object-cover"
/>
Não altere nenhum outro elemento do componente.
```
