# Changelog — Tony's Auto Repair & Towing

## [v1.1.0] — 2026-05-25 (Session 2 — Design Refinement)

### Visual / Design
- **Hero**: Cambio de fondo negro-oscuro a gradiente azul profesional (`#0f2d4a → #1a4a7a → #2471a3 → #5dade2`)
- **Hero overlay**: Reducido de 75% opacidad negra a 20% para exponer el gradiente
- **Info-cards en hero**: Semi-transparentes con borde blanco sutil (`rgba(255,255,255,0.12)`)
- **Header**: Cambiado a negro sólido (`rgba(5,6,10,0.97)`) con borde naranja inferior para contraste en scroll

### Botones
- **btn-repair-link**: Cambiado de outline gris a sólido azul (`#0052CC`) — mismo peso visual que el botón de towing
- **btn-emergency**: Cambiado de rojo a naranja (`#FF6B00`) — consistente con el color de acción del sitio
- **Altura mínima**: `min-height: 52px` en ambos botones de tarjetas para igualar tamaño

### Imágenes
- **GRUA.png**: Reemplazada imagen rota de componente electrónico por foto profesional de flatbed tow truck
- Imagen copiada desde `C:\Users\hotde\Downloads\GRUA.png` al directorio del proyecto

### Mobile (390px)
- **Mapa**: `max-width: 100%`, `aspect-ratio: auto`, `min-height: 280px` — elimina overflow horizontal
- **Requirements grid**: Colapsado de 3 columnas a 1 columna en mobile
- **Info-cards**: Grid redefinido a `44px 1fr` con el `<p>` ocupando `grid-column: 1 / -1` — texto ya no se atasca en columna estrecha
- **Hero title**: Reducido a `36px` en mobile
- **Section titles**: Reducidos a `30px` en mobile

### Copy
- Botón towing: "Call Towing Dispatch (608) 867-7202" → "Call Now: (608) 867-7202" (cabe en una línea)
- Estimate description: Reescrita para mayor conversión y tono más cálido

## [v1.0.0] — 2026-05-24 (Session 1 — Creación inicial)

- Landing page completa: Hero, Stats bar, Service Cards (Repair + Towing), Dashboard section, Estimate section, Map section, Footer
- Paleta inicial: naranja `#FF6B00`, fondo oscuro, layout con CSS Grid + Flexbox
- Publicado en GitHub: `github.com/beto4400/tonys-auto-repair-madison`
- Publicado en Vercel: `tonys-auto-detail-repair.vercel.app`
