# 🧪 Patrón: Escribir Tests

## Descripción
Los tests no son algo que "se añade al final". Este patrón produce tests útiles en vez de tests superficiales que solo verifican que "la función no lanza error".

---

## Estructura del Patrón

### Contexto
`[Qué módulo/servicio quieres testear y qué hace]`

### Tarea
```
Genera tests para [archivo]. Para cada función pública:
- Un test del caso normal (happy path)
- Un test de caso edge [ejemplos relevantes]
- Un test de error [ejemplos relevantes]
```

### Restricciones
```
- [framework de testing a usar]
- [patrones de test del proyecto]
```

### Verificación
```
Ejecuta los tests. Después ejecuta con cobertura
y muéstrame qué porcentaje tiene el archivo.
```

---

## Ejemplo Completo

**Contexto:** El servicio de autenticación de Snap tiene funciones
para register y login. Usa bcrypt para passwords y JWT para tokens.

**Tarea:** Genera tests para src/auth/auth.service.ts. Para cada función:
- **Happy path:** registro exitoso devuelve usuario y token,
  login exitoso devuelve token válido
- **Edge cases:** email con mayúsculas mezcladas, password en el
  límite mínimo de longitud, email con espacios alrededor
- **Errores:** email duplicado, password incorrecto, email
  inexistente, campos vacíos

**Restricciones:**
- Usa Vitest con describe/it
- Cada test debe ser independiente (no depender del orden)

**Verificación:** Ejecuta los tests. Después ejecuta `vitest --coverage`
y muéstrame la cobertura de auth.service.ts.

---

## Por qué funciona

Especificar las tres categorías (happy path, edge, error) con ejemplos concretos produce tests que realmente encuentran bugs. Sin esos ejemplos, Claude tiende a generar tests genéricos que verifican lo obvio. La verificación con cobertura cierra el ciclo y te dice si quedaron ramas sin cubrir.

---

## Categorías de Tests

### 1. Happy Path
✅ El caso ideal donde todo funciona correctamente

### 2. Edge Cases
✅ Límites y casos especiales:
- Valores mínimos/máximos
- Strings vacíos
- Colecciones vacías
- Formatos inusuales pero válidos

### 3. Error Cases
✅ Situaciones de error:
- Validaciones fallidas
- Recursos no encontrados
- Permisos denegados
- Timeouts

---

## Casos de uso
- ✅ Cubrir código existente sin tests
- ✅ Tests antes de refactorizar (safety net)
- ✅ TDD (escribir tests primero)
- ✅ Regression testing después de bugs
- ✅ Aumentar cobertura de código

---

## 📊 Métricas de Calidad

Un buen conjunto de tests debe:
- ✅ Tener > 80% de cobertura
- ✅ Ser independientes entre sí
- ✅ Ejecutarse rápido (< 100ms por test unitario)
- ✅ Tener nombres descriptivos
- ✅ Fallar por razones claras
