# Equipo Los Aurafarmers — Caso Gimnasio

**Integrantes:**
- Hernández Flores Bryan
- Pedroza Martínez Alessandro
- Cabrera León Brendia Sofía

## Esquema relacional

<!-- Usen la notación de guias/notacion.md. Una tabla por renglón. -->

```
PLAN(**id_plan**, nombre, costo_mensual)
SOCIO(**num_socio**, nombre, fecha_nacimiento, correo UNIQUE, telefono, id_plan -> PLAN)
TELEFONO_SOCIO(num_socio -> SOCIO, telefono)
INSTRUCTOR(**num_empleado**, nombre, especialidad, id_supervisor -> INSTRUCTOR)
LOCKER(**num_locker**, ubicacion, num_socio -> SOCIO)
CLASE(**id_clase**, nombre, cupo_max, num_empleado -> INSTRUCTOR)
SESION(**num_sesion**, fecha, hora_inicio, salon, id_clase -> CLASE)
PLAN(**id_plan**, nombre, costo_mensual)
INSCRIPCION_CLASE(**num_socio** -> SOCIO **id_clase** -> CLASE, fecha_inscripcion, estatus)
SUPERVISOR(**id_supervisor**, nombre, area_supervision, **id_coordinador** -> COORDINADOR)
COORDINADOR(id_coordinador, nombre, area_coordinacion)
```

## Diagrama (opcional)

<!-- Si quieren, dibujen aquí el esquema en Mermaid. -->
PLAN ||--o{ SOCIO : "asignado a"
    SOCIO ||--o| LOCKER : "tiene asignado"
    LOCKER ||--o| SOCIO : "pertenece a"
    CLASE ||--o{ SOCIO : "inscrito en"
    INSTRUCTOR ||--o{ CLASE : "imparte"
    SOCIO ||--o{ CLASE : "asiste a"
    SUPERVISOR ||--o{ INSTRUCTOR : "supervisa"
    SOCIO ||--o{ INSCRIPCION : "realiza"
    PLAN ||--o{ INSCRIPCION : "incluye"
