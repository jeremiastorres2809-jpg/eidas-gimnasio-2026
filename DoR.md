# Definition of Ready (DoR)

_Antes de que una historia entre a desarrollo, tiene que pasar un filtro: el Definition of
Ready. Es un acuerdo del equipo sobre qué condiciones mínimas debe cumplir una historia para
considerarse "lista para trabajar". Si no las cumple, vuelve a refinamiento._

---

## Checklist del equipo

_Entre 6 y 10 ítems. Cada uno redactado como una condición verificable ("la historia tiene
criterios de aceptación escritos"), no como un deseo ("la historia está bien definida")._

| # | Ítem | Justificación (qué problema evita, máx. 3 renglones) |
|---|------|--------------------------------------------------------|
| 1 |El actor/rol de la historia está claramente identificado y sin ambigüedades. |Evita desarrollar funcionalidades para el perfil equivocado o asumir permisos de usuario incorrectos.|
| 2 |La historia cuenta con criterios de aceptación explícitos y verificables. |Evita interpretaciones libres sobre qué se considera "terminado" y frena entregas incompletas. |
| 3 |Se especifican los flujos alternativos y el manejo de excepciones o errores. |Evita cuelgues del sistema o pantallas en blanco cuando el usuario realiza acciones no previstas. |
| 4 |Se declaran explícitamente las dependencias con otras Historias o Casos de Uso. |Evita arrancar a programar una función cuya base de datos o módulo previo aún no fue construido. |
| 5 |Tiene vinculado al menos un Requisito No Funcional (RNF) especifico y medible. |Evita problemas de rendimiento, interfaces no adaptadas a celulares o fallos de seguridad. |
| 6 |El equipo puede estimar el esfuerzo sin preguntas abiertas de alcance. |Evita bloqueos a mitad del desarrollo por no saber exactamente qué elementos componen la pantalla. |

---

## Aplicación a tres historias propias

_Elijan TRES historias de usuario de su propio trabajo del primer semestre y pásenlas por su
propia checklist. Es esperable —y deseable— que alguna no pase._

### Historia 1 — [Ver mi rutina (HU-01)]

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1 |SI|Se identifica claramente al "Cliente" como usuario. |
| 2 |NO|Le falta definir las condiciones de aceptación y reglas de negocio.|
| 3 |NO|Le falta indicar el mensaje cuando el cliente aún no tiene rutina cargada.|
| 4 |NO|Le falta vincular la asignación previa realizada por el entrenador (CU-002).|
| 5 |NO|Le falta un requisito no funcional medible (como tiempo de respuesta o vista móvil). |
| 6 |NO|Le falta detallar la interacción (si incluye series, repeticiones o tildar ejercicios). |

---

### Historia 2 — Asignar rutinas (HU-02)

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1 |SI |Identifica correctamente al "Entrenador" como responsable de la acción.|
| 2 |NO |Le falta listar las condiciones necesarias para validar la asignación.|
| 3 |NO |Le falta definir la alerta si el alumno buscado no existe o está inactivo|
| 4 |NO |Le falta vincular el registro previo de usuarios (CU-001) y las tablas del DER.|
| 5 |NO |Le falta especificar el tiempo de respuesta al guardar (RNF-01) o la adaptabilidad de la pantalla en tablets/celulares (RNF-08).|
| 6 |NO |Le falta aclarar si la rutina se debe armar desde cero seleccionando ejercicios o si se van a reutilizar plantillas prediseñadas. |

---

### Historia 3 — Registrar nuevos socios (HU-03)

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1 |SI|El rol "Administrativo" está claro en la descripción del proyecto |
| 2 |NO|Es solo un título sin criterios de validación ni negocio. |
| 3 |NO|Omite el manejo de DNI/Email duplicado o campos incompletos. |
| 4 |NO|No indica la relación con la base de datos de usuarios de su DER |
| 5 |NO|No se especifica ningún RNF de seguridad ni de validación de contraseña. |
| 6 |NO|Un programador no sabe qué campos son obligatorios u opcionales. |
