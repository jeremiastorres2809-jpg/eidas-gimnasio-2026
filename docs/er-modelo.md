# Modelo Entidad-Relación

## Diagrama

_Incluir el código PlantUML en `diagramas/er.puml`._
_Visualizar en [plantuml.com](https://www.plantuml.com/plantuml/uml/)._

## Entidades

| Entidad | Descripción | Relaciones clave |
|---------|-------------|-----------------|
| USUARIO | Datos personales comunes a todas las personas del sistema | Se especializa en SOCIO o ENTRENADOR (1 a 0..1) |
| SOCIO | Persona que asiste al gimnasio | Realiza muchos PAGO, tiene muchas RUTINA, registra muchas ASISTENCIA |
| ENTRENADOR | Personal que arma rutinas y dicta clases | Asigna muchas RUTINA, dicta muchas CLASE |
| PAGO | Pago de la membresía de un socio | Pertenece a un SOCIO |
| RUTINA | Plan de entrenamiento asignado a un socio | Pertenece a un SOCIO y a un ENTRENADOR, contiene muchos EJERCICIO |
| EJERCICIO | Ejercicio con series y repeticiones dentro de una rutina | Pertenece a una RUTINA |
| CLASE | Clase con horario y duración | Dictada por un ENTRENADOR, puede recibir ASISTENCIA |
| ASISTENCIA | Registro de ingreso de un socio (con fecha y hora) | Pertenece a un SOCIO y a una CLASE |

## Descripción de atributos principales

### USUARIO

- `id_usuario` (PK): identifica a cada persona registrada.
- `tipo_usuario`: indica si es socio o entrenador y define su acceso.
- `email`, `telefono`: datos de contacto.

### SOCIO

- `id_usuario` (PK, FK): es a la vez clave primaria y referencia a USUARIO.
- `estado_fisico`, `objetivo`: información que usa el entrenador para armar la rutina.

### PAGO

- `id_pago` (PK): identifica cada pago.
- `monto`, `fecha`: importe abonado y día en que se registró.
- `id_socio` (FK): socio que realizó el pago.

### RUTINA

- `id_rutina` (PK): identifica la rutina.
- `id_socio` (FK): socio que la recibe.
- `id_entrenador` (FK): entrenador que la asignó.
- `fecha_asignacion`: permite saber cuál es la rutina vigente.

### ASISTENCIA

- `id_asistencia` (PK): identifica cada registro.
- `fecha_hora`: momento del ingreso.
- `id_socio` (FK): socio que asistió.
- `id_clase` (FK): solo se completa si asistió a una clase puntual.

## Decisiones de diseño

### Decisión 1 — Separar pagos de socios
Se separa para poder registrar varios pagos por cada socio. Se descartó guardar un campo "último pago" dentro de SOCIO porque se perdería el historial.

### Decisión 2 — Rutinas independientes
Permite modificar o cambiar rutinas sin afectar otros datos. Cada rutina guarda su fecha de asignación, así se conserva el historial de rutinas de un socio.

### Decisión 3 — Generalización USUARIO → SOCIO / ENTRENADOR
Los datos comunes (nombre, email, teléfono) se guardan una sola vez en USUARIO. Se descartó repetirlos en cada tabla porque duplicaría información.
