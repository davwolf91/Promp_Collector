# ♻️ Patrón: Refactorizar

## Descripción
Refactorizar es el patrón donde más fácil es que Claude se desborde. Sin restricciones claras, "refactoriza este módulo" puede convertirse en una reescritura completa que rompe media aplicación. La clave es definir qué no debe cambiar.

---

## Estructura del Patrón

### Contexto
`[Qué módulo y por qué quieres refactorizarlo]`

### Tarea
`Refactoriza [archivo/módulo] para [objetivo concreto].`

### Restricciones
```
- La API pública NO debe cambiar
- Los tests existentes deben seguir pasando sin modificarlos
- Sigue el patrón [patrón del proyecto]
```

### Formato
```
Antes de tocar código:
1. Muéstrame qué cambiarías y por qué
2. Lista los archivos afectados
3. Identifica riesgos
```

### Verificación
```
Ejecuta todos los tests sin cambiarlos.
Si alguno falla, el refactoring rompió algo.
```

---

## Ejemplo Completo

**Contexto:** En Snap hay lógica de validación dispersa por varios
servicios: validación de URLs en el servicio de URLs, validación
de emails en el servicio de auth, validación de alias en otro
archivo. Quiero centralizarla.

**Tarea:** Extrae toda la validación a un módulo dedicado que los
demás servicios importen.

**Restricciones:**
- Los endpoints deben devolver exactamente los mismos errores
  que antes. Ningún cliente debería notar el cambio.
- Los tests actuales deben pasar tal cual, sin tocarlos.
- El módulo de validación debe seguir la misma convención de
  naming y exports que los módulos existentes.

**Formato:** Antes de implementar, muéstrame:
1. Qué cambiarías y por qué
2. Lista los archivos afectados
3. Identifica riesgos

**Verificación:** Ejecuta todos los tests del proyecto. Si pasan
sin cambios, el refactoring es correcto.

---

## Por qué funciona

La restricción "los tests existentes pasan sin cambiarlos" es la red de seguridad más potente que puedes darle a Claude. Convierte un cambio potencialmente destructivo en algo verificable objetivamente. Y pedir el plan antes de la implementación te da un punto de control donde puedes detener un refactoring mal planteado antes de que toque un solo archivo.

---

## Casos de uso
- ✅ Extraer lógica duplicada
- ✅ Mejorar la legibilidad del código
- ✅ Aplicar patrones de diseño
- ✅ Centralizar funcionalidades dispersas
- ✅ Simplificar complejidad ciclomática

---

## ⚠️ Regla de Oro
**La API pública NO debe cambiar.** Los tests existentes deben pasar sin modificaciones.
