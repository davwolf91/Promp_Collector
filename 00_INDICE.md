# 📑 Índice de Patrones de Prompts para Claude Code

> Colección organizada de patrones profesionales para trabajar con Claude Code

---

## 🎯 Patrones por Categoría

### 🛠️ Desarrollo e Implementación
- **[01_Implementacion_Features.md](01_Implementacion_Features.md)**
  - Añadir funcionalidad nueva a proyectos existentes
  - Casos: endpoints, integraciones, features completas
  
- **[02_Refactorizacion.md](02_Refactorizacion.md)**
  - Mejorar código existente sin cambiar comportamiento
  - Casos: extraer duplicación, aplicar patrones, simplificar

### 🐛 Debugging y Testing
- **[03_Debugging.md](03_Debugging.md)**
  - Depurar problemas con análisis de causa raíz
  - Casos: errores runtime, bugs de lógica, casos edge
  
- **[04_Testing.md](04_Testing.md)**
  - Escribir tests útiles (happy path, edge cases, errores)
  - Casos: cobertura, TDD, regression testing

### 🔍 Análisis y Exploración
- **[05_Exploracion_Proyectos.md](05_Exploracion_Proyectos.md)**
  - Entender arquitectura y convenciones antes de codificar
  - Casos: onboarding, auditorías, planificación
  
- **[07_Revision_y_Justificacion.md](07_Revision_y_Justificacion.md)**
  - Revisar decisiones y explorar alternativas
  - Casos: code review, análisis de trade-offs

### 📚 Documentación
- **[06_Documentacion.md](06_Documentacion.md)**
  - Generar documentación útil y actualizada
  - Casos: APIs, READMEs, guías, arquitectura

### ⛓️ Metodología Avanzada
- **[08_Metodologia_Encadenamiento.md](08_Metodologia_Encadenamiento.md)**
  - Combinar patrones en secuencias verificables
  - Flujos completos: feature → tests → docs

- **[10_Division_Tareas_Complejas.md](10_Division_Tareas_Complejas.md)**
  - Dividir tareas grandes en pasos pequeños verificables
  - Casos: migraciones, integraciones complejas, features multi-capa

### 🎤 Presentaciones y Documentación Técnica
- **[09_Presentaciones_Arquitectura.md](09_Presentaciones_Arquitectura.md)**
  - Crear presentaciones comparativas sobre arquitecturas
  - Casos: tech talks, decisiones de diseño, capacitaciones

### 📘 Ejemplos y Casos de Estudio
- **[Ejemplo_Debugging_Token_Snap.md](Ejemplo_Debugging_Token_Snap.md)**
  - Caso real: debugging de persistencia de tokens JWT
  - Aplicación del patrón de debugging

---

## 🚀 Inicio Rápido

### Para cada patrón encontrarás:

1. **Descripción** - Qué problema resuelve
2. **Estructura** - Los 5 componentes (contexto, tarea, restricciones, formato, verificación)
3. **Ejemplo completo** - Prompt real listo para usar
4. **Por qué funciona** - La lógica detrás del patrón
5. **Casos de uso** - Cuándo aplicarlo

---

## 📊 Guía de Selección Rápida

| Si necesitas... | Usa el patrón... |
|----------------|------------------|
| Añadir una feature | [01_Implementacion_Features](01_Implementacion_Features.md) |
| Limpiar código existente | [02_Refactorizacion](02_Refactorizacion.md) |
| Arreglar un bug | [03_Debugging](03_Debugging.md) |
| Escribir tests | [04_Testing](04_Testing.md) |
| Entender un proyecto | [05_Exploracion_Proyectos](05_Exploracion_Proyectos.md) |
| Crear documentación | [06_Documentacion](06_Documentacion.md) |
| Evaluar implementación | [07_Revision_y_Justificacion](07_Revision_y_Justificacion.md) |
| Tarea compleja multi-paso | [08_Metodologia_Encadenamiento](08_Metodologia_Encadenamiento.md) |
| Crear presentación técnica | [09_Presentaciones_Arquitectura](09_Presentaciones_Arquitectura.md) |
| Dividir tarea grande | [10_Division_Tareas_Complejas](10_Division_Tareas_Complejas.md) |

---

## 🏗️ La Estructura Universal

Todos los patrones se basan en 5 componentes:

```
Contexto: Qué necesita saber Claude de la situación
         ↓
Tarea: Qué tiene que hacer exactamente
         ↓
Restricciones: Qué no debe hacer o qué límites tiene
         ↓
Formato: Cómo quieres el resultado
         ↓
Verificación: Cómo confirmar que está bien
```

No todos los prompts necesitan los cinco, pero cuando falla, casi siempre falta una pieza.

---

## 💡 Principios Clave

### 1. Especificidad
❌ "Implementa autenticación"  
✅ "Implementa JWT con refresh tokens, siguiendo el patrón de módulos del proyecto"

### 2. Verificabilidad
Cada prompt debe producir algo que puedas comprobar objetivamente.

### 3. Restricciones claras
Define qué NO debe cambiar para proteger lo que funciona.

### 4. Contexto relevante
Da a Claude la información que necesita para tomar buenas decisiones.

### 5. Incrementalidad
Para tareas complejas, encadena patrones simples en vez de un mega-prompt.

---

## 📚 Recursos Adicionales

- **[Estructura_Base_Prompts.md](Estructura_Base_Prompts.md)** - Template genérico para crear tus propios prompts
- **[Promp_exploraciondeproyectos.txt](Promp_exploraciondeproyectos.txt)** - Prompts originales de exploración
- **[Promp_presentaciones.md](Promp_presentaciones.md)** - Prompt para presentaciones técnicas

---

## 🎓 Flujo de Trabajo Recomendado

Para cualquier tarea significativa:

```
1. EXPLORAR    → Entiende el código existente
2. IMPLEMENTAR → Añade lo que necesitas
3. TESTEAR     → Verifica que funciona
4. JUSTIFICAR  → Revisa decisiones
5. DOCUMENTAR  → Registra los cambios
```

---

## ⚡ Tips Pro

1. **Siempre explora antes de implementar** - Te ahorra refactors
2. **Pide el plan antes del código** - Te da control
3. **Verifica después de cada paso** - Detecta problemas temprano
4. **Usa restricciones para proteger código** - Previene roturas
5. **Los tests son tu red de seguridad** - Especialmente en refactors

---

**Última actualización:** Agosto 2026  
**Fuente:** Patrones de prompt para Claude Code  
**Organizado por:** David Tayu Panta
