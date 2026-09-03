# Historias de usuario

_Presentar al menos una historia de usuario representativa por módulo._
_Cada historia debe incluir formato clásico, criterios de aceptación y validación INVEST._

---

## HU-01 — [Ver rutina asignada]
| Campo | Detalle |
|-------|---------|
| Historia | Como cliente, quiero ver mi rutina asignada, para saber qué ejercicios tengo que hacer cada día.|
| Módulo |Módulo 5 — Rutinas|
| Requisitos relacionados | RF-15 |

### Criterios de aceptación

El cliente logueado visualiza su rutina activa dividida por días, mostrando para cada ejercicio: nombre, series, repeticiones y observaciones.

Si el cliente no posee una rutina asignada, el sistema muestra un mensaje informativo: "Aún no tienes una rutina asignada".

La consulta de la rutina debe responder en menos de 2 segundos y adaptarse correctamente a pantallas móviles.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |SI |Se puede programar la vista de rutina sin depender de que estén hechos otros módulos complejos.|
| Negociable |SI | El diseño (lista, tarjetas o pestañas por día) se puede acordar entre el equipo de desarrollo y diseño.|
| Valiosa |SI  | Le sirve al socio para ver sus ejercicios en el celular sin depender de pedirle la hoja de papel al profesor.|
| Estimable |SI  |Es una consulta simple a la base de datos, así que los programadores pueden calcular el tiempo fácilmente. |
| Pequeña |SI  |Es una tarea corta porque se enfoca únicamente en mostrar información en pantalla. |
| Verificable |SI  |Se prueba ingresando con un usuario que tenga rutina cargada y con otro que no tenga nada.|

---

## HU-02 — [Registrar asistencia del clinte]

| Campo | Detalle |
|-------|---------|
| Historia | Como administrativo, quiero registrar la asistencia de un socio ingresando su DNI, para validar su estado de pago y autorizar su ingreso.|
| Módulo |Módulo 3 — Asistencia y turnos |
| Requisitos relacionados | RF-06, RF-08|

### Criterios de aceptación

El recepcionista ingresa el DNI del cliente en la pantalla de entrada.

Si el cliente tiene el mes pago, el sistema guarda la fecha/hora de ingreso y muestra un cartel verde de "Acceso Permitido".

Si la cuota está vencida o el DNI no existe, muestra un cartel rojo de "Membresía Vencida" o "Usuario no encontrado".

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |SI  |La función de marcar la entrada opera de forma aislada una vez consultada la base de datos. |
| Negociable |SI  |Se puede acordar si el DNI se ingresa a mano en el teclado o si se usa un lector de código de barras.|
| Valiosa |SI  |Le sirve a la recepción para saber rápido quién puede pasar y quién tiene la cuota vencida. |
| Estimable |SI  |Es una verificación rápida de estado y una grabación de ficha de entrada.|
| Pequeña |SI  |Cumple un objetivo único y puntual que requiere pocos días de desarrollo. |
| Verificable |SI  |Se prueba ingresando el DNI de un alumno al día, uno vencido y un número que no exista. |
