# Diseño UI

Las pantallas están pensadas para el uso diario en el gimnasio: a la gran parte de estas, las usa el administrativo en la secretaria, con un socio en el momento, y el resto las usan entrenadores y socios desde el celular (RNF-08).

---

## Pantalla / Módulo 1 — Login

**Wireframe:** diagramas/wireframes/login.png

**Patrones de diseño utilizados:** Formulario simple

**Justificación:** Es la puerta de entrada de todos los roles, así que tiene solo lo mas importante. El administrativo la usa al empezar el turno y no tiene que pensar nada: dos campos y un botón grande.

**Formulario (si aplica):**
- Cantidad de campos: usuario, contraseña
- Flujo: una sola pantalla
- Validaciones relevantes: campos obligatorios; si los datos son incorrectos se muestra un mensaje de texto

---

## Pantalla / Módulo 2 — Socios

**Wireframe:** diagramas/wireframes/socios.png

**Patrones de diseño utilizados:** Tabla + buscador + botón de acción principal

**Justificación:** Cuando llega un socio a secretaria, el administrativo lo necesita encontrar en segundos. Por eso el buscador (por nombre o telefono) está arriba de la lista, y el botón "+ Nuevo" a la vista para las altas.

**Formulario (si aplica):** El alta se hace en la pantalla siguiente (Nuevo socio).

---

## Pantalla / Modulo 3 — Pagos

**Wireframe:** diagramas/wireframes/pagos.png

**Patrones:** Formulario + tabla

**Justificación:** Se piden solo los datos necesarios para dar de alta (nombre, apellido, DNI y teléfono). Así el alta no demora la atención y el resto de los datos se pueden completar después. El DNI permite detectar si el socio ya existe (CU-001, E2).

**Formulario:**
- Cantidad de campos: 4 (nombre, apellido, DNI, teléfono), todos obligatorios
- Flujo: todo en una pantalla
- Validaciones relevantes: campos obligatorios; DNI no repetido (el error se muestra en texto)

---

## Pantalla / Módulo 4 — Pagos

**Wireframe:** diagramas/wireframes/pagos.png

**Patrones de diseño utilizados:** Formulario + buscador con sugerencias + tabla

**Justificación:** El campo "Socio" es un buscador con sugerencias: se escribe nombre o DNI y aparecen las coincidencias, igual que el paso 1 del CU-002 ("Busca al socio"). Debajo del formulario quedan los últimos pagos del socio, para ver su vencimiento y para verificar si un pago se guardó cuando se corta la conexión.

**Formulario:**
- Campos: socio (buscador), plan, monto, fecha
- Validaciones: el monto debe ser numérico y mayor a cero
- Flujo: una sola pantalla

---

## Pantalla / Módulo 5 — Asistencia

**Wireframe:** diagramas/wireframes/asistencia.png

**Patrones de diseño utilizados:** Buscador + tarjeta de estado + botón de acción grande

**Justificación:** Es la operación más frecuente (unas 80 veces por día), así que tiene que resolverse con dos pasos: buscar al socio y tocar un botón. La tarjeta muestra si la cuota está al día, con un texto y un color, para que el administrativo lo vea sin entrar a otra pantalla (CU-003, E2).

**Formulario:**
- Campos: socio (buscador)
- Validaciones: avisa si ya registró asistencia hoy, si tiene la cuota vencida o si está dado de baja
- Flujo: una sola pantalla

---

## Pantalla / Módulo 6 — Asignar rutina (entrenador)

**Wireframe:** diagramas/wireframes/asignar-rutina.png

**Patrones de diseño utilizados:** Buscador + tabla editable de ejercicios

**Justificación:** El entrenador arma la rutina con una tabla de ejercicios, series y repeticiones, igual que la ve el socio después. Puede elegir una rutina existente o crear una nueva, como indica el CU-006.

**Formulario:**
- Campos: socio, rutina, ejercicios (nombre, series, repeticiones)
- Validaciones: la rutina necesita al menos un ejercicio
- Flujo: una sola pantalla

---

## Pantalla / Módulo 7 — [Mi rutina] (cliente)

**Wireframe:** diagramas/wireframes/mi-rutina.png

**Patrones de diseño utilizados:** Lista de tarjetas

**Justificación:** El socio la mira desde el celular, de pie entre ejercicios. Cada ejercicio es una tarjeta grande con sus series y repeticiones, para leerla de un vistazo (CU-004).

---

## Pantalla / Módulo 8 — Horarios (cliente)

**Wireframe:** diagramas/wireframes/horarios.png

**Patrones de diseño utilizados:** Tabla

**Justificación:** El socio quiere saber cuándo hay clase y con quién para organizar su semana. Una tabla ordenada por día muestra todo junto, sin tener que abrir cada clase (CU-005).

---

## Consideraciones de accesibilidad

Pensadas para el uso desde el celular (RNF-08):

- Botones principales de al menos 44 píxeles de alto, para tocarlos con el pulgar sin errarle.
- Contraste alto: texto oscuro sobre fondo claro y texto blanco sobre botones de color.
- Los errores y avisos se muestran con texto, no solo con color rojo (por ejemplo, "Ya existe un socio con ese DNI").
- El estado de la cuota se indica con una etiqueta de texto ("Cuota al día" o "Cuota vencida") además del color.
- Formularios cortos y una sola pantalla por tarea, para usuarios no técnicos.
