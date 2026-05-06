# Errores de accesibilidad introducidos

Página revisada: `index.html`. Los errores son deliberados para el ejercicio y no deberían mantenerse en una web real.

## 1.1 Alternatives textuals

| Nº | WCAG | Error introducido | Dónde está | Qué conlleva | Valoración WCAG | Detección |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | 1.1.1 Contenido no textual | Imagen informativa sin `alt`. | Galería, primera imagen de `#galeria`. | Un lector de pantalla no recibe la información de la imagen. | Nivel A, falla. | Automática. |

## 1.3 Adaptable

| Nº | WCAG | Error introducido | Dónde está | Qué conlleva | Valoración WCAG | Detección |
| --- | --- | --- | --- | --- | --- | --- |
| 2 | 1.3.1 Información y relaciones | Campos de formulario sin `label` asociado; usan solo `placeholder`. | Formulario de `#contacte`. | La relación campo-etiqueta no es robusta y puede perderse al escribir. | Nivel A, falla. | Automática/manual. |
| 3 | 1.3.1 Información y relaciones | Dos controles comparten el mismo `id="client"`. | Inputs de nombre y email en `#contacte`. | Rompe asociaciones programáticas y puede confundir tecnologías de apoyo. | Nivel A, falla. | Automática. |
| 4 | 1.3.2 Secuencia significativa | Orden de tabulación alterado con `tabindex` no secuencial. | Menú principal y CTA de cabecera. | La navegación por teclado no sigue el orden visual ni lógico. | Nivel A, falla. | Manual. |

## 1.4 Distingible

| Nº | WCAG | Error introducido | Dónde está | Qué conlleva | Valoración WCAG | Detección |
| --- | --- | --- | --- | --- | --- | --- |
| 5 | 1.4.1 Uso del color | La disponibilidad de planes se comunica principalmente con puntos verde/coral. | Tarjetas de precios en `#preus`. | Usuarios con daltonismo o lectores de pantalla pueden perder el significado si no perciben el color. | Nivel A, falla parcial. | Manual. |
| 6 | 1.4.3 Contraste mínimo | Texto gris muy claro sobre blanco. | `.hint-low` en el formulario. | Lectura difícil para personas con baja visión. | Nivel AA, falla. | Automática. |
| 7 | 1.4.4 Cambio de tamaño del texto | Ayuda del formulario con altura fija y `overflow:hidden`. | `.hint-low`. | Al ampliar texto puede cortarse contenido. | Nivel AA, falla. | Manual. |
| 8 | 1.4.11 Contraste no textual | Foco visible eliminado con `outline: 1px solid transparent`. | Enlaces, botones y campos con `:focus`. | Usuarios de teclado no pueden localizar con claridad el elemento activo. | Nivel AA, falla. | Automática/manual. |

## 2.2 Temps suficient

| Nº | WCAG | Error introducido | Dónde está | Qué conlleva | Valoración WCAG | Detección |
| --- | --- | --- | --- | --- | --- | --- |
| 9 | 2.2.2 Pausar, detener, ocultar | Aviso promocional parpadeante sin control para detenerlo. | `.flash-note` en la barra superior. | Puede distraer y dificulta la lectura. | Nivel A, falla. | Manual. |

## 2.3 Convulsions

| Nº | WCAG | Error introducido | Dónde está | Qué conlleva | Valoración WCAG | Detección |
| --- | --- | --- | --- | --- | --- | --- |
| 10 | 2.3.1 Tres destellos o por debajo del umbral | Simulación de destello rápido mediante animación CSS. | `@keyframes softFlash` aplicado a `.flash-note`. | Aunque se usan tonos poco agresivos, representa un patrón que debe evitarse o controlarse. | Nivel A, riesgo/falla didáctica. | Manual. |

## 2.4 Navegable

| Nº | WCAG | Error introducido | Dónde está | Qué conlleva | Valoración WCAG | Detección |
| --- | --- | --- | --- | --- | --- | --- |
| 11 | 2.4.1 Evitar bloques | No hay enlace de salto al contenido principal. | Inicio del `body`. | Usuarios de teclado deben recorrer cabecera y menú en cada carga. | Nivel A, falla. | Manual. |
| 12 | 2.4.3 Orden del foco | El CTA tiene `tabindex="1"` y los enlaces del menú saltan de `2` a `5`. | Header. | El foco se mueve de forma inesperada. | Nivel A, falla. | Manual. |
| 13 | 2.4.7 Foco visible | El estilo de foco es transparente. | Regla CSS global de `:focus`. | No hay indicador visual suficiente para navegación por teclado. | Nivel AA, falla. | Automática/manual. |
| 14 | 2.4.4 Propósito del enlace en contexto | Enlaces de idioma apuntan al mismo destino sin explicar cambio real. | Footer, columna “Idiomes”. | El propósito puede resultar ambiguo fuera de contexto. | Nivel A, falla parcial. | Manual. |

## 3.1 Legible

| Nº | WCAG | Error introducido | Dónde está | Qué conlleva | Valoración WCAG | Detección |
| --- | --- | --- | --- | --- | --- | --- |
| 15 | 3.1.1 Idioma de la página | El documento se declara en catalán, pero mezcla español e inglés sin estructura suficiente. | `html lang="ca"` y textos de promoción/footer. | La pronunciación por lector de pantalla puede ser incorrecta en otros idiomas. | Nivel A, falla parcial. | Manual. |
| 16 | 3.1.2 Idioma de las partes | Fragmentos en inglés y español no usan `lang`. | “May promo”, “Your plants are watered and stable”, “Fragmentos en español”. | Las tecnologías de asistencia no cambian reglas de pronunciación. | Nivel AA, falla. | Manual. |

## 3.2 Predictible

| Nº | WCAG | Error introducido | Dónde está | Qué conlleva | Valoración WCAG | Detección |
| --- | --- | --- | --- | --- | --- | --- |
| 17 | 3.2.1 Al recibir el foco | Al enfocar el selector del plan se cambia automáticamente el hash a `#preus`. | JavaScript del formulario. | Cambio de contexto inesperado al navegar por teclado o lector de pantalla. | Nivel A, falla. | Manual. |

## 3.3 Assistència a l'entrada

| Nº | WCAG | Error introducido | Dónde está | Qué conlleva | Valoración WCAG | Detección |
| --- | --- | --- | --- | --- | --- | --- |
| 18 | 3.3.1 Identificación de errores | El formulario solo muestra “Error. Revisa el formulari.” | `submit` de `#bookingForm`. | No identifica qué campo falla. | Nivel A, falla. | Manual. |
| 19 | 3.3.2 Etiquetas o instrucciones | Las instrucciones obligatorias están solo en placeholders y una ayuda de bajo contraste. | Campos del formulario. | El usuario puede no saber qué datos son requeridos cuando el placeholder desaparece. | Nivel A, falla. | Automática/manual. |

## 4.1 Compatible

| Nº | WCAG | Error introducido | Dónde está | Qué conlleva | Valoración WCAG | Detección |
| --- | --- | --- | --- | --- | --- | --- |
| 20 | 4.1.1 Análisis sintáctico | IDs duplicados en el DOM. | `id="client"` repetido. | Puede romper referencias y scripts; afecta compatibilidad. | Nivel A, falla en WCAG 2.1; obsoleto en WCAG 2.2 pero útil para compatibilidad. | Automática. |
| 21 | 4.1.2 Nombre, función, valor | Botón de menú móvil no expone estado `aria-expanded` ni relación `aria-controls`. | `#menuButton`. | Tecnologías de asistencia no conocen si el menú está abierto o cerrado. | Nivel A, falla. | Automática/manual. |

## Resumen por pauta solicitada

- 1.1: 1 error.
- 1.3: 2 errores diferentes.
- 1.4: 4 errores diferentes.
- 2.2: 1 error.
- 2.3: 1 error simulado sin intención de generar riesgo real.
- 2.4: 4 errores diferentes.
- 3.1: 2 errores diferentes.
- 3.2: 1 error.
- 3.3: 2 errores diferentes.
- 4.1: 2 errores diferentes.

## Revisión automática prevista

Herramientas como Axe, Lighthouse o TAW deberían detectar con facilidad la imagen sin `alt`, IDs duplicados, parte de los problemas de contraste, algunos campos sin nombre accesible robusto y carencias ARIA del botón de menú. Requieren revisión manual el orden lógico del foco, el cambio de contexto al enfocar, el uso real del color como único canal, los cambios de idioma sin marcar y el impacto de las animaciones.
