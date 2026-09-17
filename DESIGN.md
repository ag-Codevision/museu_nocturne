
# DESIGN.md — NOCTURNE ARCHIVE
## Dark Romantic / Archival Editorial Design System

> Sistema visual derivado das referências fornecidas.
>
> Objetivo: permitir a criação de novas interfaces, landing pages,
> portfolios, editoriais, campanhas e experiências digitais que pareçam
> pertencer ao mesmo universo visual das referências sem simplesmente
> reproduzir a composição original.
>
> DNA resumido:
>
> ROMANTIC PHOTOGRAPHY
> + ARCHIVAL INFORMATION DESIGN
> + AGED IVORY
> + DIRTY CHARCOAL
> + EDITORIAL SERIF
> + CALLIGRAPHIC INTERFERENCE
> + MICRO METADATA
> + BOTANICAL ORNAMENT
> + ANALOG DEGRADATION

---

# 0. EXECUTIVE VISUAL DNA

## 0.1 North Star

A experiência deve parecer um objeto editorial encontrado em um arquivo:

- fotografia de moda antiga;
- catálogo de coleção privada;
- perfume experimental;
- convite impresso;
- editorial europeu;
- capa de disco;
- documento de arquivo;
- material fotográfico envelhecido;
- peça gráfica impressa e posteriormente digitalizada.

A interface NÃO deve parecer um website convencional que recebeu
uma textura vintage posteriormente.

O design nasce da relação entre:

1. fotografia;
2. tipografia;
3. matéria;
4. silêncio;
5. ornamentação;
6. informação arquivística.

A principal tensão visual é:

> SENSUALIDADE FOTOGRÁFICA × RIGOR DE ARQUIVO

A fotografia é emocional.

A informação gráfica é sistemática.

A combinação das duas cria a identidade.

---

# 1. REFERENCE DECOMPOSITION

## 1.1 Shared DNA — Observed

As referências compartilham:

- fundo predominantemente escuro;
- fotografia integrada à composição;
- tons quentes e dessaturados;
- branco substituído por ivory/off-white;
- tipografia display de forte personalidade;
- contraste extremo entre texto enorme e texto microscópico;
- linhas horizontais finas;
- pequenos elementos de catalogação;
- números, datas ou identificadores;
- sobreposição de elementos gráficos;
- ornamentação floral/botânica;
- textura analógica;
- imperfeições visuais;
- composição assimétrica;
- baixa saturação;
- ausência de componentes digitais convencionais.

---

## 1.2 Reference-specific traits

### Reference A

Contribui principalmente com:

- mãos;
- pele;
- joalheria;
- bordados;
- renda;
- tecido;
- flores;
- proximidade física;
- sensação romântica;
- sensualidade;
- iluminação pictórica;
- textura material muito forte.

### Reference B

Contribui principalmente com:

- construção editorial;
- tipografia monumental;
- catalogação;
- composição gráfica;
- informação secundária;
- índices;
- sobreposição tipográfica;
- comportamento de pôster.

---

## 1.3 Winning rule

Quando houver conflito entre as referências:

> A fotografia fornece emoção.
> O sistema gráfico fornece estrutura.

Não transformar a interface em:

- vintage scrapbook;
- site luxury genérico;
- minimalismo bege;
- dark SaaS;
- cyberpunk;
- brutalismo digital;
- página editorial excessivamente limpa.

---

# 2. DESIGN PRINCIPLES

## 2.1 MATERIAL BEFORE UI

A superfície precisa parecer material.

Evitar superfícies digitais perfeitamente uniformes.

Usar:

- grain;
- dust;
- scratches;
- fading;
- tonal variation;
- paper/scanner artifacts.

---

## 2.2 IMAGE BEFORE COMPONENT

A fotografia deve frequentemente funcionar como estrutura.

Não colocar toda imagem dentro de card.

Permitir:

- bleed;
- crop;
- overlap;
- masking;
- elementos saindo do grid.

---

## 2.3 EXTREME TYPOGRAPHIC CONTRAST

A diferença entre display e metadata deve ser radical.

Exemplo:

    DISPLAY     96px
    METADATA     9px

Não normalizar a hierarquia.

---

## 2.4 ORNAMENT HAS FUNCTION

Ornamentos funcionam como:

- separadores;
- ritmo;
- assinatura;
- marcador;
- índice;
- elemento de repetição.

Nunca adicionar flores aleatoriamente.

---

## 2.5 CONTROLLED IMPERFECTION

Imperfeição deve parecer intencional.

Não confundir com desorganização.

---

# 3. COLOR SYSTEM

## 3.1 Estimated palette

Os valores são aproximações visuais derivadas das referências,
não tokens originais confirmados.

```css
:root {
  --color-ink-1000: #12130F;
  --color-ink-950: #171814;
  --color-ink-900: #1D1E19;
  --color-ink-850: #24251F;
  --color-ink-800: #2B2C25;

  --color-ivory-50: #E0E0C6;
  --color-ivory-100: #D8D8BB;
  --color-ivory-200: #C7C7A8;
  --color-ivory-300: #ADAE91;
  --color-ivory-500: #7F806B;

  --color-skin: #8B654E;
  --color-earth: #665343;

  --color-gold: #9A803D;
  --color-gold-muted: #786831;

  --color-line:
    rgba(216,216,187,.22);

  --color-line-strong:
    rgba(216,216,187,.42);

  --color-overlay:
    rgba(18,19,15,.32);
}
3.2 Distribution
Aproximadamente:

70–80% charcoal / black
15–25% photographic earth tones
 5–10% ivory graphics
   <5% antique gold
O accent nunca deve dominar.
3.3 Accent policy
Gold allowed


 joias; 

 pequenos números; 

 detalhe ornamental; 

 hover muito pontual; 

 indicador selecionado; 

 pequenos símbolos. 
Gold forbidden


 backgrounds grandes; 

 parágrafos; 

 todos os botões; 

 grandes gradientes; 

 bordas de todos os componentes. 
4. TYPOGRAPHY
A tipografia possui três vozes principais.
4.1 DISPLAY
Role
Marca, hero, título monumental, palavra editorial.
Morphology


 serif; 

 high contrast; 

 elegante; 

 vertical stress; 

 terminais refinados; 

 contraste fino/grosso elevado; 

 aparência editorial/fashion; 

 possibilidade de italic dramático. 
Candidate fonts
Não é possível confirmar a fonte original apenas pelo raster.
Recomendadas:


 Bodoni Moda 

 Instrument Serif 

 Cormorant Garamond 

 DM Serif Display 
Settings

Weight:       400–600
Size:         64–160px desktop
Line-height:  .78–.96
Tracking:     -.02em → -.055em
Case:         contextual
Confidence:   Medium
4.2 SCRIPT
Role
Interferência caligráfica.
Não deve funcionar como body copy.
Usar como:


 assinatura; 

 palavra atravessando título; 

 detalhe; 

 elemento quase ilustrativo. 
Candidate fonts


 Ballet 

 Italianno 

 Allura 
Idealmente utilizar lettering customizado.
Settings

Size:         40–96px
Line-height:  .8–1
Weight:       regular
Rotation:     -2deg → +2deg
Confidence:   Medium/Low
4.3 METADATA
Role


 datas; 

 índices; 

 navegação; 

 legendas; 

 coordenadas; 

 edição; 

 categorias; 

 microcopy. 
Morphology


 sans estreita; 

 neutral grotesk; 

 uppercase frequente; 

 tracking elevado; 

 pequeno tamanho. 
Candidates


 Helvetica Neue 

 Arial Narrow 

 Archivo 

 IBM Plex Sans Condensed 
Settings

Size:         7–11px
Weight:       400–500
Line-height:  1.25–1.5
Tracking:     .08–.18em
Case:         uppercase
Confidence:   Medium
5. TYPE SCALE

:root {
  --type-micro: 8px;
  --type-meta: 10px;
  --type-caption: 12px;
  --type-body: 15px;
  --type-body-lg: 18px;

  --type-h4: 24px;
  --type-h3: 32px;
  --type-h2: 48px;

  --type-display-sm: 64px;
  --type-display-md: 96px;
  --type-display-lg: 136px;
  --type-display-xl: 160px;
}
Responsive display:

font-size: clamp(4rem, 10vw, 10rem);
6. SPACING SYSTEM
Evidence suggests disciplined spacing underneath an apparently  free composition.
Use a 4px implementation base.

:root {
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;
  --space-20: 80px;
  --space-24: 96px;
  --space-32: 128px;
}
Não deixar o sistema de 4px visivelmente mecânico.
A composição final deve continuar editorial.
7. LAYOUT GRID
7.1 Desktop
Recommended implementation:

.editorial-grid {
  display: grid;
  grid-template-columns: repeat(12, minmax(0, 1fr));
  column-gap: clamp(12px, 1.5vw, 24px);
}
Outer margins
Estimated/recommended:

1440px viewport: 48–72px
1280px viewport: 40–56px
1024px viewport: 32–40px
7.2 Composition ratio
Typical composition:

IMAGE / MATERIAL FIELD
55–75%

GRAPHIC INFORMATION
25–45%
Isso não precisa representar duas colunas explícitas.
Elementos podem se sobrepor.
7.3 Alignment anchors
Criar aproximadamente 3–5 anchors por composição.
Exemplo:

x1 = page margin
x2 = image edge
x3 = title start
x4 = metadata start
x5 = page edge
Reutilizar os mesmos anchors.
Isso impede que a assimetria vire caos.
8. BORDERS / RADIUS / SHADOWS
Borders

--border-hairline:
  1px solid rgba(216,216,187,.22);

--border-visible:
  1px solid rgba(216,216,187,.42);
Radius

--radius: 0px;
Radius máximo excepcional:

--radius-soft: 2px;
Não usar:

8px
12px
16px
24px
pill
Shadows
Evitar UI drop shadows.
Se necessário:

box-shadow:
  0 16px 50px rgba(0,0,0,.18);
Somente para simular profundidade fotográfica/papel.
9. BACKGROUND & SURFACE SYSTEM
Base

body {
  background: #171814;
  color: #D8D8BB;
}
Não deixar background perfeitamente uniforme.
Adicionar variação tonal extremamente baixa.

.archive-background {
  background:
    radial-gradient(
      circle at 30% 20%,
      rgba(216,216,187,.025),
      transparent 40%
    ),
    #171814;
}
10. TEXTURE SYSTEM
Textura é componente estrutural.
Layer 1 — Fine grain

opacity: 4–12%
scale:   150–350px tile
Layer 2 — Dust

opacity: 2–6%
Aplicar irregularmente.
Layer 3 — Scratches
Poucos elementos.
Preferência:

vertical
diagonal
edge-biased
Layer 4 — Exposure
Áreas fotográficas podem apresentar:


 blooming; 

 faded blacks; 

 local haze; 

 vignette; 

 highlight degradation. 
11. HEADER / NAVIGATION
O header não deve parecer uma navbar SaaS.
Recommended structure:

BRAND / MONOGRAM

                INDEX
                ARCHIVE
                ABOUT

         EDITION 034
Pode ser sobreposto diretamente à imagem.
Desktop

height: 64–96px
padding-inline: page margin
Typography

8–11px
uppercase
tracking .12em
Active state
Não usar pill.
Usar:


 underline; 

 small star; 

 dot; 

 index; 

 opacity difference. 
12. HERO
Hero recomendado:

┌──────────────────────────────────────────┐
│ metadata                    edition      │
│                                          │
│ PHOTOGRAPHY                              │
│ ██████████████████                       │
│ ██████████████████      LARGE            │
│ ██████████████████     DISPLAY           │
│ ██████████████████    script             │
│ ██████████████████                       │
│                         ───── ◆ ─────     │
│                         metadata         │
│                         metadata         │
└──────────────────────────────────────────┘
Hero formula
Cada hero deve ter:


 uma imagem dominante; 

 uma palavra/título monumental; 

 um elemento script opcional; 

 metadata; 

 uma linha; 

 um pequeno ornamento. 
Evitar adicionar mais elementos sem necessidade.
13. SECTION GRAMMAR
Nova seção:

INDEX
small metadata

LARGE TYPOGRAPHIC OR PHOTOGRAPHIC EVENT

supporting copy

──────────── ◆ ────────────

secondary information
Não transformar cada seção em card.
14. BUTTONS & LINKS
Primary editorial action

.editorial-link {
  display: inline-flex;
  align-items: center;
  gap: 12px;

  color: var(--color-ivory-100);

  font-family: var(--font-meta);
  font-size: 10px;
  letter-spacing: .12em;
  text-transform: uppercase;

  border-bottom:
    1px solid rgba(216,216,187,.42);

  padding-bottom: 5px;
}
Hover:

.editorial-link:hover {
  color: var(--color-ivory-50);
}
Adicionar deslocamento da linha ou arrow:

4–8px
Não usar:


 large filled CTA; 

 pill; 

 glowing button; 

 gradient button. 
15. CARDS / CONTENT MODULES
Cards convencionais devem ser exceção.
Preferir:

IMAGE

034 / ARCHIVE

TITLE
────────────

YEAR      CATEGORY
Sem background separado.
Sem radius.
Sem sombra.
Imagem é o principal container.
16. FORMS
Inputs devem parecer campos editoriais.

.archive-input {
  width: 100%;

  background: transparent;

  border: 0;
  border-bottom:
    1px solid rgba(216,216,187,.32);

  border-radius: 0;

  color: #D8D8BB;

  padding: 12px 0;

  font-size: 12px;
}
Focus:

.archive-input:focus-visible {
  outline: none;
  border-color: #D8D8BB;
}
Adicionar focus ring alternativo acessível no wrapper.
17. ICONOGRAPHY
Evitar icon sets genéricos como linguagem principal.
Priorizar:


 star; 

 diamond; 

 flower; 

 cross; 

 thin arrow; 

 monogram; 

 registration mark. 
Stroke:

.75–1px
18. IMAGERY & ART DIRECTION
18.1 Subject
Preferir:


 mãos; 

 pele; 

 joias; 

 renda; 

 tecido; 

 flores; 

 bordados; 

 objetos antigos; 

 detalhes corporais não explícitos; 

 materiais orgânicos; 

 superfícies envelhecidas. 
18.2 Framing
Fotografar fragmentos.
Preferir:

hand instead of full person
fabric detail instead of full garment
flower detail instead of bouquet
jewelry detail instead of product shot
18.3 Camera
Visual recomendado:

50–85mm equivalent
shallow/moderate depth
intimate crop
imperfect focus allowed
underexposed exposure
18.4 Lighting


 low-key; 

 side light; 

 warm highlights; 

 deep shadows; 

 no bright commercial fill. 
18.5 Tonality

saturation: -20% → -45%
contrast: moderate
blacks: deep but imperfect
warmth: slight
grain: visible
18.6 UI integration
Nunca colocar imagem apenas como thumbnail.
Imagem pode:


 ocupar background; 

 desaparecer atrás do título; 

 receber metadata; 

 ser cortada pelo viewport; 

 cruzar colunas; 

 receber textura global. 
19. SIGNATURE MOTIFS
Motif A — Botanical repetition

✣    ✣    ✣    ✣
3–6 símbolos.
Motif B — Central diamond

────────── ◆ ──────────
Motif C — Archival date

23/02     2025     D-034
Motif D — Micro header

DSGN           FEB           034
Motif E — Edition

EDITION
NO. 034
Motif F — Overprinted script
Display word:

ARCHIVE
Script atravessando:

mémoire
O script deve ocupar aproximadamente:

35–65%
da largura do display.
20. MOTION SYSTEM
Status
INFERRED.
As referências são estáticas e não demonstram comportamento real.
Timings

:root {
  --motion-fast: 240ms;
  --motion-base: 400ms;
  --motion-slow: 700ms;

  --ease-editorial:
    cubic-bezier(.22,.61,.36,1);
}
Image reveal

opacity 0 → 1
transform translateY(8px) → 0
duration 600–900ms
Metadata

opacity 0 → 1
duration 300–500ms
Rule reveal

scaleX(0) → scaleX(1)
transform-origin: left
duration 400–700ms
Image hover
No zoom maior que:

1.015–1.025
Preferir:


 contrast change; 

 grain shift; 

 opacity; 

 metadata reveal. 
Reduced motion

@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: .001ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: .001ms !important;
    scroll-behavior: auto !important;
  }
}
21. RESPONSIVE BEHAVIOR
Status
INFERRED.
Não observado diretamente nas referências.
Desktop — ≥ 1200px

12 columns
40–72px margins
aggressive overlaps allowed
display 96–160px
photography 55–75% visual weight
Laptop — 992–1199px

12 columns
reduce margins
display 72–120px
preserve overlap
reduce micro metadata density ~15%
Tablet — 768–991px

8 columns
display 64–96px
photography may become 60–100% width
metadata clusters reposition
botanical motif remains visible
Mobile — <768px
Do NOT transform into generic stacked cards.
Use:

photography
↓
overlapping display
↓
script
↓
metadata cluster
↓
ornament
Recommended:

margin: 16–24px
display: 48–72px
metadata: 8–10px
Permitir crop agressivo.
Manter pelo menos:


 1 ornament; 

 1 archival index; 

 1 oversized title; 

 texture; 

 photography. 
22. ACCESSIBILITY
Acessibilidade não deve remover a direção de arte.
Focus

:focus-visible {
  outline: 1px solid #D8D8BB;
  outline-offset: 4px;
}
Contrast
Metadata puramente atmosférica pode ter contraste menor.
Informação funcional não.
Nunca usar microcopy de baixo contraste para:


 preço; 

 navegação necessária; 

 erro; 

 labels de formulário; 

 CTA; 

 informação legal importante. 
Target sizes
Elementos interativos visualmente pequenos devem possuir hit-area  invisível maior.
Target recomendado:

44 × 44px
quando aplicável.
Semantic structure
Usar:

header
nav
main
section
article
figure
figcaption
footer
Não construir a página inteira com divs decorativas.
Alt strategy
Descrever:


 sujeito; 

 ação; 

 material; 

 informação relevante. 
Não descrever grain, scratches ou filtros se forem puramente decorativos.
23. CSS TOKENS

:root {
  /* COLOR */
  --bg: #171814;
  --bg-deep: #12130F;
  --surface: #24251F;

  --ivory: #D8D8BB;
  --ivory-soft: #C7C7A8;
  --muted: #ADAE91;

  --earth: #665343;
  --skin: #8B654E;

  --gold: #9A803D;
  --gold-muted: #786831;

  --line: rgba(216,216,187,.22);
  --line-strong: rgba(216,216,187,.42);

  /* TYPOGRAPHY */
  --font-display:
    "Bodoni Moda",
    "Instrument Serif",
    "Cormorant Garamond",
    serif;

  --font-script:
    "Ballet",
    "Italianno",
    cursive;

  --font-meta:
    "Archivo",
    "Helvetica Neue",
    "Arial Narrow",
    sans-serif;

  /* SPACING */
  --s1: 4px;
  --s2: 8px;
  --s3: 12px;
  --s4: 16px;
  --s5: 20px;
  --s6: 24px;
  --s8: 32px;
  --s10: 40px;
  --s12: 48px;
  --s16: 64px;
  --s20: 80px;
  --s24: 96px;
  --s32: 128px;

  /* GEOMETRY */
  --radius: 0px;
  --border: 1px solid var(--line);

  /* MOTION */
  --motion-fast: 240ms;
  --motion-base: 400ms;
  --motion-slow: 700ms;

  --ease-editorial:
    cubic-bezier(.22,.61,.36,1);

  /* Z */
  --z-base: 0;
  --z-image: 10;
  --z-type: 20;
  --z-meta: 30;
  --z-texture: 40;
  --z-nav: 50;
}
24. TAILWIND MAPPING

theme: {
  extend: {
    colors: {
      archive: {
        bg: "#171814",
        deep: "#12130F",
        surface: "#24251F",
        ivory: "#D8D8BB",
        ivorySoft: "#C7C7A8",
        muted: "#ADAE91",
        earth: "#665343",
        skin: "#8B654E",
        gold: "#9A803D",
      }
    },

    fontFamily: {
      display: [
        "Bodoni Moda",
        "Instrument Serif",
        "Cormorant Garamond",
        "serif"
      ],

      meta: [
        "Archivo",
        "Helvetica Neue",
        "Arial Narrow",
        "sans-serif"
      ]
    },

    borderRadius: {
      archive: "0px"
    }
  }
}
Não depender de Tailwind para composições editoriais complexas.
CSS Grid e CSS custom devem controlar os principais overlaps.
25. COMPONENT ARCHITECTURE

<AppShell>

  <TextureLayer />

  <ArchiveHeader>
    <Brand />
    <EditionIndex />
    <ArchiveNavigation />
  </ArchiveHeader>

  <Main>

    <EditorialHero>
      <HeroPhotography />
      <HeroDisplay />
      <ScriptOverlay />
      <MetadataCluster />
      <OrnamentalRule />
    </EditorialHero>

    <ArchiveSection>
      <SectionIndex />
      <EditorialMedia />
      <SectionCopy />
      <ArchiveMetadata />
    </ArchiveSection>

    <CollectionGrid>
      <EditorialArtifact />
      <EditorialArtifact />
      <EditorialArtifact />
    </CollectionGrid>

    <ManifestoSection />

    <ArchiveIndex />

  </Main>

  <ArchiveFooter>
    <EditionData />
    <Navigation />
    <BotanicalMark />
  </ArchiveFooter>

</AppShell>
26. CONTENT / PATTERN INVENTORY
Recommended recurring content:


 issue number; 

 date; 

 collection; 

 archive ID; 

 photographer; 

 location; 

 material; 

 edition; 

 chapter; 

 catalog number; 

 short poetic phrase; 

 short editorial title. 
Example:

COLLECTION / 04

ARCHIVE OF
FRAGILE THINGS

23 / 02
2025

D—034

TEXTILE STUDY
NO. 07

PORTO / BR
Metadata precisa parecer plausível e relacionada ao conteúdo.
Não gerar números aleatórios em excesso.
27. COMPONENT STATES
Link
Default:

ivory
Hover:

ivory brighter
underline expands
Focus:

visible ivory outline
Disabled:

muted @ ~45%
Editorial Artifact
Default:

image muted
metadata visible
Hover:

image contrast +3–6%
title opacity 1
rule extends
metadata shifts 2–4px
Navigation
Default:

opacity .65
Hover:

opacity 1
Active:

opacity 1
+ tiny marker / underline
Form
Default:

thin line
Focus:

strong ivory line
Error:

explicit textual error
+ icon/label
Do not rely exclusively on red.
28. VISUAL DENSITY RULES
Three information layers:
LEVEL 1 — Emotional


 photography; 

 display typography. 
Visual weight:

~70%
LEVEL 2 — Structural


 rules; 

 ornaments; 

 script; 

 section labels. 
Visual weight:

~20%
LEVEL 3 — Archival


 dates; 

 IDs; 

 microcopy; 

 edition; 

 metadata. 
Visual weight:

~10%
LEVEL 3 must never compete with photography.
29. DO / DON'T
DO

✓ dark tactile photography
✓ dirty charcoal
✓ aged ivory
✓ antique gold in tiny quantities
✓ editorial serif
✓ calligraphic interference
✓ extreme scale contrast
✓ microscopic metadata
✓ botanical ornament
✓ grain
✓ dust
✓ scratches
✓ crop
✓ overlap
✓ asymmetric composition
✓ hairline rules
✓ archival indexing
✓ imperfect photographic focus
DON'T

✗ blue/purple neon
✗ glassmorphism
✗ SaaS cards
✗ rounded-xl
✗ pill buttons
✗ bright white
✗ pure digital black everywhere
✗ gradients as decoration
✗ giant drop shadows
✗ generic stock fashion
✗ perfect commercial photography
✗ generic luxury marble
✗ excessive gold
✗ centered-everything layouts
✗ uniform typography
✗ clean minimalism without texture
✗ random vintage stickers
✗ scrapbook aesthetic
30. GENERATIVE COMPOSITION FORMULA
Para criar uma tela completamente nova:

NEW COMPOSITION =

1 DOMINANT PHOTOGRAPH
+
1 MONUMENTAL DISPLAY EVENT
+
0–1 SCRIPT INTERFERENCE
+
1 METADATA CLUSTER
+
1 HAIRLINE STRUCTURE
+
1 ORNAMENT FAMILY
+
1 ARCHIVAL IDENTIFIER
+
ANALOG SURFACE DEGRADATION
Se uma composição precisar de muitos elementos além disso,  provavelmente está ficando decorativa demais.
31. VISUAL QA CHECKLIST
Antes de aprovar:


 A fotografia domina a experiência? 

 O background não parece digitalmente perfeito? 

 O preto possui nuance charcoal? 

 O branco foi substituído por ivory? 

 Gold ocupa menos de aproximadamente 5%? 

 Existe forte contraste entre display e metadata? 

 O display parece editorial e não SaaS? 

 Metadata parece catalogação real? 

 Há pelo menos um alinhamento estrutural repetido? 

 As sobreposições parecem intencionais? 

 Há pelo menos um motif ornamental? 

 Grain está visível sem prejudicar leitura? 

 Scratches não parecem um filtro genérico? 

 Cards arredondados foram evitados? 

 Sombras de UI foram evitadas? 

 A fotografia possui crop íntimo? 

 A composição mantém espaço escuro? 

 O layout mobile mantém o DNA? 

 Elementos interativos têm focus visible? 

 Motion reduzido é respeitado? 

 Metadata funcional continua legível? 

 O resultado parece um artefato editorial, não um template? 
32. AI FRONT-END AGENT PROMPT
Build the interface using the NOCTURNE ARCHIVE visual system.
The experience must feel like a dark romantic fashion artifact,  archival publication, private collection catalogue or aged European  editorial rather than a conventional website.
Use a dirty charcoal #171814 foundation instead of pure black,  aged ivory #D8D8BB typography and only sparse antique-gold #9A803D  details.
Photography must dominate the composition. Use intimate crops of  hands, skin, jewelry, embroidery, lace, flowers, textiles and tactile  materials with low-key directional lighting, muted warm tones,  underexposure, analog grain and imperfect focus.
Combine monumental high-contrast editorial serif typography with  extremely small tracked metadata. Optional calligraphic typography  may cross the main display word as a graphic intervention.
Use 12-column editorial grids, repeated alignment anchors, asymmetric  composition, intentional overlap, hairline rules, botanical symbols,  dates, issue numbers and archive identifiers.
The interface must have zero or near-zero border radius. Avoid  conventional cards wherever possible. Photography should often act  as the container itself.
Add restrained analog degradation: fine grain, dust, occasional  scratches and tonal imperfections. Texture must feel physically  printed/scanned, not like a uniform noise filter.
Do not use glassmorphism, neon, purple/blue gradients, generic SaaS  cards, pill buttons, soft UI shadows, generic stock photography,  bright white surfaces, excessive gold, centered startup layouts or  clean luxury minimalism.
On mobile preserve the editorial art direction: large photography,  oversized serif typography, archival metadata, ornaments and  controlled overlaps. Do not collapse the system into generic stacked  cards.
Motion should be slow and editorial: opacity reveals, line expansion,  tiny image drift and metadata emergence. Respect prefers-reduced-motion.
Fidelity priority:


 macro composition 

 photography 

 charcoal / ivory palette 

 typography 

 overlap 

 spacing 

 archival metadata 

 botanical ornament 

 analog texture 

 motion 
If the page looks like a normal luxury website with a vintage filter,  the implementation is incorrect.
33. AI IMAGE ART-DIRECTION PROMPT
Positive prompt
Dark romantic archival fashion editorial photography, intimate crop  of a human hand resting against heavily embroidered antique ivory  fabric, delicate vintage gold jewelry, lace and botanical textile  details, low-key directional lighting, deep dirty-charcoal shadows,  warm muted skin tones, faded ivory highlights, restrained antique  gold, tactile textile fibers, analog 35mm film grain, aged European  fashion publication, scanned print texture, subtle dust and scratches,  slightly imperfect focus, underexposed cinematic photography,  museum archive atmosphere, mysterious private collection catalogue,  1970s to 1990s editorial reproduction character, dramatic crop,  physical materiality, subdued colors, elegant decay.
Negative direction
Avoid glossy commercial fashion photography, clean studio lighting,  white backgrounds, modern ecommerce photography, HDR, oversharpening,  perfect plastic skin, saturated colors, neon, cyberpunk, blue or  purple lighting, glossy robots, glassmorphism, colorful gradients,  generic luxury marble, excessive gold, modern SaaS styling,  cheerful lifestyle photography, influencer aesthetic, perfect digital  surfaces, generic stock imagery, fantasy costume, steampunk clichés.
34. CONFIDENCE / ASSUMPTIONS
Observed — High confidence


 predominantly dark palette; 

 aged light typography; 

 photographic dominance; 

 human/material imagery; 

 botanical ornamentation; 

 micro metadata; 

 large expressive typography; 

 thin structural rules; 

 asymmetrical composition; 

 analog degradation; 

 restrained color system; 

 strong scale contrast. 
Estimated — Medium confidence


 exact HEX values; 

 12-column implementation grid; 

 percentage distribution of colors; 

 spacing values; 

 exact typography scale; 

 photographic tonal adjustments. 
These values are production approximations intended to reproduce the  visual relationships.
Low confidence / Unverified


 exact original font families; 

 exact original print process; 

 exact texture source; 

 original design tokens. 
Do not claim those as source facts.
Inferred


 responsive behavior; 

 hover behavior; 

 page transitions; 

 reveal animations; 

 interaction states; 

 reduced-motion implementation. 
Static references do not prove those behaviors.
35. FINAL DESIGN FORMULA
DARK ROMANTIC PHOTOGRAPHY


 AGED IVORY 

 DIRTY CHARCOAL 

 MONUMENTAL FASHION SERIF 

 CALLIGRAPHIC INTERFERENCE 

 MICROSCOPIC ARCHIVAL DATA 

 BOTANICAL SYMBOLS 

 HAIRLINE GEOMETRY 

 CONTROLLED OVERLAP 

 ANALOG DEGRADATION 
The finished interface should feel discovered rather than rendered,  printed rather than generated, catalogued rather than decorated,  and intimate rather than commercially polished.
crie uma landing page sobre um museu  de arte .

O ponto mais importante desse `DESIGN.md` é não reduzir a estética a **“dark + serif + grain”**. O DNA está no contraste entre **fotografia romântica/material** e **catalogação gráfica extremamente controlada**. É essa combinação — junto do contraste brutal de escala tipográfica, ivory envelhecido, microdados, ornamentos e degradação analógica — que fará novas páginas parecerem parte da mesma família visual. :contentReference[oaicite:2]{index=2}