# Equipo Los Aurafarmers — Caso Gimnasio

**Integrantes:**
- Hernández Flores Bryan
- Pedroza Martínez Alessandro
- Cabrera León Brendia Sofía

## Esquema relacional

<!-- Usen la notación de guias/notacion.md. Una tabla por renglón. -->

```
PLAN(**id_plan**, nombre, costo_mensual)
SOCIO(**num_socio**, nombre, fecha_nacimiento, correo UNIQUE, telefono, id_plan -> PLAN, num_locker -> LOCKER)
INSTRUCTOR(**num_empleado**, nombre, especialidad)
LOCKER(**num_locker**, ubicacion)
CLASE(**id_clase**, nombre, cupo_max, num_empleado -> INSTRUCTOR)
SESION(**num_sesion**, fecha, hora_inicio, salon)
PLAN(**id_plan**, nombre, costo_mensual)
INSCRIPCION(**num_socio** -> SOCIO **id_plan** -> PLAN ****)
SUPERVISOR(**num_empleado**, nombre, area_supervision)

```

## Diagrama (opcional)

<!-- Si quieren, dibujen aquí el esquema en Mermaid. -->
