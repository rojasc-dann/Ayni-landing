# Component Rules — Andean High-Tech Editorial

> Reglas mandatorias para todos los componentes Astro de la landing page Ayni.AI.

---

## Reglas Generales

1. **Cada componente** debe ser un archivo `.astro` en `src/components/`.
2. **Prohibido** usar `<hr>`, bordes de 1px, o cualquier divisor visual lineal.
3. La separación entre secciones se logra con **spacing vertical** (64px / 80px) y **cambios tonales**.
4. Todos los elementos interactivos deben tener **IDs únicos y descriptivos** para testing.

---

## Tipografía en Componentes

```astro
<!-- Headlines: Space Grotesk -->
<h1 class="font-display font-bold tracking-tight">...</h1>
<h2 class="font-display font-bold tracking-tight">...</h2>

<!-- Body: Manrope -->
<p class="font-body font-light">...</p>
```

- `font-display` → Space Grotesk
- `font-body` → Manrope
- Headlines siempre `tracking-tight` (letter-spacing: -0.02em)
- Body siempre `font-light` (300) o `font-normal` (400)

---

## Clases de Utilidad Esperadas (Tailwind v4)

Se definirán como CSS custom properties en `global.css` con la sintaxis de Tailwind v4:

```css
@theme {
  --color-surface: #0f172a;
  --color-primary: #e0b3ff;
  --color-secondary: #6b21a8;
  --color-tertiary: #7e87ff;
  --font-family-display: "Space Grotesk", sans-serif;
  --font-family-body: "Manrope", sans-serif;
}
```

---

## Patrones de Componentes

### Hero Section

- Titular con **gradiente de texto** (`primary` → `tertiary`).
- Descripción en Manrope light.
- Fondo con **profundidad atmosférica**: orbs radiales difusos.
- CTA con botón "Luminous" (gradiente `primary` → `secondary`).
- Sin líneas divisorias. Espaciado vertical generoso.

### Cards / Tarjetas

- Background: `surface-container-high`.
- Glassmorphism: 40% opacidad + `backdrop-blur-md`.
- Sin bordes visibles (ghost border solo si es necesario para a11y).
- Hover: `translateY(-2px)` + sutil cambio de opacidad.

### Navigation

- Fija en top con glassmorphism.
- Logo + links minimalistas.
- Sin bordes inferiores; la separación es por contraste con el contenido.

### Sections

- Cada sección ocupa **full-width** del viewport.
- Contenido interno centrado con `max-w-7xl`.
- Separación: 64px–80px de spacing vertical.
- Cambio tonal de fondo entre secciones adyacentes.

---

## Accesibilidad

- Ghost borders (`outline_variant` al 15%) solo en elementos de foco.
- Color contrast ratio mínimo 4.5:1 para texto sobre `surface`.
- `primary` (#E0B3FF) sobre `surface` (#0F172A) = ratio ~10:1 ✓
- Alt text en todas las imágenes decorativas.
- Semantic HTML: `<header>`, `<main>`, `<section>`, `<footer>`.

---

## Prohibiciones Explícitas

| ❌ Prohibido                        | ✅ Usar en su lugar          |
| ----------------------------------- | ---------------------------- |
| `<hr>`                              | Spacing vertical 64px/80px   |
| `border: 1px solid`                 | Cambio tonal de fondo        |
| Colores planos genéricos            | Paleta del design system     |
| Layout simétrico de "SaaS template" | Asimetría intencional        |
| Sans-serif genérica (Arial, etc.)   | Space Grotesk + Manrope      |
| Animaciones con bounce              | Ease-out suave (300ms–500ms) |
