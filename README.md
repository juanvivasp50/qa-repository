# Proyecto 1 — Testing Manual: saucedemo.com

Proyecto de testing manual sobre una tienda online de demostración, cubriendo el flujo completo de compra: desde el inicio de sesión hasta la confirmación del pedido.

---

## Aplicación bajo prueba

**saucedemo.com** (Swag Labs) es una tienda online de demostración que simula un comercio electrónico real: catálogo de productos, carrito de compra y proceso de checkout.

La aplicación ofrece varios usuarios de acceso, cada uno con comportamientos distintos y defectos deliberados, lo que la convierte en un entorno adecuado para practicar detección y documentación de fallos.

---

## Alcance

Se probaron las siguientes áreas:

| Requisito | Área |
|---|---|
| REQ-01 | Login (usuarios válidos, credenciales incorrectas, cuenta bloqueada) |
| REQ-02 | Carrito (agregar y quitar artículos, contador) |
| REQ-03 | Checkout (campos obligatorios, validación de datos, finalización de compra) |
| REQ-04 | Catálogo de productos (nombre, precio, descripción, imagen) |

**Fuera de alcance:** procesamiento de pagos reales (la aplicación es una demo) y pruebas de rendimiento bajo carga.

---

## Resultados

**10 casos de prueba** ejecutados (TC-001 a TC-010) y **5 bugs reportados** (BUG-001 a BUG-005).

### Hallazgos destacados

**BUG-003 — El campo "Last Name" no recibe texto en el checkout**

El usuario avanza con normalidad hasta el formulario de datos personales. Al escribir en el campo "Last Name", el texto aparece en "First Name" y el campo queda vacío, lo que impide continuar y completar la compra.

*Severidad: Alta — Prioridad: Alta*

**BUG-001 — Las imágenes del catálogo no corresponden a los productos**

Todas las imágenes muestran el mismo contenido, sin relación con el artículo. La severidad es **baja** porque el defecto no bloquea la compra: el producto se agrega al carrito y el checkout se completa con normalidad. Sin embargo, la prioridad es **alta**, porque en una tienda real ningún cliente compraría un artículo cuya fotografía no puede ver.

Este caso ilustra que severidad y prioridad son ejes independientes: la primera mide el daño al sistema, la segunda la urgencia para el negocio.

---

## Estructura del repositorio

qa-portfolio/
├── caso-de-prueba/ Plan de pruebas y casos TC-001 a TC-010
├── reportes-de-bug/ Reportes BUG-001 a BUG-005 (formato de siete campos)
└── trazabilidad/ Matriz que vincula requisitos, casos de prueba y bugs

- **caso-de-prueba/** — Contiene el plan de pruebas (objetivo, alcance, riesgos, criterios de éxito) y cada caso documentado con ID, precondición, pasos, resultado esperado, resultado actual y estado.
- **reportes-de-bug/** — Cada bug sigue una estructura fija: título, severidad, prioridad, precondición, pasos para reproducir, resultado esperado y resultado actual.
- **trazabilidad/** — Matriz que conecta cada requisito con sus casos de prueba y los bugs asociados, permitiendo detectar huecos de cobertura de un vistazo.

---

## Técnicas aplicadas

- Partición de equivalencia y análisis de valores límite
- Testing exploratorio con charters (sesiones acotadas con objetivo definido)
- Trazabilidad de requisitos
- Clasificación de defectos por severidad y prioridad

---

## Entorno de pruebas

Navegador Chrome · saucedemo.com · Pruebas manuales ejecutadas por un tester
