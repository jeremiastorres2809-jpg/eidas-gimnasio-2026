# Casos de uso

## Diagrama general

_Incluir el código PlantUML en `diagramas/casos-de-uso.puml`._
_Visualizar en [plantuml.com](https://www.plantuml.com/plantuml/uml/)._

_Describir brevemente los actores identificados y las relaciones principales (include, extend)._

---

### CU-001 — Registrar socio

| Campo | Detalle |
|------|--------|
| Identificador | CU-001 |
| Nombre | Registrar socio |
| Descripción | Permite dar de alta un nuevo socio en el sistema. |
| Actores | Principal: Administrativo |
| Precondiciones | El usuario debe haber iniciado sesión. |
| Postcondiciones | Éxito: socio registrado / Falla: datos inválidos |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|--|----------------|--------------------|
| 1 | Ingresa a la sección de socios | Muestra formulario |
| 2 | Completa los datos | Valida la información |
| 3 | Confirma | Guarda el socio |

### Excepciones

| # | Situación | Respuesta del sistema |
|--|-----------|-----------------------|
| E1 | Faltan datos | Pide completar los campos |
|E2 |El socio ya existe |Mismo dni o teléfono | el sistema avisa y no lo duplica|
| Campo | Detalle |
|------|--------|
| Rendimiento | Menor a 2 segundos |
| Frecuencia | Alta |
| Importancia | Alta |
| Urgencia | Alta |

---

### CU-002 — Registrar pago

| Campo | Detalle |
|------|--------|
| Identificador | CU-002 |
| Nombre | Registrar pago |
| Descripción | Permite registrar el pago de la membresía de un socio. |
| Actores | Principal: Administrativo |
| Precondiciones | El socio debe existir |
| Postcondiciones | Pago registrado correctamente |

### Secuencia normal

| # | Acción | Reacción |
|--|--------|----------|
| 1 | Busca un socio | Muestra sus datos |
| 2 | Ingresa el pago | Valida los datos |
| 3 | Confirma | Guarda el pago |

### Excepciones

| # | Situación | Respuesta |
|--|-----------|-----------|
| E1| Datos incorrectos | Muestra error |
| E2| Monto no numérico o <= a cero | muestra error| 
|E3 | El socio no se encuentra | muestra aviso|
| Campo | Detalle |
|------|--------|
| Rendimiento | Menor a 2 segundos |
| Frecuencia | Alta |
| Importancia | Alta |
| Urgencia | Alta |

---

### CU-003 — Registrar asistencia

| Campo | Detalle |
|------|--------|
| Identificador | CU-003 |
| Nombre | Registrar asistencia |
| Descripción | Permite registrar la asistencia de un socio al gimnasio. |
| Actores | Administrativo |
| Precondiciones | El socio debe existir |
| Postcondiciones | Asistencia registrada |

### Secuencia normal

| # | Acción | Reacción |
|--|--------|----------|
| 1 | Selecciona un socio | Muestra datos |
| 2 | Registra asistencia | Guarda fecha y hora |

### Excepciones

| # | Situación | Respuesta |
|--|-----------|-----------|
| E1 | Error del sistema | Muestra mensaje |
|E2 | El socio ya registró asistencia hoy | el sistema avisa y no duplica el registro|
| Campo | Detalle |
|------|--------|
| Rendimiento | Menor a 2 segundos |
| Frecuencia | Alta |
| Importancia | Alta |
| Urgencia | Media |

---

### CU-004 — Ver rutina

| Campo | Detalle |
|------|--------|
| Identificador | CU-004 |
| Nombre | Ver rutina |
| Descripción | Permite al socio ver la rutina que tiene asignada. |
| Actores | Cliente |
| Precondiciones | Usuario logueado |
| Postcondiciones | Se muestra la rutina |

### Secuencia normal

| # | Acción | Reacción |
|--|--------|----------|
| 1 | Entra a su rutina | El sistema muestra los ejercicios |

### Excepciones

| # | Situación | Respuesta |
|--|-----------|-----------|
| E1 | No tiene rutina | Muestra aviso |

| Campo | Detalle |
|------|--------|
| Rendimiento | Menor a 2 segundos |
| Frecuencia | Media |
| Importancia | Alta |
| Urgencia | Media |

---

### CU-005 — Ver horarios

| Campo | Detalle |
|------|--------|
| Identificador | CU-005 |
| Nombre | Ver horarios |
| Descripción | Permite al socio consultar los horarios de las clases del gimnasio. |
| Actores | Principal: Cliente / Secundario: Sistema |
| Precondiciones | El socio está registrado y tiene acceso al sistema. |
| Postcondiciones | Éxito: se muestran los horarios / Falla: se informa que no hay clases cargadas |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|--|----------------|--------------------|
| 1 | Selecciona la opción "Ver horarios" | Busca las clases cargadas |
| 2 | Revisa la información | Muestra la lista de clases con día, hora y entrenador |

### Excepciones

| # | Situación | Respuesta del sistema |
|--|-----------|-----------------------|
| E1 | No hay clases cargadas | Muestra un aviso |
| E2 | Error del sistema | Muestra un mensaje de error |

| Campo | Detalle |
|------|--------|
| Rendimiento | Menor a 2 segundos |
| Frecuencia | Alta |
| Importancia | Media |
| Urgencia | Baja |

---

## Excepciones sugeridas para agregar a los CU existentes

- **CU-001:** E2 — El socio ya existe (mismo email o teléfono) → el sistema avisa y no lo duplica.
- **CU-002:** E2 — Monto no numérico o menor o igual a cero → muestra error. E3 — El socio no se encuentra → muestra aviso.
- **CU-003:** E2 — El socio ya registró asistencia hoy → el sistema avisa y no duplica el registro.
