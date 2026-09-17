# Museu Nocturne — A Memória das Coisas
> **Exposição 034 (2026 — 2027) | Porto Alegre / Brasil — Est. 1987**  
> *Conceito Editorial: Dark Romantic Archival Editorial*

Uma experiência digital cinematográfica e interativa desenvolvida com rigor curatorial e estético de padrão internacional (Awwwards / FWA). O projeto investiga a persistência dos afetos retidos no linho desgastado, no mármore, no carvalho e na poeira mineral sob a penumbra de 45 lux.

---

## 🏛️ Identidade Visual & Conceito
- **Fórmula Visual:** `ARTE + MEMÓRIA + MATÉRIA + ARQUIVO`
- **Paleta Estrita:**
  - Carvão Profundo: `#12130F` / `#171814`
  - Marfim Envelhecido: `#D8D8BB` / `#ADAE91`
  - Ouro Antigo (< 5%): `#9A803D`
- **Tipografia Editorial:** *Bodoni Moda*, *Cormorant Garamond*, *Cinzel*, *Space Mono* e caligrafia cursiva *Alex Brush*.
- **Rigor Geométrico:** Ausência absoluta de cantos arredondados (`border-radius: 0px`).

---

## ✨ Recursos Técnicos & Motion Design
- **Hero Section Multicamadas Cinematográfica:**
  - Background com vídeo em loop contínuo (*ping-pong / boomerang*) a 60 FPS com textura analógica e vinheta escura.
  - Midground com feixe de luz de conservação (*Museum Spotlight*), micropartículas minerais em suspensão browniana lenta no Canvas e grade de coordenadas de tombo.
  - Foreground estável com revelação de abertura (*Line-Mask* + *Blur-to-Focus*).
  - Micro-parallax e spotlight reativo ao cursor no desktop.
- **Efeitos Inspirados no React Bits:**
  - *Spotlight Cards:* Iluminação radial dinâmica nos cards das obras e galerias.
  - *Tilted Cards:* Inclinação tridimensional controlada de até 2.5°.
  - *Magnetic Buttons:* Microatração de 3 a 5px nos botões de conversão e laudos.
  - *Decrypted Text:* Decodificação técnica de caracteres arcaicos de tombo.
  - *Retículo Técnico Contextual:* Mira de inspeção arquivística sobre fotografias de obras.
- **Storytelling Completo:** Manifesto, catálogo de obras, metodologia de conservação preventiva, visitas com controle ambiental, tabela de tombo com busca ao vivo e modal de laudos técnicos catalográficos.
- **Acessibilidade:** Suporte integral a `@media (prefers-reduced-motion: reduce)`.

---

## 🚀 Como Executar Localmente

Como o projeto é construído com HTML5 semântico, Vanilla CSS e JavaScript moderno nativo, basta servi-lo através de qualquer servidor HTTP estático:

```bash
# Utilizando Python 3:
python -m http.server 8080

# Ou utilizando Node (npx serve):
npx serve .
```

Acesse em seu navegador:
```
http://localhost:8080
```

---

## 📁 Estrutura de Arquivos

```
├── index.html              # Aplicação principal editorial
├── README.md               # Documentação institucional
├── .gitignore              # Configuração de arquivos ignorados
├── animacoes.md            # Especificações de motion design V1
├── animacoes2.md           # Diretrizes cinematográficas e Awwwards V2
├── DESIGN.md               # Sistema de design tokens e tipografia
├── lp.md                   # Diretrizes editoriais e de conteúdo
├── Mastrer3.md             # Especificação técnica master de arquitetura
└── assets/                 # Mídias e fotografias de conservação
    ├── hero_artwork.jpg
    ├── museum_gallery.jpg
    ├── object_017.jpg
    ├── object_041.jpg
    ├── object_052.jpg
    ├── video_hero.mp4
    └── video_hero_loop.mp4
```

---

## ⚖️ Licença
MUSEU NOCTURNE / PORTO ALEGRE / BRASIL — Direitos de arquivo e curadoria reservados.
