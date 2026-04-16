# Design System Rules — Andean High-Tech Editorial

> Reglas estrictas. Aplicar **siempre** al escribir código para este proyecto.

## Identidad

- Proyecto: **Ayni.AI** — Landing Page
- Design System: **Andean High-Tech Editorial**
- Visión: **"The Ethereal Altiplano"**

## Reglas Inquebrantables

### 1. No SaaS genérico

Toda decisión visual debe alejarse del estilo genérico de SaaS.
Priorizar espacios negativos, asimetría, y profundidad atmosférica.

### 2. No bordes sólidos

Prohibido `border: 1px solid`. La jerarquía se define por
cambios tonales y capas de fondo.

### 3. No divisores

Prohibido `<hr>` y bordes separadores. Usar spacing
vertical de 64px u 80px entre secciones.

### 4. Glassmorphism obligatorio

Elementos flotantes: `surface_variant` al 40% opacidad + `backdrop-blur-md` (24px).

### 5. Botones Luminous

CTAs primarios: gradiente de `primary` (#E0B3FF) a `secondary` (#6B21A8).

### 6. Ghost Borders solo para a11y

Si es estrictamente necesario: `outline_variant` al 15% opacidad.
Nunca como decoración.

### 7. Tipografía estricta

Headlines: **Space Grotesk** (tracking tight).
Body: **Manrope** (light/regular).

### 8. Paleta de colores

- `surface`: #0F172A
- `primary`: #E0B3FF
- `secondary`: #6B21A8
- `tertiary`: #7E87FF

### 9. Profundidad atmosférica

Usar gradientes radiales sutiles, orbs de luz difusa,
y noise textures como capas de fondo.

### 10. Animaciones suaves

Transiciones 300ms–500ms con ease-out.
Hover: translateY(-2px) + cambio de opacidad.
Prohibido: bounce, spring exagerado.
