# Skill: Local Business Landing Page (Static HTML/CSS)

> Template y proceso documentado basado en Tony's Auto Repair & Towing (Madison, WI)
> Reutilizable para: talleres, towing, cleaning companies, plomería, electricistas, etc.

---

## Stack
- HTML5 semántico puro
- CSS con Custom Properties (`--var`)
- Vanilla JS (solo para interactividad básica)
- Sin frameworks, sin npm, sin build step
- Deploy: GitHub → Vercel (CI/CD automático)

---

## Estructura de Archivos

```
proyecto/
├── index.html          # Única página
├── styles.css          # Todos los estilos
├── app.js              # JS mínimo (scroll, menú)
├── [IMAGEN].png        # Hero / imagen principal
├── .gitignore          # Vercel, .env, node_modules
├── CHANGELOG.md        # Historial de cambios
└── SKILL-*.md          # Este archivo (documentación)
```

---

## Secciones Estándar (orden recomendado)

1. **Header** — Logo + Nav + CTA rápido (número de teléfono)
2. **Hero** — Headline + Subheadline + 2 CTAs primarios + Info-cards
3. **Stats bar** — 3-4 números clave (años, servicios, disponibilidad)
4. **Service Cards** — 2 tarjetas máximo (servicio A vs servicio B)
5. **Trust/Feature section** — Fondo alternativo, bullets de confianza
6. **CTA section** — Formulario de estimado O número directo
7. **Map section** — Google Maps embed o imagen enlazada
8. **Footer** — Datos de contacto, navegación repetida, copyright

---

## Paleta de Colores por Tipo de Negocio

### Auto Repair / Towing
```css
--color-primary: #0052CC;    /* Azul confianza */
--color-action: #FF6B00;     /* Naranja urgencia */
--color-dark: #0f2d4a;       /* Hero background base */
--color-light: #F8F9FA;      /* Secciones alternas */
```

### Cleaning Company (sugerencia para siguiente proyecto)
```css
--color-primary: #0EA5E9;    /* Azul agua / limpieza */
--color-action: #22C55E;     /* Verde fresco */
--color-dark: #0C1A2E;       /* Hero oscuro */
--color-light: #F0FDF4;      /* Fondo secciones, tono verde suave */
```

---

## Hero Gradient (fórmula que funciona)

```css
.hero-section {
    background: linear-gradient(135deg,
        [color-oscuro] 0%,
        [color-medio] 45%,
        [color-claro] 80%,
        [highlight] 100%
    );
}
.hero-overlay {
    background: rgba(10, 25, 45, 0.15); /* MÁX 20% — dejar ver el gradiente */
}
```

---

## CSS Grid para Info-Cards (patrón anti-overflow)

```css
.info-card {
    display: grid;
    grid-template-columns: 44px 1fr;
    grid-template-rows: auto auto;
    gap: 8px;
}
.info-card p {
    grid-column: 1 / -1; /* CRÍTICO: el párrafo siempre ocupa ancho completo */
    grid-row: 2;
}
```

---

## Mobile-First Breakpoints

```css
/* Mobile: hasta 768px (default) */
.requirements-grid { grid-template-columns: 1fr; }
.hero-title { font-size: 36px; }

/* Tablet: 768px+ */
@media (min-width: 768px) {
    .requirements-grid { grid-template-columns: repeat(2, 1fr); }
}

/* Desktop: 1024px+ */
@media (min-width: 1024px) {
    .requirements-grid { grid-template-columns: repeat(3, 1fr); }
    .hero-title { font-size: 52px; }
}
```

---

## Botones — Regla de 2 pesos visuales

```css
/* Botón primario (acción urgente) */
.btn-primary {
    background: var(--color-action);
    color: #ffffff;
    min-height: 52px;
    padding: 14px 28px;
}

/* Botón secundario (mismo peso visual que primario) */
.btn-secondary {
    background: var(--color-primary);
    color: #ffffff;
    min-height: 52px;  /* IGUAL al primario — nunca diferentes alturas */
    padding: 14px 28px;
}
```

**Regla**: si hay 2 botones uno al lado del otro, `min-height` debe ser idéntico.

---

## Checklist de Deploy

- [ ] `.gitignore` incluye `.vercel`, `.env`, `node_modules`
- [ ] Imágenes optimizadas (PNG < 2MB, JPG < 500KB idealmente)
- [ ] No hay API keys ni credenciales en el código
- [ ] Meta title y description únicos en `<head>`
- [ ] Número de teléfono clickeable: `<a href="tel:+16085551234">`
- [ ] `git add`, `git commit`, `git push` → Vercel autodeploy en <2min
- [ ] Verificar en mobile real (o Playwright a 390px)

---

## Skills UX Recomendados para Este Stack

| Orden | Skill | Cuándo usarlo |
|-------|-------|---------------|
| 1 | `ui-designer` | Antes de escribir código — definir layout y paleta |
| 2 | `design:design-system` | Crear variables CSS y tokens desde el inicio |
| 3 | `design:ux-copy` | Mejorar headlines, CTAs, y copy de servicios |
| 4 | `design:design-critique` | Al finalizar — validar antes del deploy |
| 5 | `design:accessibility-review` | Opcional: si hay cliente corporativo o mayor de edad |

---

## Herramientas de Alineación (usar durante desarrollo)

- **Chrome DevTools Grid Inspector**: Activar en Elements → Layout → Grid overlays
- **Pesticide extension**: Muestra todos los bordes de elementos en tiempo real
- **Playwright resize**: `browser_resize(390, 844)` para simular iPhone 14 Pro

---

## Lecciones Aprendidas (Tony's)

1. **Info-card paragraph trap**: Si el `<p>` no tiene `grid-column: 1/-1`, queda atrapado en la columna del ícono (44px). Siempre declararlo explícitamente.
2. **Hero overlay muy oscuro**: El valor 0.75 mata cualquier gradiente. Usar máx 0.20.
3. **Botones de texto largo**: "Call Towing Dispatch (608) 867-7202" → 2 líneas en mobile. Máx 25 caracteres por botón.
4. **Vercel scope**: Usar `vercel --scope [org-id]` si hay múltiples orgs en la cuenta.
5. **GRUA.png en git**: Las imágenes del sitio SÍ van al repo (son el sitio). Solo excluir imágenes de trabajo/referencias que no se sirven al usuario.
