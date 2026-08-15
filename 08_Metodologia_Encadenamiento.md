# ⛓️ Metodología: Encadenamiento de Patrones

## Descripción
Los patrones no se usan aislados. Una tarea compleja es una secuencia donde cada prompt usa un patrón distinto y cada paso produce algo verificable.

---

## La Cadena Básica

```
Explorar    → "Analiza cómo funciona el módulo X"
             ↓
Implementar → "Siguiendo ese patrón, añade Y"
             ↓
Tests       → "Genera tests para lo que acabas de implementar"
             ↓
Justificar  → "¿Qué alternativas consideraste?"
             ↓
Documentar  → "Actualiza la documentación con los cambios"
```

---

## Regla de Oro

**Cada prompt de la cadena produce algo que puedes verificar antes de lanzar el siguiente.**

Si no puedes comprobar el resultado, el paso es demasiado grande o le falta el componente de verificación.

---

## Ejemplos de Cadenas

### 🔹 Cadena 1: Feature Completa

1. **Explorar**
   ```
   Analiza cómo está implementado el módulo de autenticación.
   ¿Qué patrón sigue? ¿Qué middlewares usa?
   ```
   ✅ Verificación: Lees el análisis y confirmas que es correcto

2. **Implementar**
   ```
   Siguiendo exactamente el mismo patrón, implementa un sistema
   de roles (admin, user, guest) con middleware de autorización.
   ```
   ✅ Verificación: Compilación exitosa, endpoints responden

3. **Tests**
   ```
   Genera tests para el sistema de roles: casos de acceso permitido,
   denegado, y casos edge como usuarios sin rol.
   ```
   ✅ Verificación: Tests pasan con > 80% cobertura

4. **Justificar**
   ```
   Sobre la implementación de roles:
   ¿Por qué usaste middleware vs decorators?
   ¿Qué pasa si un usuario tiene múltiples roles?
   ```
   ✅ Verificación: Las respuestas tienen sentido o revelan problemas

5. **Documentar**
   ```
   Actualiza docs/API.md con los nuevos endpoints protegidos
   y cómo usar el sistema de roles.
   ```
   ✅ Verificación: La doc cubre todos los endpoints nuevos

---

### 🔹 Cadena 2: Bug Fix Crítico

1. **Explorar contexto**
   ```
   Analiza el flujo completo del proceso de checkout en
   src/checkout/. Muestra qué archivos intervienen y en qué orden.
   ```
   ✅ Verificación: El diagrama de flujo es correcto

2. **Debug**
   ```
   Tengo este error al hacer checkout:
   [stack trace]
   Identifica la causa raíz antes de arreglar.
   ```
   ✅ Verificación: La explicación de la causa tiene sentido

3. **Implementar fix**
   ```
   Corrige el bug que identificaste. Asegúrate de que el fix
   maneja también el caso edge de [X].
   ```
   ✅ Verificación: El bug ya no ocurre

4. **Tests de regresión**
   ```
   Crea un test que reproduzca el bug original y verifique
   que ahora está corregido.
   ```
   ✅ Verificación: El test falla antes del fix, pasa después

5. **Justificar**
   ```
   ¿Podría este fix afectar otras partes del checkout?
   ¿Hay otros lugares con el mismo patrón que también estén rotos?
   ```
   ✅ Verificación: Revisas los lugares mencionados

---

### 🔹 Cadena 3: Refactor Seguro

1. **Explorar estado actual**
   ```
   Analiza src/services/. ¿Qué código está duplicado?
   ¿Qué patrones se repiten?
   ```
   ✅ Verificación: Confirmas la duplicación identificada

2. **Planear refactor**
   ```
   Propón un plan para extraer la lógica duplicada de validación
   a un módulo compartido. No implementes, solo planea.
   ```
   ✅ Verificación: El plan tiene sentido, no rompe dependencias

3. **Implementar paso 1**
   ```
   Crea el módulo de validación compartido sin cambiar los
   servicios todavía.
   ```
   ✅ Verificación: Compila, tests existentes siguen pasando

4. **Implementar paso 2**
   ```
   Migra el servicio de usuarios al nuevo módulo de validación.
   ```
   ✅ Verificación: Tests del servicio pasan sin cambios

5. **Implementar paso 3**
   ```
   Migra los servicios restantes uno por uno.
   ```
   ✅ Verificación: Todos los tests pasan después de cada migración

6. **Justificar**
   ```
   ¿Qué ventajas obtenemos con este refactor?
   ¿Hay desventajas?
   ```
   ✅ Verificación: Los beneficios justifican el esfuerzo

---

## Principios del Encadenamiento

### 1. Incrementalidad
Cada paso debe ser pequeño y verificable. No saltes de "explorar" a "todo implementado".

### 2. Verificación constante
Después de cada paso, verifica antes de continuar. Si algo está mal, no avances.

### 3. Contexto acumulativo
Cada prompt puede referenciar los resultados anteriores:
```
"Siguiendo el patrón que identificaste en el paso 1..."
"Basándote en los tests que acabas de crear..."
```

### 4. Puntos de control
En cadenas largas, define puntos donde puedes "guardar progreso":
- Después de implementar algo
- Después de que los tests pasen
- Antes de cambios estructurales grandes

### 5. Reversibilidad
Cada paso debe ser reversible. Si algo sale mal:
- Git reset al punto anterior
- Continúa desde el último paso verificado

---

## ⚠️ Errores Comunes

### ❌ Saltar la exploración
```
❌ "Implementa autenticación con JWT"
✅ "Primero analiza cómo está estructurado el proyecto,
    luego implementa JWT siguiendo esos patrones"
```

### ❌ Pasos demasiado grandes
```
❌ "Implementa todo el módulo de pagos"
✅ "Implementa solo el endpoint de crear pago"
    "Ahora agrega validación"
    "Ahora agrega logs"
```

### ❌ No verificar entre pasos
```
❌ Implementar → Tests → Documentar (todo de golpe)
✅ Implementar → [verificas que compila]
    Tests → [verificas que pasan]
    Documentar → [verificas que cubre todo]
```

---

## 💡 Tips Avanzados

### Paralelización
Algunos pasos pueden ir en paralelo si son independientes:
```
Después de implementar:
- Rama A: Escribe tests
- Rama B: Actualiza documentación
[Ambos pueden hacerse independientemente]
```

### Checkpoints explícitos
```
"Antes de continuar, confirma:
1. Todos los tests pasan ✅
2. No hay errores de compilación ✅
3. El código sigue las convenciones del proyecto ✅"
```

### Ciclos de mejora
```
Implementar → Justificar → [identificas problema]
          ↓
Refactorizar → Justificar → [ahora está mejor]
```

---

## Conclusión

Con el tiempo, estos patrones dejan de ser plantillas que consultas y se convierten en una forma de pensar. No te preguntas "¿qué patrón uso?", sino que naturalmente incluyes contexto, restricciones y verificación en cada instrucción.

**Eso es lo que separa un uso casual de Claude Code de un uso profesional.**
