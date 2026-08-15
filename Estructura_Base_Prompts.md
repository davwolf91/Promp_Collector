# 📋 Estructura Base para Prompts Profesionales

> Template universal para crear prompts efectivos con Claude Code

---

## Los 5 Componentes

Todo prompt profesional se compone de **hasta cinco piezas**. No todos los prompts necesitan las cinco, pero cuando el resultado no es el esperado, casi siempre falta una de estas.

---

## 1️⃣ Contexto

**Qué necesita saber Claude de la situación**

### Incluye:
- ✅ Qué tipo de proyecto es
- ✅ Qué stack/tecnologías usa
- ✅ Qué existe ya (estado actual)
- ✅ Qué ha pasado antes (si es relevante)

### Ejemplo:
```
Contexto: Snap es un acortador de URLs. Express + TypeScript + SQLite.
Ya tiene endpoints de creación y redirect de URLs funcionando.
```

---

## 2️⃣ Tarea

**Qué tiene que hacer exactamente**

### Características:
- ✅ Clara y específica
- ✅ Con requisitos enumerados
- ✅ Accionable y medible
- ✅ Sin ambigüedades

### Ejemplo:
```
Tarea: Implementa tracking de clicks. Cada vez que alguien visita
un código corto y es redirigido, registra el click con timestamp,
IP y user-agent. Añade un endpoint para consultar el total de
clicks y un desglose por día de los últimos 7 días.
```

---

## 3️⃣ Restricciones

**Qué NO debe hacer o qué límites tiene**

### Tipos de restricciones:
- 🚫 Qué no cambiar
- 📐 Patrones del proyecto a respetar
- 📦 Dependencias que no instalar
- ⚡ Requisitos de performance
- 🏗️ Arquitectura a mantener

### Ejemplo:
```
Restricciones:
- El redirect no debe volverse más lento. Registra el click
  después de enviar la respuesta al usuario.
- Sigue la misma estructura de módulos que ya tiene el proyecto.
- No cambies la interfaz de los endpoints existentes.
```

---

## 4️⃣ Formato

**Cómo quieres el resultado**

### Especifica:
- 📄 Tipo de archivo (Markdown, JSON, código, etc.)
- 📊 Estructura deseada (lista, tabla, diagrama, etc.)
- 🎯 Nivel de detalle
- 📝 Incluir o no ejemplos
- 🔢 Orden de presentación

### Ejemplo:
```
Formato: Antes de tocar código:
1. Muéstrame qué cambiarías y por qué
2. Lista los archivos afectados
3. Identifica riesgos
```

---

## 5️⃣ Verificación

**Cómo confirmar que está bien**

### Tipos de verificación:
- ✅ Tests que deben pasar
- ✅ Comandos para ejecutar
- ✅ Métricas a alcanzar (cobertura, performance, etc.)
- ✅ Checklist de completitud
- ✅ Comparación con estado esperado

### Ejemplo:
```
Verificación: Escribe tests que cubran el registro de clicks
y la consulta de estadísticas. Ejecuta todos los tests del
proyecto al terminar.
```

---

## 📝 Template Completo

```markdown
Contexto: [Qué proyecto es, qué stack usa, qué existe ya]

Tarea: [Qué tiene que hacer exactamente]
- [requisito concreto 1]
- [requisito concreto 2]
- [requisito concreto 3]

Restricciones:
- [qué no cambiar]
- [patrones del proyecto a respetar]
- [límites o requisitos]

Formato: [Cómo quieres el resultado]
[estructura específica si es necesario]

Verificación: [Cómo confirmar que está bien]
[tests, comandos, o métricas]
```

---

## ⚖️ Cuándo Usar Cada Componente

| Componente | Siempre | Casi siempre | Opcional |
|------------|---------|--------------|----------|
| **Tarea** | ✅ | | |
| **Contexto** | | ✅ | |
| **Verificación** | | ✅ | |
| **Restricciones** | | | ✅* |
| **Formato** | | | ✅* |

\* Pero muy recomendables cuando el resultado necesita estructura específica o proteger código existente

---

## 🎯 Ejemplos por Complejidad

### Nivel 1: Fix Rápido
Solo necesita **Tarea + Verificación**

```
Tarea: Cambia el timeout del servidor de 30s a 60s.

Verificación: Reinicia el servidor y confirma el nuevo timeout en logs.
```

### Nivel 2: Feature Simple
Necesita **Contexto + Tarea + Verificación**

```
Contexto: API de tareas con Express. Ya existe GET y POST /tasks.

Tarea: Añade endpoint DELETE /tasks/:id que elimine una tarea.

Verificación: Crea un test que verifique la eliminación exitosa
y que devuelva 404 para IDs inexistentes.
```

### Nivel 3: Feature Compleja
Usa los **5 componentes**

```
Contexto: E-commerce con módulo de productos funcionando.

Tarea: Implementa sistema de descuentos:
- Descuentos por porcentaje o monto fijo
- Aplicables a productos o categorías
- Con fecha de inicio y fin

Restricciones:
- No cambies la estructura de productos existente
- El precio original debe mantenerse visible
- Sigue el patrón de servicios del proyecto

Formato: Antes de implementar, muéstrame:
1. Qué tablas de BD necesitas
2. Qué endpoints crearás
3. Cómo afecta al cálculo de precio actual

Verificación: Tests para aplicación, expiración, y acumulación
de descuentos. Cobertura > 80%.
```

---

## ❌ Errores Comunes

### 1. Tarea Vaga
```
❌ "Mejora el rendimiento"
✅ "Reduce el tiempo de respuesta del endpoint /search de 2s a < 500ms
    usando índices de base de datos"
```

### 2. Sin Contexto
```
❌ "Implementa autenticación"
✅ "Contexto: API REST sin auth. Stack: Node + Express.
    Tarea: Implementa JWT con refresh tokens..."
```

### 3. Sin Restricciones en Refactor
```
❌ "Refactoriza el módulo de pagos"
✅ "Refactoriza el módulo de pagos para usar async/await.
    Restricción: Los tests existentes deben pasar sin modificarlos."
```

### 4. Sin Verificación
```
❌ "Crea tests para el módulo de usuarios"
✅ "Crea tests para el módulo de usuarios.
    Verificación: Ejecuta con coverage y muestra el porcentaje alcanzado."
```

---

## 💡 Tips para Prompts Efectivos

### 1. Sé Específico
Más detalle = mejor resultado. Claude no adivina.

### 2. Un Prompt, Una Tarea
Si mezclas múltiples tareas, sepáralas en prompts encadenados.

### 3. Pide el Plan Primero
Para tareas complejas: "Antes de implementar, muéstrame el plan"

### 4. Usa Ejemplos Concretos
No digas "maneja errores", di "devuelve 404 si el ID no existe"

### 5. Haz Verificable Todo
Si no puedes verificar el resultado, el prompt es demasiado vago.

---

## 🔗 Próximos Pasos

Una vez domines la estructura:
1. Revisa los **[patrones específicos](00_INDICE.md)** para casos comunes
2. Aprende a **[encadenar patrones](08_Metodologia_Encadenamiento.md)** para tareas complejas
3. Practica hasta que incluyas estos componentes naturalmente

---

## 📚 Referencia Rápida

**Pregúntate:**
- ¿Qué necesita saber? → **Contexto**
- ¿Qué tiene que hacer? → **Tarea**
- ¿Qué NO debe hacer? → **Restricciones**
- ¿Cómo lo quiero? → **Formato**
- ¿Cómo lo compruebo? → **Verificación**

Si alguna respuesta es importante para el resultado, inclúyela en el prompt.

---

**💡 Recuerda:** No todos los prompts necesitan los cinco componentes, pero cuando algo falla, casi siempre es porque falta uno.
