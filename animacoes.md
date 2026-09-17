# ANIMACOES.md — MUSEU NOCTURNE
## Motion DNA / Dark Romantic Archival Editorial

> Motion system derivado da linguagem visual das referências e do
> DESIGN.md da landing page do museu.
>
> STATUS DA EVIDÊNCIA:
>
> OBSERVED:
> composição, hierarquia, fotografia, textura, tipografia,
> ornamentação, metadata, sobreposição e materialidade.
>
> INFERRED:
> comportamento temporal coerente com esses elementos.
>
> RECOMMENDED:
> timings, easing, triggers, implementação, thresholds e estados.
>
> As referências são estáticas. Portanto nenhuma animação descrita
> neste documento deve ser tratada como comportamento originalmente
> observado.

---

# 0. MOTION NORTH STAR

O movimento deve parecer:

ARCHIVAL
SLOW
TACTILE
EDITORIAL
CINEMATIC
PRECISE
QUIET
PHYSICAL

A landing page não deve parecer uma interface animada.

Ela deve parecer um objeto editorial que está sendo:

- revelado;
- folheado;
- exposto;
- catalogado;
- descoberto;
- iluminado;
- enquadrado;
- consultado.

A metáfora principal é:

> O visitante não navega por componentes.
> Ele atravessa um arquivo que lentamente revela suas peças.

---

# 1. MOTION DNA

## 1.1 Fórmula

```txt
MOTION DNA =

SLOW PHOTOGRAPHIC REVEAL
+
TYPOGRAPHIC MASKING
+
ARCHIVAL DATA APPEARANCE
+
HAIRLINE DRAWING
+
CONTROLLED PARALLAX
+
SUBTLE MATERIAL DRIFT
+
EDITORIAL SECTION TRANSITIONS
+
NEAR-STATIC MICROINTERACTIONS
2. MOTION PRINCIPLES
2.1 REVEAL > FLY-IN

Elementos não devem parecer que "entram na tela".

Eles devem parecer que estavam lá e foram revelados.

PREFERIR:

clip-path;
mask;
opacity;
exposure;
line drawing;
crop reveal.

EVITAR:

translateY(80px);
fly-in lateral;
bounce;
spring;
zoom dramático.
2.2 DEPTH > DECORATIVE MOTION

Movimento deve reforçar profundidade.

Exemplo:

foreground typography
move pouco

photography
move muito lentamente

background texture
quase imóvel

metadata
static/reveal only

Isso cria camadas.

2.3 ASYNCHRONY > EVERYTHING AT ONCE

Não revelar todos os elementos simultaneamente.

Sequência recomendada:

PHOTO
↓
INDEX
↓
DISPLAY
↓
SCRIPT
↓
RULE
↓
METADATA
↓
CTA

A diferença entre cada evento pode ser pequena:

60–180ms.

2.4 MATERIAL > DIGITAL

Movimento deve lembrar:

exposição fotográfica;
impressão;
página;
película;
obturador;
scanner;
catalogação.

Não lembrar:

app mobile;
dashboard;
videogame;
apresentação PowerPoint.
2.5 REST IS PART OF MOTION

A maior parte da interface deve permanecer parada.

Regra:

~80–90% STATIC
~10–20% TEMPORALLY ACTIVE

Não manter várias animações contínuas simultaneamente.

3. GLOBAL MOTION TOKENS
:root {
  /* DURATION */
  --motion-instant: 120ms;
  --motion-fast: 240ms;
  --motion-base: 400ms;
  --motion-reveal: 700ms;
  --motion-slow: 1000ms;
  --motion-cinematic: 1400ms;

  /* STAGGER */
  --stagger-tight: 50ms;
  --stagger-base: 90ms;
  --stagger-editorial: 140ms;

  /* EASING */
  --ease-out-editorial:
    cubic-bezier(.22,.61,.36,1);

  --ease-out-expo:
    cubic-bezier(.16,1,.3,1);

  --ease-in-out-soft:
    cubic-bezier(.65,0,.35,1);

  --ease-linear:
    linear;

  /* PARALLAX */
  --parallax-micro: 8px;
  --parallax-small: 16px;
  --parallax-medium: 32px;

  /* IMAGE */
  --image-hover-scale: 1.018;

  /* Z */
  --z-photo: 10;
  --z-display: 20;
  --z-script: 25;
  --z-meta: 30;
  --z-grain: 40;
}
4. MOTION HIERARCHY

Existem quatro níveis.

LEVEL 1 — CINEMATIC

Usar somente em momentos principais.

hero;
artwork reveal;
section transition;
large photography.

Duration:

700–1400ms.

LEVEL 2 — EDITORIAL
títulos;
linhas;
quotations;
ornaments;
section indices.

Duration:

400–800ms.

LEVEL 3 — INFORMATIONAL
metadata;
captions;
dates;
archive IDs.

Duration:

200–500ms.

LEVEL 4 — INTERACTION
links;
navigation;
hover;
focus.

Duration:

120–280ms.

5. PAGE ENTRY

Ao carregar a landing page, evitar splash screen.

A própria hero funciona como abertura.

Sequência:

0ms
background already visible

100ms
photography exposure starts

300ms
archive number appears

400ms
hero display starts reveal

550ms
second title line starts

700ms
script begins appearing

800ms
hairline draws

900ms
metadata begins

1050ms
CTA appears

1200–1400ms
composition reaches rest

Tempo máximo recomendado até interface funcional:

~1.4s.

Navigation deve permanecer utilizável durante a sequência.

6. HERO PHOTOGRAPHY — EXPOSURE REVEAL

A fotografia não deve simplesmente fazer:

opacity: 0 → 1.

Adicionar transformação de exposição/crop.

Initial:

.hero-image {
  opacity: 0;
  transform: scale(1.025);
  filter:
    brightness(.72)
    contrast(1.08);
}

Final:

.hero-image.is-visible {
  opacity: 1;
  transform: scale(1);
  filter:
    brightness(.92)
    contrast(1.03);

  transition:
    opacity 1000ms var(--ease-out-editorial),
    transform 1400ms var(--ease-out-expo),
    filter 1200ms var(--ease-out-editorial);
}

Sensação:

A fotografia está sendo revelada em uma sala escura.

Não:

imagem "popando" para dentro.

7. HERO IMAGE MASK

Alternativa de maior fidelidade:

.hero-media {
  clip-path: inset(0 0 100% 0);
}

.hero-media.is-visible {
  clip-path: inset(0 0 0 0);

  transition:
    clip-path 1100ms var(--ease-out-expo);
}

Preferência:

reveal vertical ou diagonal muito sutil.

Evitar wipes digitais excessivamente perfeitos.

8. HERO DISPLAY TYPOGRAPHY

Título:

THE
MEMORY
OF THINGS

Cada linha deve ser mascarada individualmente.

HTML:

<h1 class="hero-title">
  <span class="line-mask">
    <span>THE</span>
  </span>

  <span class="line-mask">
    <span>MEMORY</span>
  </span>

  <span class="line-mask">
    <span>OF THINGS</span>
  </span>
</h1>

CSS:

.line-mask {
  display: block;
  overflow: hidden;
}

.line-mask > span {
  display: block;

  transform:
    translateY(105%);

  transition:
    transform
    850ms
    var(--ease-out-expo);
}

Stagger:

THE       0ms
MEMORY   90ms
OF THINGS 180ms

O movimento vertical interno pode ser grande porque fica escondido
pela máscara.

Visualmente o texto parece impresso/revelado.

9. SCRIPT INTERFERENCE

A palavra manuscrita:

mémoire

não deve entrar junto do título.

Delay recomendado:

200–350ms depois do display principal.

Preferir:

opacity;
clipping;
stroke reveal se SVG/custom lettering.

Exemplo:

.script-overlay {
  opacity: 0;
  clip-path: inset(0 100% 0 0);
}

.script-overlay.is-visible {
  opacity: .92;
  clip-path: inset(0 0 0 0);

  transition:
    clip-path 900ms var(--ease-out-editorial),
    opacity 500ms ease;
}

A sensação deve ser:

alguém escreveu sobre o catálogo.

Não:

logo animado.

10. ARCHIVE INDEX REVEAL

Exemplo:

034
CURRENT EXHIBITION

Animação:

opacity 0 → 1
translateY 4px → 0
duration 320ms

Nunca mais de 8px de deslocamento.

Metadata deve parecer precisa e quase estática.

11. HAIRLINE DRAWING

Motif:

────────── ◆ ──────────

Construir em HTML/SVG.

Animação:

.archive-rule::before,
.archive-rule::after {
  transform: scaleX(0);
}

.archive-rule.is-visible::before,
.archive-rule.is-visible::after {
  transform: scaleX(1);

  transition:
    transform
    650ms
    var(--ease-out-editorial);
}

Origins:

linha esquerda:

transform-origin: right;

linha direita:

transform-origin: left;

Resultado:

as linhas encontram o diamond central.

12. BOTANICAL ORNAMENT REVEAL

Motif:

✣ ✣ ✣ ✣

Não fazer os símbolos pularem.

Usar stagger de opacity.

✣  0ms
✣  80ms
✣ 160ms
✣ 240ms

Cada símbolo:

opacity 0 → 1
scale .96 → 1
duration 400ms

Scale é quase imperceptível.

13. HERO PARALLAX

Parallax deve ser mínimo.

Camadas:

BACKGROUND
0px

PHOTO
-12px → +12px

DISPLAY
-4px → +4px

SCRIPT
-8px → +8px

METADATA
0px

Metadata permanece quase estática.

Isso é importante:

O sistema gráfico funciona como placa de catalogação enquanto
a fotografia possui profundidade.

14. SCROLL-LINKED HERO

Quando usuário começa a sair da hero:

0–30% hero scroll:
composition intact

30–70%:
image drifts ~12–20px
display drifts ~4–8px
script opacity .9 → .65

70–100%:
metadata remains
hero begins disappearing
next section emerges

Não usar:

scale 1 → 2
rotation
3D perspective
large zoom
pinning for 5 screens
15. GRAIN MOTION

Grain não deve ficar completamente imóvel se o objetivo for
simular material fotográfico.

Mas movimento deve ser praticamente subliminar.

Recommended:

@keyframes archive-grain {
  0%   { transform: translate(0,0); }
  25%  { transform: translate(-1%,1%); }
  50%  { transform: translate(1%,-1%); }
  75%  { transform: translate(.5%,1%); }
  100% { transform: translate(0,0); }
}

Duration:

150–300ms.

IMPORTANTE:

Não executar continuamente.

Usar ocasionalmente:

short burst
↓
long pause
↓
short burst

Por exemplo:

150ms de movimento a cada 4–8 segundos.

Melhor ainda:

usar sprite/noise shader somente quando performance justificar.

16. SCRATCHES

Scratches não devem se mover como chuva.

Preferir:

static
+
occasional opacity variation

Exemplo:

opacity .06 → .10 → .06
duration 800–1600ms

Frequência muito baixa.

17. SECTION ENTRY

Todas as seções não devem repetir exatamente a mesma animação.

Criar uma gramática compartilhada.

Base:

01 index
↓
hairline
↓
title
↓
image
↓
metadata

Mas variar a ordem conforme a hierarquia.

18. CURRENT EXHIBITION REVEAL

Para:

THE MEMORY OF THINGS

Trigger:

quando ~20–25% da seção entra no viewport.

Sequência:

0ms
/ EXHIBITION 034

100ms
vertical/horizontal rule

180ms
photograph reveal

300ms
THE MEMORY

390ms
OF THINGS

520ms
curatorial paragraph

650ms
metadata rows
19. ARTWORK IMAGE REVEAL

Evitar fade-up genérico.

Usar crop.

.artwork-frame {
  overflow: hidden;
}

.artwork-frame img {
  transform: scale(1.035);
}

.artwork-frame.is-visible img {
  transform: scale(1);

  transition:
    transform
    1200ms
    var(--ease-out-expo);
}

Combinar com clip-path do container.

20. COLLECTION — STAGGERED EDITORIAL REVEAL

Não revelar todos os artworks juntos.

Como tamanhos são diferentes, usar ritmo irregular.

Exemplo:

Artwork 01     0ms
Metadata 01  160ms

Artwork 02   240ms
Metadata 02  390ms

Artwork 03   470ms
Metadata 03  610ms

Evitar grid stagger perfeitamente mecânico.

Introduzir variação de:

±40–80ms.

Isso preserva sensação editorial.

21. ARTWORK HOVER

Desktop only.

Default:

.artwork img {
  filter:
    saturate(.72)
    contrast(1.02);

  transform: scale(1);
}

Hover:

.artwork:hover img {
  filter:
    saturate(.78)
    contrast(1.07);

  transform:
    scale(1.018);
}

Duration:

image      700ms
metadata   240ms
line       400ms

Não ultrapassar:

scale(1.025)
22. ARTWORK METADATA HOVER

Default:

opacity .58

Hover:

opacity 1

Além disso:

archive marker:

◆

pode aparecer.

Animation:

opacity 0 → 1
translateX -3px → 0
240ms
23. OPTIONAL CURSOR IMAGE BEHAVIOR

Para desktop de alta precisão:

ao hover em item textual de exposição, imagem associada pode surgir
em área lateral.

Não fazer imagem seguir cursor diretamente.

Usar posição fixa editorial.

Exemplo:

UPCOMING EXHIBITION LIST

035  BOTANICAL MEMORY          [IMAGE]
036  THE WEIGHT OF LIGHT
037  FRAGMENTS OF HOME

Ao trocar item:

old image:

opacity 1 → 0
scale 1 → .985
300ms

new image:

opacity 0 → 1
scale 1.015 → 1
500ms
24. ARCHIVAL INTERLUDE

Quote:

EVERY OBJECT
REMEMBERS
A HAND.

Essa seção pode ter motion mais dramático.

Trigger:

40% viewport.

Sequence:

EVERY OBJECT
mask reveal

REMEMBERS
mask reveal +90ms

A HAND.
mask reveal +180ms

script
+320ms

rule
+450ms

metadata
+600ms

Permitir que o texto ocupe o viewport.

25. QUOTE SCROLL BEHAVIOR

Opcional:

Durante aproximadamente 60vh de scroll:

quote translateY:
12px → -12px

background image:
-8px → 8px

metadata:
static

Diferença de velocidade cria profundidade.

Não usar pin prolongado.

26. UPCOMING EXHIBITIONS LIST

Cada linha:

035
BOTANICAL MEMORY
12.03—28.06.2027
GALLERY 02
→

Hover:

title opacity .65 → 1
line brightens
arrow moves 4px
archive number becomes gold/ivory
related image changes

Duration:

180–300ms.

27. ROW LINE ANIMATION

Default:

border-color:
rgba(216,216,187,.18);

Hover:

border-color:
rgba(216,216,187,.48);

Pode adicionar pseudo-elemento:

.row::after {
  transform: scaleX(0);
  transform-origin: left;
}

.row:hover::after {
  transform: scaleX(1);
}

Duration:

400ms.

28. NAVIGATION MOTION

Navigation deve permanecer extremamente calma.

Hover:

opacity .55 → 1

Optional marker:

◆

aparece em 180ms.

Não:

background fill;
pill;
scale;
bounce.
29. HEADER SCROLL STATE

Hero top:

background transparent
border invisible

After approximately 80–120px scroll:

background rgba(23,24,20,.82)
backdrop blur 8–12px OPTIONAL
border-bottom rgba(216,216,187,.12)

Transition:

300–450ms

Blur é permitido apenas funcionalmente no header.

Não transformar o design em glassmorphism.

30. HEADER HIDE / REVEAL

Opcional.

Scroll down:

header translateY(-100%)

Scroll up:

header translateY(0)

Threshold:

não reagir a movimentos inferiores a ~20–30px.

Duration:

350–450ms.

Easing:

var(--ease-out-editorial)

31. CTA MOTION

CTA:

VIEW EXHIBITION →

Default:

VIEW EXHIBITION →
───────────────

Hover:

arrow translateX(4px)
underline scaleX(1 → .72 → 1)

ou simplesmente:

line extends 6–12px

Duration:

180–300ms.

Nunca transformar em botão preenchido no hover.

32. MUSEUM VISIT SECTION

Fotografia de interior pode usar reveal por iluminação.

Initial:

brightness .65
opacity .75

Visible:

brightness .9
opacity 1

Duration:

1000–1400ms.

O efeito deve lembrar olhos se ajustando à luz da galeria.

33. OPENING HOURS

Não animar cada horário agressivamente.

Use apenas:

opacity 0 → 1
translateY 3px → 0

Stagger:

60ms.

Metadata precisa continuar parecendo informação funcional.

34. FOOTER ENTRY

Footer não precisa de grande reveal.

Recommended:

top rule draws
↓
museum wordmark fades
↓
columns fade
↓
botanical sequence appears
↓
MNT / 034 appears

Duration total:

600–900ms.

35. PAGE TRANSITION

Se landing page levar para exhibition detail:

EXIT

Current page:

opacity 1 → .92
image scale 1 → 1.015

Duration:

300–450ms.

COVER

Charcoal layer:

clip-path:
inset(100% 0 0 0)
→
inset(0)

Duration:

500–700ms.

NEXT PAGE

New hero photograph:

dark exposure
→
normal exposure

Display title:

mask reveal.

Total:

~900–1300ms.

Não bloquear navegação por vários segundos.

36. OPTIONAL ARCHIVE TRANSITION

Alternativa mais conceitual:

Ao abrir artwork:

OBJECT 017
↓
selected image expands
↓
surrounding content darkens
↓
archive metadata remains visible
↓
detail page replaces composition

Usar shared-element transition se stack permitir.

A imagem deve parecer removida do arquivo e colocada sobre uma
mesa de análise.

37. SCROLL REVEAL OBSERVER

Recommended threshold:

{
  threshold: 0.18,
  rootMargin: "0px 0px -8% 0px"
}

Elementos grandes:

threshold:

0.10–0.20

Metadata:

0.25–0.35

Não esperar elemento estar no centro para começar animação.

38. REVEAL ONCE

Por padrão:

animate once = true

Não repetir reveal toda vez que usuário sobe/desce.

Repetição faz o site parecer demo de animação.

Exceptions:

hover;
navigation states;
artwork swapping;
tiny texture variation.
39. SCROLL VELOCITY

Não vincular transformações diretamente a cada pixel sem damping.

Se usar GSAP/Framer Motion:

usar smoothing.

Exemplo conceitual:

scroll input
↓
lerp / spring heavily damped
↓
visual movement

Spring, quando usado internamente, não deve produzir bounce.

40. FRAMER MOTION TOKENS
export const editorialEase = [0.22, 0.61, 0.36, 1];

export const expoEase = [0.16, 1, 0.3, 1];

export const fadeMetadata = {
  hidden: {
    opacity: 0,
    y: 4
  },

  visible: {
    opacity: 1,
    y: 0,
    transition: {
      duration: 0.4,
      ease: editorialEase
    }
  }
};

export const titleReveal = {
  hidden: {
    y: "105%"
  },

  visible: {
    y: "0%",
    transition: {
      duration: 0.85,
      ease: expoEase
    }
  }
};

export const artworkReveal = {
  hidden: {
    opacity: 0,
    scale: 1.025
  },

  visible: {
    opacity: 1,
    scale: 1,
    transition: {
      opacity: {
        duration: 0.8
      },

      scale: {
        duration: 1.2,
        ease: expoEase
      }
    }
  }
};
41. GSAP RECOMMENDED HERO TIMELINE

Pseudo implementation:

const tl = gsap.timeline({
  defaults: {
    ease: "power3.out"
  }
});

tl
  .fromTo(
    ".hero-image",
    {
      opacity: 0,
      scale: 1.025,
      filter: "brightness(.72)"
    },
    {
      opacity: 1,
      scale: 1,
      filter: "brightness(.92)",
      duration: 1.2
    }
  )

  .from(
    ".hero-index",
    {
      opacity: 0,
      y: 4,
      duration: .35
    },
    .2
  )

  .from(
    ".hero-title-line",
    {
      yPercent: 105,
      duration: .85,
      stagger: .09,
      ease: "expo.out"
    },
    .32
  )

  .from(
    ".hero-script",
    {
      opacity: 0,
      clipPath: "inset(0 100% 0 0)",
      duration: .9
    },
    .65
  )

  .from(
    ".hero-rule",
    {
      scaleX: 0,
      duration: .65
    },
    .75
  )

  .from(
    ".hero-meta",
    {
      opacity: 0,
      y: 4,
      stagger: .06,
      duration: .35
    },
    .82
  )

  .from(
    ".hero-cta",
    {
      opacity: 0,
      duration: .4
    },
    1
  );
42. PERFORMANCE RULES

Não sacrificar qualidade do scroll para criar atmosfera.

Priorizar animações de:

transform
opacity
clip-path (com moderação)

Evitar animar continuamente:

width
height
top
left
filter blur
large box-shadow
background-position em assets gigantes

Filters pesados em fotografias devem ser pré-processados quando
possível.

43. WILL-CHANGE

Não aplicar globalmente.

Usar somente enquanto necessário:

.motion-image {
  will-change: transform, opacity;
}

Remover ou limitar em elementos fora da viewport.

44. MOBILE MOTION

Mobile deve ser mais simples.

Reduzir:

parallax;
grain animation;
cursor effects;
complex masking;
simultaneous layers.

Preservar:

photographic reveal;
title mask;
line drawing;
metadata fade;
subtle artwork transitions.
45. MOBILE HERO

Sequence:

photo reveal
↓
archive number
↓
title
↓
script
↓
date
↓
CTA

Total:

800–1100ms.

Não esperar 2 segundos para liberar conteúdo.

46. TOUCH INTERACTION

Não depender de hover para revelar informação essencial.

Artwork tap:

first tap/click = navigation

Metadata essencial já deve estar visível.

Não implementar:

"tap once to reveal hover, tap twice to open"

sem necessidade funcional.

47. PREFERS-REDUCED-MOTION

Obrigatório.

@media (prefers-reduced-motion: reduce) {

  *,
  *::before,
  *::after {
    scroll-behavior: auto !important;
    animation-duration: .001ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: .001ms !important;
  }

  .parallax {
    transform: none !important;
  }

  .grain-motion {
    animation: none !important;
  }
}

Mas não esconder conteúdo inicialmente esperando JS.

Reduced motion deve receber estado final imediatamente.

48. ACCESSIBILITY + MOTION

Nunca animar de forma que:

texto funcional fique ilegível;
botão fique indisponível;
focus seja removido;
layout shift mova alvo durante interação;
scroll seja sequestrado;
usuário precise assistir animação para acessar informação.

Evitar flashes.

Não usar glitch/strobe.

49. MOTION DENSITY

Por viewport:

Recommended:

1 dominant motion event
2–4 secondary reveals
microinteraction only on interaction

Evitar:

10 elementos se movendo continuamente
50. MOTION CONTRAST

Assim como tipografia possui contraste, motion também.

Exemplo correto:

PHOTO        1200ms
TITLE         850ms
RULE          650ms
METADATA      350ms
HOVER         200ms

Isso cria hierarquia temporal.

Não usar:

everything = 500ms ease
51. SCROLL CHOREOGRAPHY

Mapa recomendado:

┌───────────────────────────────┐
│ HERO                          │
│ cinematic reveal             │
│ slow parallax                 │
└───────────────┬───────────────┘
                ↓
┌───────────────────────────────┐
│ CURRENT EXHIBITION            │
│ photo crop reveal             │
│ title mask                    │
└───────────────┬───────────────┘
                ↓
┌───────────────────────────────┐
│ COLLECTION                    │
│ irregular artwork stagger     │
│ hover interactions            │
└───────────────┬───────────────┘
                ↓
┌───────────────────────────────┐
│ ARCHIVAL QUOTE                │
│ large typographic reveal      │
│ slight depth                  │
└───────────────┬───────────────┘
                ↓
┌───────────────────────────────┐
│ UPCOMING                      │
│ restrained list interaction   │
│ artwork swapping              │
└───────────────┬───────────────┘
                ↓
┌───────────────────────────────┐
│ VISIT                         │
│ photographic light reveal     │
└───────────────┬───────────────┘
                ↓
┌───────────────────────────────┐
│ FOOTER                        │
│ almost static                 │
└───────────────────────────────┘

A intensidade diminui no final.

Isso cria uma narrativa:

DISCOVERY
↓
OBSERVATION
↓
EXPLORATION
↓
REFLECTION
↓
INFORMATION
↓
REST
52. DO

✓ slow photographic reveal

✓ typography through masks

✓ irregular but controlled stagger

✓ micro metadata fade

✓ line drawing

✓ tiny depth differences

✓ occasional material movement

✓ restrained image hover

✓ static resting periods

✓ cinematic exposure changes

✓ motion hierarchy

✓ reduced-motion support

53. DON'T

✗ bouncing

✗ elastic springs

✗ large fly-ins

✗ spinning

✗ neon glow animation

✗ glitch

✗ RGB split

✗ cursor trail

✗ magnetic everything

✗ 3D card tilt

✗ endless marquee

✗ huge image zoom

✗ aggressive scroll hijacking

✗ five-screen pinned hero

✗ continuous grain movement

✗ every text line fading upward

✗ every section using identical reveal

✗ animation just because an element exists

54. MOTION QA CHECKLIST

Before shipping:

 Motion feels editorial rather than app-like
 Hero settles within ~1.4s
 Navigation is immediately usable
 Photography receives the slowest motion
 Metadata receives the fastest/subtlest motion
 Typography primarily uses masks
 No generic 40px fade-up pattern
 Parallax stays within restrained ranges
 No essential information depends on hover
 Reveals normally happen once
 Grain is not constantly moving
 Scratches do not look like rain
 Hover scale remains <= ~1.025
 Motion hierarchy is visible
 Sections do not all animate identically
 Mobile has reduced motion complexity
 No scroll hijacking
 No visible layout shift
 Focus remains stable
 prefers-reduced-motion works
 Content exists in final state without JS animation
 Animation supports hierarchy instead of competing with artwork
55. AI FRONT-END MOTION AGENT PROMPT

Implement the museum landing page motion according to an archival,
dark-romantic editorial language.

Motion must feel like photography being exposed, catalogue pages being
revealed and museum artifacts gradually emerging from darkness.

Do not animate the interface like a SaaS product.

Use slow photographic exposure reveals, typography revealed through
overflow masks, subtle metadata fades, hairline drawing, restrained
parallax and irregular editorial staggering.

The hero choreography should follow:

PHOTOGRAPH
→ ARCHIVE INDEX
→ DISPLAY TITLE
→ CALLIGRAPHIC OVERLAY
→ ORNAMENTAL RULE
→ METADATA
→ CTA

The complete hero should settle in approximately 1.2–1.4 seconds.

Photography should generally use 700–1400ms transitions.

Large typography should use approximately 700–900ms masked reveals.

Hairlines should draw in approximately 400–700ms.

Metadata should appear in approximately 250–450ms.

Interactive states should respond in approximately 120–280ms.

Use controlled asymmetry in timing. Do not give every element the
same duration or delay.

Parallax must be extremely restrained:
approximately 8–32px maximum depending on layer and viewport.

Metadata should generally remain static while photographic layers
move slightly, reinforcing the idea that the interface is an archival
cataloguing layer placed over physical material.

Artwork hover may scale imagery only to approximately 1.018 and
slightly increase contrast. Never use dramatic card zoom.

Do not use bounce, elastic motion, large fly-ins, 3D tilt, neon glow,
RGB glitch, cursor trails, aggressive parallax, long scroll hijacking,
constant marquees or continuous decorative animation.

The majority of the page should be at rest.

Use animation once when sections enter the viewport. Do not repeatedly
replay reveals as the user scrolls backward and forward.

Preserve the hierarchy:

PHOTO = slow / cinematic
DISPLAY = expressive / masked
ORNAMENT = precise
METADATA = fast / subtle
INTERACTION = immediate

On mobile reduce parallax, grain animation and layered complexity while
preserving photographic reveals, title masks, line drawing and metadata.

Implement prefers-reduced-motion and immediately expose all content in
its final state when reduced motion is requested.

The final experience should feel:

DISCOVERED, NOT TRIGGERED.
EXPOSED, NOT FADED-IN.
PHYSICAL, NOT DIGITAL.
CURATED, NOT ANIMATED.

If the visitor notices the animation before noticing the artwork,
the motion is too strong.

56. FINAL MOTION FORMULA

MUSEUM MOTION =

PHOTOGRAPHIC EXPOSURE
+
MASKED TYPOGRAPHY
+
ARCHIVAL SEQUENCING
+
HAIRLINE DRAWING
+
MICRO METADATA
+
SUBTLE DEPTH
+
LONG REST STATES

The motion should make the museum feel alive without making the
interface feel busy.

The artwork remains the protagonist.

Motion only controls how it is discovered.


A regra central para implementação é **“se o usuário percebe primeiro a animação e depois a obra, o motion está forte demais”**. A imagem original fornece materialidade, hierarquia e sobreposição; o sistema acima converte essas propriedades estáticas em uma hierarquia temporal equivalente, sem alegar que o movimento foi observado na referência. :contentReference[oaicite:1]{index=1}