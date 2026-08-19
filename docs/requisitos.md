# Requisitos del sistema

## Descripción del sistema

El sistema consiste en una aplicación web orientada a la gestión integral de un gimnasio. Actualmente, el gimnasio administra la información de socios, pagos y asistencia de forma manual o mediante herramientas poco eficientes, lo que genera desorganización, pérdida de información y dificultad para el control del negocio.

El sistema propuesto permitirá centralizar toda la información en una única plataforma, facilitando la gestión de socios, el registro de pagos, el control de asistencia y la administración de turnos y rutinas de entrenamiento.

El sistema será utilizado principalmente por el personal administrativo del gimnasio, como recepcionistas y el dueño, quienes podrán gestionar la información de manera rápida y segura. También podrá ser utilizado por entrenadores para consultar datos de los socios y asignar rutinas.

El objetivo principal es mejorar la organización interna del gimnasio, optimizar los procesos administrativos y brindar un mejor servicio a los socios.

---

## Requisitos funcionales

### Módulo 1 — Gestión de socios

| ID | Requisito |
|----|-----------|
| RF-01 | El sistema debe permitir registrar nuevos socios con sus datos personales. |
| RF-02 | El sistema debe permitir modificar la información de los socios existentes. |
| RF-03 | El sistema debe permitir eliminar o dar de baja socios. |
| RF-04 | El sistema debe permitir consultar la información de cada socio. |

---

### Módulo 2 — Gestión de pagos

| ID | Requisito |
|----|-----------|
| RF-05 | El sistema debe permitir registrar pagos de membresías. |
| RF-06 | El sistema debe permitir consultar el estado de pago de los socios. |
| RF-07 | El sistema debe permitir identificar socios con pagos vencidos. |

---

### Módulo 3 — Asistencia y turnos

| ID | Requisito |
|----|-----------|
| RF-08 | El sistema debe permitir registrar la asistencia de los socios. |
| RF-09 | El sistema debe permitir gestionar turnos para clases o entrenamientos. |
| RF-10 | El sistema debe permitir visualizar disponibilidad de turnos. |

---

### Módulo 4 — Usuarios y administración

| ID | Requisito |
|----|-----------|
| RF-11 | El sistema debe permitir el inicio de sesión de usuarios. |
| RF-12 | El sistema debe permitir gestionar usuarios con distintos roles. |
| RF-13 | El sistema debe permitir la visualización de información general del gimnasio. |

---

### Módulo 5 — Rutinas

| ID | Requisito |
|----|-----------|
| RF-14 | El sistema debe permitir asignar rutinas de entrenamiento a los socios. |
| RF-15 | El sistema debe permitir consultar las rutinas asignadas. |

---

## Requisitos no funcionales

### Rendimiento y disponibilidad

| ID | Requisito |
|----|-----------|
| RNF-01 | El sistema debe responder en menos de 2 segundos en operaciones comunes. |
| RNF-02 | El sistema debe estar disponible durante el horario operativo del gimnasio. |
| RNF-03 | El sistema debe ser capaz de manejar múltiples usuarios simultáneamente. |

---

### Seguridad y usabilidad

| ID | Requisito |
|----|-----------|
| RNF-04 | El sistema debe garantizar la seguridad de los datos mediante autenticación de usuarios. |
| RNF-05 | El sistema debe permitir distintos niveles de acceso según el rol del usuario. |
| RNF-06 | El sistema debe contar con una interfaz intuitiva y fácil de usar. |
| RNF-07 | El sistema debe almacenar la información de forma segura y persistente. |
| RNF-08 | El sistema debe ser accesible desde dispositivos móviles y de escritorio. |
