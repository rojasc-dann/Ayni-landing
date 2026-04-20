# High-Altitude Digital Editorial — Design System

> Sistema de diseño oficial para la landing page de **Ayni.AI**.
> Toda decisión de UI/UX debe respetar estas reglas sin excepción.

---

## 1. Visión Creativa: "The Atmospheric Summit"

### Estética

- **Prohibido** el estilo "SaaS estándar" (bloques simétricos, colores planos, layout genérico).
- Priorizar **grandes espacios negativos**, **asimetría intencional** y **profundidad atmosférica**.
- La interfaz debe sentirse como un paisaje etéreo de alta montaña: expansivo, misterioso, profundo.

### Estructura

- **Prohibido** el uso de bordes sólidos de 1px.
- La jerarquía visual se define mediante **cambios tonales** y **capas de fondo**, nunca con líneas.

---

## 2. Tokens de Diseño

### Colores — Surface Hierarchy

| Token                    | Valor      | Uso                     |
| ------------------------ | ---------- | ----------------------- |
| `surface`                | `#0F172A`  | Fondo principal         |
| `surface-container-low`  | _derivado_ | Bloques estructurales   |
| `surface-container-high` | _derivado_ | Tarjetas y contenedores |

> **Nota**: Los valores derivados deben calcularse como variaciones tonales del `surface` base,
> subiendo luminosidad en HSL. Se definirán en la configuración de Tailwind v4.

### Colores — Acentos

| Token       | Valor     | Uso                                |
| ----------- | --------- | ---------------------------------- |
| `primary`   | `#E0B3FF` | CTAs, brillos, elementos de acción |
| `secondary` | `#6B21A8` | Morado profundo, fondos de énfasis |
| `tertiary`  | `#7E87FF` | Periwinkle, indicadores de IA      |

### Colores — Auxiliares

| Token             | Valor                        | Uso                       |
| ----------------- | ---------------------------- | ------------------------- |
| `surface_variant` | `surface` al 40% de opacidad | Glassmorphism             |
| `outline_variant` | `surface` al 15% de opacidad | Ghost borders (solo a11y) |

### Tipografía

| Rol       | Familia           | Propiedades                                                    |
| --------- | ----------------- | -------------------------------------------------------------- |
| Headlines | **Space Grotesk** | `font-weight: 700`, `letter-spacing: -0.02em` (tracking tight) |
| Body      | **Manrope**       | `font-weight: 300–400`, `letter-spacing: normal`               |

> Ambas fuentes se cargan desde Google Fonts.
> Space Grotesk: weights 500, 700.
> Manrope: weights 300, 400, 500.

---

## 3. Reglas de Componentes

### 3.1 Glassmorphism

Los elementos flotantes **deben** usar:

```css
background: rgba(15, 23, 42, 0.4); /* surface_variant al 40% */
backdrop-filter: blur(24px); /* backdrop-blur-md */
-webkit-backdrop-filter: blur(24px);
```

### 3.2 Botones "Luminous"

Los botones primarios llevan un **gradiente de `primary` a `secondary`**:

```css
background: linear-gradient(135deg, #e0b3ff, #6b21a8);
```

- Hover: aumentar luminosidad del gradiente un 10%.
- Active: reducir luminosidad un 5%.
- Siempre con `border-radius` generoso (12px+).
- Sombra sutil con el color `primary` al 25% de opacidad.

### 3.3 La Regla de No-Dividers

- **Nunca** usar `<hr>` ni bordes para separar secciones.
- Usar espacios verticales de **64px** u **80px** entre secciones.
- La separación se logra con cambio tonal de fondo, no con líneas.

### 3.4 Ghost Borders

Si es **estrictamente necesario** para accesibilidad:

```css
outline: 1px solid rgba(15, 23, 42, 0.15); /* outline_variant */
```

- Solo usar cuando un elemento interactivo necesita indicador de foco visible.
- Nunca como decoración.

---

## 4. Efectos Atmosféricos

### Profundidad Atmosférica

- Usar gradientes radiales sutiles como capas de fondo.
- Orbs de luz difusa con los colores `primary` y `tertiary` al 5–15% de opacidad.
- Noise texture overlay sutil para dar materialidad.

### Micro-Animaciones

- Transiciones suaves (300ms–500ms) con `ease-out`.
- Hover states con `transform: translateY(-2px)` y cambio de opacidad.
- Evitar animaciones bruscas o rebotes exagerados.

---

## 5. Layout & Spacing

### Principios

- **Asimetría intencional**: los elementos no necesitan estar centrados simétricamente.
- **Espacios negativos generosos**: mínimo 64px entre secciones, 80px preferido.
- **Max-width**: contenido principal a `max-w-7xl` (1280px) con padding lateral generoso.

### Grid

- CSS Grid y Flexbox, nunca tablas para layout.
- Las columnas no necesitan ser iguales; la asimetría es parte del diseño.

---

## 6. Stack Técnico

| Herramienta  | Versión  | Notas                          |
| ------------ | -------- | ------------------------------ |
| Astro        | 6.x      | Framework principal            |
| Tailwind CSS | 4.x      | Via `@tailwindcss/vite` plugin |
| Runtime      | Bun      | Lock file: `bun.lock`          |
| Node         | ≥22.12.0 | Engine mínimo                  |
