# 🛠️ Patrón: Implementar una Feature

## Descripción
El patrón más frecuente. Añadir funcionalidad nueva a un proyecto existente.

---

## Estructura del Patrón

### Contexto
`[Qué proyecto es, qué stack usa, qué existe ya]`

### Tarea
```
Implementa [feature] con estos requisitos:
- [requisito concreto 1]
- [requisito concreto 2]
- [requisito concreto 3]
```

### Restricciones
```
- [qué no cambiar]
- [patrones del proyecto a respetar]
- [dependencias que no instalar]
```

### Verificación
`[tests a crear y ejecutar, o comando para comprobar]`

---

## Ejemplo Completo

**Contexto:** Snap es un acortador de URLs. Express + TypeScript + SQLite.
Ya tiene endpoints de creación y redirect de URLs funcionando.

**Tarea:** Implementa tracking de clicks. Cada vez que alguien visita
un código corto y es redirigido, registra el click con timestamp,
IP y user-agent. Añade un endpoint para que el dueño de una URL
pueda consultar el total de clicks y un desglose por día de los
últimos 7 días.

**Restricciones:**
- El redirect no debe volverse más lento. Registra el click
  después de enviar la respuesta al usuario.
- Sigue la misma estructura de módulos que ya tiene el proyecto.
- No cambies la interfaz de los endpoints existentes.

**Verificación:** Escribe tests que cubran el registro de clicks
y la consulta de estadísticas. Ejecuta todos los tests del
proyecto al terminar.

---

## Por qué funciona

El contexto evita que Claude invente una estructura propia. Los requisitos son concretos y contables (puedes verificar cada uno). Las restricciones protegen lo que ya funciona. Y la verificación cierra el ciclo: si los tests no pasan, Claude lo sabe antes que tú.

---

## Casos de uso
- ✅ Agregar nuevos endpoints a una API
- ✅ Implementar funcionalidades completas
- ✅ Extender sistemas existentes
- ✅ Añadir integraciones con servicios externos
