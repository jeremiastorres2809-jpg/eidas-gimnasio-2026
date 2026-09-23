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

---

### HU-03 — [Registrar pagos]

| Campo | Detalle |
|------|--------|
| Historia | Como administrativo, quiero registrar pagos de membresías, para llevar el control de los ingresos. |
| Módulo | Módulo 2 — Pagos |
| Requisitos relacionados | RF-05 |

#### Criterios de aceptación

El sistema permite registrar un pago con monto, fecha y socio asociado.

El estado de pago del socio se actualiza correctamente.

La operación debe completarse en menos de 2 segundos.

#### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|------------|------------|
| Independiente | SI | No depende de otros módulos. |
| Negociable | SI | Puede cambiar el método de pago. |
| Valiosa | SI | Permite controlar ingresos. |
| Estimable | SI | Operación simple. |
| Pequeña | SI | Funcionalidad puntual. |
| Verificable | SI | Se prueba registrando pagos. |

---

### HU-04 — [Registrar socio]

| Campo | Detalle |
|------|--------|
| Historia | Como administrativo, quiero registrar nuevos socios, para mantener actualizada la base de datos. |
| Módulo | Módulo 1 — Gestión de socios |
| Requisitos relacionados | RF-01 |

#### Criterios de aceptación

El sistema permite ingresar los datos personales del socio.

El sistema guarda correctamente la información.

El socio queda disponible para futuras operaciones.

#### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|------------|------------|
| Independiente | SI | No depende de otros módulos complejos. |
| Negociable | SI | Se pueden ajustar los campos requeridos. |
| Valiosa | SI | Permite registrar clientes. |
| Estimable | SI | Es una operación simple. |
| Pequeña | SI | Función puntual. |
| Verificable | SI | Se prueba registrando un socio. |

---

### HU-05 — [Consultar estado de pago]

| Campo | Detalle |
|------|--------|
| Historia | Como cliente, quiero consultar mi estado de pago, para saber si estoy al día con la membresía. |
| Módulo | Módulo 2 — Pagos |
| Requisitos relacionados | RF-06 |

#### Criterios de aceptación

El cliente puede visualizar si su membresía está activa o vencida.

El sistema muestra la información de manera clara.

La consulta se realiza en menos de 2 segundos.

#### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|------------|------------|
| Independiente | SI | Consulta independiente. |
| Negociable | SI | Puede cambiar la forma de visualización. |
| Valiosa | SI | Permite al cliente conocer su estado. |
| Estimable | SI | Consulta simple. |
| Pequeña | SI | Función puntual. |
| Verificable | SI | Se prueba con distintos estados. |

---

### HU-06 — [Gestionar turnos]

| Campo | Detalle |
|------|--------|
| Historia | Como administrativo, quiero gestionar los turnos, para evitar superposición de horarios. |
| Módulo | Módulo 3 — Turnos |
| Requisitos relacionados | RF-09 |

#### Criterios de aceptación

El sistema permite crear, modificar y eliminar turnos.

El sistema evita superposición de horarios.

Los turnos se visualizan correctamente.

#### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|------------|------------|
| Independiente | SI | Puede funcionar como módulo separado. |
| Negociable | SI | Puede variar la lógica de turnos. |
| Valiosa | SI | Mejora la organización del gimnasio. |
| Estimable | SI | Complejidad media. |
| Pequeña | SI | Alcance controlado. |
| Verificable | SI | Se prueba creando turnos. |