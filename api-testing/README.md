# Proyecto 2 - API Testing

Proyecto de testing manual sobre API de demostración, cubriendo los 4 métodos de HTTP (GET, POST, PUT y DELETE) para poder obtener la base de datos de usuarios, crear usuarios, modificar y eliminar utilizando Postman. 

---

## Aplicación bajo prueba

**reqres.in** API REST pública y gratuita en línea que sirve como un entorno de prueba para desarrolladores, permitiendo simular solicitudes HTTP (como GET, POST, PUT, DELETE) sin necesidad de configurar un servidor o un backend.

---

## Alcance

Se probaron las siguientes áreas:

| Requisito | Área |
|---|---|
| API-001 | GET - Lista de usuarios (page, per_page, total, total_pages, array data) |
| API-002 | POST - Creación de usuarios (datos enviados(name y job), id y createdAt) |
| API-003 | PUT - Modificar usuarios (datos enviados,(name y job) updatedAt) |
| API-004| DELETE - Eliminar usuarios |

**Fuera de alcance:** 

Autenticación y permisos, Rendimiento y Seguridad.

---

## Resultados

**4 casos de prueba** ejecutados (API-001 a API-004).

### Hallazgos destacados

**API-004 — el DELETE que devuelve 204 pero no borra nada. Y sobre todo, que lo verificaste con un GET posterior en vez de fiarte del código de respuesta.**
El hallazgo de validación — la API acepta cualquier dato en el POST (nombres numéricos, campos vacíos) sin validar.

---

## Estructura del repositorio

qa-portfolio/API-Testing/
├── API Testing.postman_colletion.json/ Prueba de los 4 métodos en Postman
├── README.md/ Documento que estructura el test.
└── casos-de-prueba.md/ Todos los casos de prueba documentados. 

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
