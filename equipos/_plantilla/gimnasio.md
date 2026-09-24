# Equipo Los Aurafarmers — Caso Gimnasio

**Integrantes:**
- Hernández Flores Bryan
- Pedroza Martínez Alessandro
- Cabrera León Brendia Sofía

## Esquema relacional

<!-- Usen la notación de guias/notacion.md. Una tabla por renglón. -->

```
PLAN(**id_plan**, nombre, costo_mensual)
SOCIO(**num_socio**, nombre, fecha_nacimiento, correo UNIQUE, telefono, id_plan -> PLAN, num_locker -> LOCKER, id_clase -> CLASE)
INSTRUCTOR(**num_empleado**, nombre, especialidad, id_supervisor -> SUPERVISOR, id_clase -> CLASE)
LOCKER(**num_locker**, ubicacion, num_socio -> SOCIO)
CLASE(**id_clase**, nombre, cupo_max, num_empleado -> INSTRUCTOR num_socio -> SOCIO)
SESION(**num_sesion**, fecha, hora_inicio, salon)
PLAN(**id_plan**, nombre, costo_mensual)
INSCRIPCION(**num_socio** -> SOCIO **id_plan** -> PLAN ****)
SUPERVISOR(**id_supervisor**, nombre, area_supervision)
COORDINADOR(id_coordinador, nombre, area_coordinacion)
```

## Diagrama (opcional)

<!-- Si quieren, dibujen aquí el esquema en Mermaid. -->
