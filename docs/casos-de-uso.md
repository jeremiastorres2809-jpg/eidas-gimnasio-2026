# Casos de uso

## Diagrama general

**Actores identificados:**
- **Administrativo:** es quien atiende en recepción. Registra socios, pagos y asistencias.
- **Entrenador:** arma y asigna las rutinas de los socios.
- **Cliente:** el socio del gimnasio. Consulta su rutina y los horarios de las clases.


**Relaciones principales:**
- "Registrar pago", "Registrar asistencia" y "Asignar rutina" incluyen (`include`) "Buscar socio", porque en los tres casos siempre hay que encontrar primero al socio, y así el paso se define una sola vez.
- Iniciar sesión no se dibuja como (`include`): es una precondición de todos los casos de uso (el usuario tiene que haber iniciado sesión antes de empezar).

---

### CU-001 — Registrar socio

| Campo | Detalle |
|------|--------|
| Identificador | CU-001 |
| Nombre | Registrar socio |
| Descripción | Permite dar de alta un nuevo socio en el sistema. |
| Actores | Principal: Administrativo |
| Precondiciones | El usuario debe haber iniciado sesión. |
| Postcondiciones |  Éxito: socio registrado y visible en la lista de socios / Falla: no se guarda nada|

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|--|----------------|--------------------|
| 1 | Ingresa a la sección de socios | Muestra formulario |
| 2 |  Completa nombre, apellido, DNI y teléfono | Valida la información |
| 3 | Confirma | Guarda el socio y lo muestra en la lista  |

### Excepciones

| # | Situación | Respuesta del sistema |
|--|-----------|-----------------------|
| E1 | Falta algún dato obligatorio | Marca los campos vacíos y pide completarlos |
| E2 |Ya existe un socio con el mismo DNI  | el sistema avisa y no lo duplica|

| Campo | Detalle |
|------|--------|
| Rendimiento | Menor a 2 segundos |
| Frecuencia | ~12 altas por día |
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
| Precondiciones |  El usuario inició sesión como administrativo. El socio está registrado. |
| Postcondiciones | Éxito: pago guardado con su fecha de vencimiento / Falla: no se guarda nada |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|--|----------------|--------------------|
| 1 | Busca al socio por nombre o DNI | Muestra sus datos |
| 2 | Elige el plan e ingresa el monto y la fecha | Valida los datos y calcula la fecha de vencimiento |
| 3 | Confirma | Guarda el pago y lo muestra en "Últimos pagos" del socio |

### Excepciones

| # | Situación | Respuesta del sistema |
|--|-----------|-----------------------|
| E1 | El monto no es numérico o es menor o igual a cero | Muestra el error en el campo y no guarda |
| E2 | No se encuentra al socio | Avisa que no hay resultados y no permite continuar |
| E3 | El socio está dado de baja | Avisa y pide confirmar antes de continuar |
| E4 | Falla el guardado | Deshace la operación, muestra error y no deja el pago a medias |

| Campo | Detalle |
|------|--------|
| Rendimiento | Menor a 2 segundos |
| Frecuencia | ~20 pagos por día |
| Importancia | Alta |
| Urgencia | Alta |

---

### CU-003 — Registrar asistencia

| Campo | Detalle |
|------|--------|
| Identificador | CU-003 |
| Nombre | Registrar asistencia |
| Descripción | Permite registrar la asistencia de un socio al gimnasio. |
| Actores | Principal: Administrativo |
| Precondiciones | El usuario inició sesión como administrativo. El socio está registrado. |
| Postcondiciones | Éxito: asistencia guardada con fecha y hora / Falla: no se registra |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|--|----------------|--------------------|
| 1 | Busca al socio por nombre o DNI | Muestra sus datos y si tiene la cuota al día |
| 2 | Toca "Registrar asistencia" | Guarda la fecha y la hora del ingreso |

### Excepciones

| # | Situación | Respuesta del sistema |
|--|-----------|-----------------------|
| E1 | El socio ya registró asistencia hoy | Avisa y no duplica el registro |
| E2 | El socio tiene la cuota vencida | Muestra un aviso destacado; el administrativo decide si registra la asistencia igual |
| E3 | El socio está dado de baja | Avisa y no registra la asistencia |

| Campo | Detalle |
|------|--------|
| Rendimiento | Menor a 2 segundos |
| Frecuencia | ~80 asistencias por día |
| Importancia | Alta |
| Urgencia | Alta |

---

## CU-004 — Ver rutina

| Campo | Detalle |
|------|--------|
| Identificador | CU-004 |
| Nombre | Ver rutina |
| Descripción | Permite al socio ver la rutina que tiene asignada. |
| Actores | Principal: Cliente |
| Precondiciones | El cliente inició sesión. |
| Postcondiciones | Éxito: se muestran los ejercicios de la rutina / Falla: se muestra un aviso |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|--|----------------|--------------------|
| 1 | Entra a "Mi rutina" | Muestra cada ejercicio con sus series y repeticiones |

### Excepciones

| # | Situación | Respuesta del sistema |
|--|-----------|-----------------------|
| E1 | El socio no tiene rutina asignada | Muestra un aviso en lugar de una pantalla vacía |

| Campo | Detalle |
|------|--------|
| Rendimiento | Menor a 2 segundos |
| Frecuencia | ~70 consultas por día |
| Importancia | Alta |
| Urgencia | Media |

---

### CU-005 — Ver horarios

| Campo | Detalle |
|------|--------|
| Identificador | CU-005 |
| Nombre | Ver horarios |
| Descripción | Permite al socio consultar los horarios de las clases del gimnasio. |
| Actores | Principal: Cliente |
| Precondiciones | El cliente inició sesión. |
| Postcondiciones | Éxito: se muestran los horarios / Falla: se informa que no hay clases cargadas |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|--|----------------|--------------------|
| 1 | Selecciona la opción "Horarios" | Busca las clases cargadas |
| 2 | Revisa la información | Muestra la lista de clases con día, hora y entrenador |

### Excepciones

| # | Situación | Respuesta del sistema |
|--|-----------|-----------------------|
| E1 | No hay clases cargadas | Muestra un aviso |

| Campo | Detalle |
|------|--------|
| Rendimiento | Menor a 2 segundos |
| Frecuencia | ~50 consultas por día |
| Importancia | Media |
| Urgencia | Baja |

---

### CU-006 — Asignar rutina

| Campo | Detalle |
|------|--------|
| Identificador | CU-006 |
| Nombre | Asignar rutina |
| Descripción | Permite al entrenador asignar una rutina de ejercicios a un socio. |
| Actores | Principal: Entrenador |
| Precondiciones | El usuario inició sesión como entrenador. El socio está registrado. |
| Postcondiciones | Éxito: la rutina queda asignada y el socio puede verla / Falla: no se asigna nada |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|--|----------------|--------------------|
| 1 | Busca al socio por nombre o DNI | Muestra sus datos |
| 2 | Elige una rutina existente o crea una agregando ejercicios con series y repeticiones | Muestra el resumen de la rutina |
| 3 | Confirma la asignación | Guarda la rutina con la fecha de asignación |

### Excepciones

| # | Situación | Respuesta del sistema |
|--|-----------|-----------------------|
| E1 | No se encuentra al socio | Avisa y no asigna nada |
| E2 | La rutina no tiene ningún ejercicio | Pide agregar al menos uno antes de confirmar |

| Campo | Detalle |
|------|--------|
| Rendimiento | Menor a 2 segundos |
| Frecuencia | ~6 asignaciones por día |
| Importancia | Alta |
| Urgencia | Media |
