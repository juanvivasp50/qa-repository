# Casos de Prueba — saucedemo.com

Casos TC-001 a TC-010, cubriendo login, catálogo, carrito y checkout.

---

## TC-001 — Login exitoso con credenciales válidas

**Requisito:** REQ-01 Login

**Precondición:** El usuario tiene una cuenta activa (`standard_user`) y está en la pantalla de login.

**Pasos:**
1. Ingresar `standard_user` en el campo de usuario.
2. Ingresar `secret_sauce` en el campo de contraseña.
3. Hacer clic en el botón "Login".

**Resultado esperado:** El sistema redirige a la página del catálogo de productos.

**Resultado actual:** El sistema redirige a la página del catálogo de productos.

**Estado:** Pass

---

## TC-002 — Login con contraseña incorrecta

**Requisito:** REQ-01 Login

**Precondición:** El usuario está en la pantalla de login.

**Pasos:**
1. Ingresar un nombre de usuario válido.
2. Ingresar una contraseña incorrecta.
3. Hacer clic en el botón "Login".

**Resultado esperado:** El sistema muestra un mensaje de error y no permite el acceso.

**Resultado actual:** Muestra el mensaje "Username and password do not match any user in this service".

**Estado:** Pass

---

## TC-003 — Agregar un producto al carrito

**Requisito:** REQ-02 Carrito

**Precondición:** El usuario inició sesión correctamente y está en la pantalla del catálogo.

**Pasos:**
1. Seleccionar "Add to cart" en un producto.
2. Verificar que el icono del carrito muestra el número de artículos seleccionados.
3. Entrar al carrito y verificar que los artículos seleccionados están presentes.

**Resultado esperado:** Los artículos aparecen en el carrito y el contador refleja la cantidad agregada.

**Resultado actual:** Los artículos aparecen en el carrito y el contador muestra la cantidad correcta (3 artículos).

**Estado:** Pass

---

## TC-004 — Quitar un producto del carrito

**Requisito:** REQ-02 Carrito

**Precondición:** El usuario está en el carrito y ya seleccionó varios productos.

**Pasos:**
1. Entrar al carrito.
2. Seleccionar "Remove" en un producto.
3. Verificar que el artículo se ha quitado.

**Resultado esperado:** Los artículos se eliminan del carrito y el contador se actualiza.

**Resultado actual:** Los artículos se eliminan correctamente y el icono del carrito vuelve a mostrarse sin número.

**Estado:** Pass

---

## TC-005 — Completar el proceso de checkout

**Requisito:** REQ-03 Checkout

**Precondición:** El usuario tiene productos en el carrito y está listo para confirmar la compra.

**Pasos:**
1. Entrar al carrito y seleccionar "Checkout".
2. Rellenar la información de envío y datos personales.
3. Seleccionar "Finish".
4. Verificar que la compra se completa correctamente.

**Resultado esperado:** El checkout se completa sin problemas y se muestra el mensaje "Thank you for your order".

**Resultado actual:** El checkout se completa y aparece el mensaje de confirmación del despacho.

**Estado:** Pass

---

## TC-006 — Checkout dejando el campo "First Name" vacío

**Requisito:** REQ-03 Checkout

**Precondición:** El usuario tiene al menos un producto en el carrito y está en la pantalla de checkout (Your Information).

**Pasos:**
1. Dejar el campo "First Name" vacío.
2. Rellenar "Last Name" y "Zip Code" con datos válidos.
3. Hacer clic en "Continue".

**Resultado esperado:** El sistema muestra un mensaje de error indicando que el campo "First Name" es obligatorio.

**Resultado actual:** Aparece en rojo "Error: First Name is required" y el campo se marca como faltante.

**Estado:** Pass

---

## TC-007 — Checkout dejando el campo "Last Name" vacío

**Requisito:** REQ-03 Checkout

**Precondición:** El usuario tiene al menos un producto en el carrito y está en la pantalla de checkout (Your Information).

**Pasos:**
1. Dejar el campo "Last Name" vacío.
2. Rellenar "First Name" y "Zip Code" con datos válidos.
3. Hacer clic en "Continue".

**Resultado esperado:** El sistema muestra un mensaje de error indicando que el campo "Last Name" es obligatorio.

**Resultado actual:** Aparece en rojo "Error: Last Name is required" y el campo se marca como faltante.

**Estado:** Pass

---

## TC-008 — Checkout dejando el campo "Zip Code" vacío

**Requisito:** REQ-03 Checkout

**Precondición:** El usuario tiene al menos un producto en el carrito y está en la pantalla de checkout (Your Information).

**Pasos:**
1. Dejar el campo "Zip Code" vacío.
2. Rellenar "First Name" y "Last Name" con datos válidos.
3. Hacer clic en "Continue".

**Resultado esperado:** El sistema muestra un mensaje de error indicando que el campo "Zip Code" es obligatorio.

**Resultado actual:** Aparece en rojo "Error: Zip Code is required" y el campo se marca como faltante.

**Estado:** Pass

---

## TC-009 — Visualización del catálogo con `standard_user`

**Requisito:** REQ-04 Catálogo

**Precondición:** El usuario está en la pantalla de login.

**Pasos:**
1. Ingresar con `standard_user`.

**Resultado esperado:** Los artículos del catálogo se muestran correctamente con nombre, precio, descripción e imagen.

**Resultado actual:** Los artículos se muestran correctamente: los nombres concuerdan con las fotografías, y precios y descripciones aparecen bien.

**Estado:** Pass

---

## TC-010 — Visualización del catálogo con `problem_user`

**Requisito:** REQ-04 Catálogo

**Precondición:** El usuario está en la pantalla de login.

**Pasos:**
1. Ingresar con `problem_user`.

**Resultado esperado:** Los artículos del catálogo se muestran con la fotografía correspondiente a cada producto.

**Resultado actual:** Todas las fotografías muestran la misma imagen, sin relación con el artículo. Ninguna corresponde al producto.

**Estado:** Fail — ver BUG-001
