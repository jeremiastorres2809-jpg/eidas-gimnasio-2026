## Parte A — Historias verticales

### Historia 1 — Registrar socio

| Campo | Detalle |
|------|--------|
| Historia | Como administrativo, quiero registrar un socio con su nombre y teléfono, para que quede en la lista y pueda usar el gimnasio. |

**Criterios de aceptación**

1. Si completo nombre y teléfono y confirmo, el socio queda guardado y aparece en la tabla de socios.
2. Si falta el nombre o el teléfono, el sistema no guarda y pide completar los campos.
3. Si ya existe un socio con el mismo teléfono, el sistema avisa y no lo duplica.

---

### Historia 2 — Registrar pago de membresía

| Campo | Detalle |
|------|--------|
| Historia | Como administrativo, quiero registrar el pago de un socio con monto y fecha, para llevar el control de quién tiene la cuota al día. |

**Criterios de aceptación**

1. Si busco a un socio existente e ingreso un monto numérico mayor a cero y una fecha, el pago se guarda.
2. El pago guardado aparece en la lista de últimos pagos de ese socio.
3. Si el monto no es numérico o es menor o igual a cero, el sistema muestra error y no guarda.

---

### Historia 3 — Registrar asistencia

| Campo | Detalle |
|------|--------|
| Historia | Como administrativo, quiero registrar la asistencia de un socio, para saber cuántas veces va al gimnasio. |

**Criterios de aceptación**

1. Si selecciono un socio y registro su asistencia, el sistema guarda la fecha y la hora.
2. Si el socio ya tiene asistencia registrada hoy, el sistema avisa y no duplica el registro.

---

### Historia 4 — Asignar rutina a un socio

| Campo | Detalle |
|------|--------|
| Historia | Como entrenador, quiero asignar una rutina a un socio, para que sepa qué ejercicios hacer. |

**Criterios de aceptación**

1. Si busco a un socio y elijo o creo una rutina, al confirmar queda asignada a ese socio.
2. La rutina asignada queda disponible para que el socio la vea.
3. Si el socio no existe, el sistema avisa y no asigna nada.

---

### Historia 5 — Ver rutina

| Campo | Detalle |
|------|--------|
| Historia | Como cliente, quiero ver mi rutina asignada, para saber qué ejercicios tengo que hacer cada día. |

**Criterios de aceptación**

1. Si tengo una rutina asignada, el sistema muestra cada ejercicio con sus series y repeticiones.
2. Si no tengo rutina, el sistema muestra un aviso en lugar de una pantalla vacía.

---

### Historia 6 — Ver horarios de clases

| Campo | Detalle |
|------|--------|
| Historia | Como cliente, quiero ver los horarios de las clases, para organizar cuándo ir al gimnasio. |

**Criterios de aceptación**

1. El sistema muestra la lista de clases con día, hora y entrenador.
2. Si no hay clases cargadas, el sistema muestra un aviso.

---

## Parte B — Los caminos que no salen bien

**Historia elegida:** Historia 2 — Registrar pago de membresía

| Pregunta | Qué hace el sistema | Quién decide (analista / negocio / técnica) |
|----------|---------------------|---------------------------------------------|
| ¿Qué pasa si el saldo es insuficiente? (equivalente: el monto ingresado es inválido, vacío, no numérico o menor o igual a cero) | Rechaza el pago, muestra un mensaje de error y no guarda nada. | Analista: define la regla de validación del monto. |
| ¿Qué pasa si el destinatario no existe o está dado de baja? (equivalente: el socio no existe o está dado de baja) | Si no existe, avisa y no permite registrar el pago. Si está de baja, avisa y pide confirmar antes de continuar. | Negocio: decide si se acepta el pago de un socio dado de baja (por ejemplo, para reactivarlo). |
| ¿Qué pasa si el sistema descuenta el saldo y falla antes de acreditarlo del otro lado? (equivalente: se guarda el pago pero falla la actualización de la cuota al día del socio) | El registro del pago y la actualización de la cuota se hacen juntos o no se hace ninguno. Si falla uno, se deshace todo y se muestra error. | Técnica: implementa que la operación sea atómica (todo o nada). |
| ¿Qué pasa si el usuario aprieta "Enviar" dos veces? (equivalente: aprieta "Registrar pago" dos veces) | Desactiva el botón después del primer clic. Si detecta un pago igual (mismo socio, monto y fecha) cargado hace segundos, pide confirmar antes de guardar otro. | Negocio: decide si dos pagos iguales el mismo día pueden ser válidos. Técnica: lo implementa. |
| ¿Qué pasa si se cae la conexión justo después de confirmar? | Al volver la conexión no reintenta solo. Muestra la lista de últimos pagos del socio para que el administrativo verifique si se guardó antes de volver a cargarlo. | Técnica: define cómo se confirma el guardado. Analista: define el aviso al usuario. |

---

## Parte C — Defensa

Se hace oral, en el plenario. No se documenta en este archivo.
