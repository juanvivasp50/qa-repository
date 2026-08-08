# Plan de Pruebas — saucedemo.com

Adaptado según ISO/IEC/IEEE 29119-3:2013, cláusula 2.2.2 (conformidad adaptada)

---

## 1. Objetivo

Verificar que las funciones de login, catálogo, carrito y checkout funcionan correctamente.

## 2. Alcance

- **Login** — usuario válido, contraseña incorrecta, cuenta bloqueada
- **Catálogo** — visualización de productos (nombre, precio, descripción, imagen)
- **Carrito** — agregar y quitar productos, contador de artículos
- **Checkout** — validación de campos obligatorios y finalización de compra

## 3. Fuera de alcance

- Pagos reales (la aplicación es una demo y no procesa transacciones)
- Rendimiento bajo carga (fuera del alcance de las pruebas manuales)

## 4. Registro de riesgos

| Riesgo | Impacto |
|---|---|
| Si el login falla, el usuario no puede acceder | Ninguna compra es posible |
| Si no se pueden agregar artículos al carrito | El usuario no puede comprar |
| Si el checkout no permite avanzar | El usuario abandona la compra por frustración |
| Si un campo obligatorio queda vacío sin aviso | El usuario no sabe cómo corregir el error |

## 5. Criterios de éxito

- Todos los casos de prueba críticos (login y checkout) deben pasar.
- Los defectos pendientes deben ser de severidad baja y estar documentados.

## 6. Recursos y entorno

- 1 tester
- Navegador Chrome
- saucedemo.com
