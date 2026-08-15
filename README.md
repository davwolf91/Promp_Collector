# 🎯 Prompts para Ingeniería de Software

Repositorio de prompts profesionales diseñados para optimizar el trabajo con asistentes de IA (especialmente Claude Code) en tareas de desarrollo, debugging, testing, documentación y arquitectura de software.

---

## 🚀 Inicio Rápido

**📑 [Ver Índice Completo](00_INDICE.md)** - Guía de todos los patrones disponibles

**📋 [Estructura Base](Estructura_Base_Prompts.md)** - Template universal para crear tus propios prompts

---

## 📋 Contenido

Este repositorio contiene dos colecciones principales:

### 🔹 Colección 1: Patrones de Prompts para Claude Code

**[Ver Índice Completo →](00_INDICE.md)**

Siete patrones profesionales organizados por categoría:

#### 🛠️ Desarrollo e Implementación
- **[01 - Implementar Features](01_Implementacion_Features.md)** - Añadir funcionalidad nueva
- **[02 - Refactorizar](02_Refactorizacion.md)** - Mejorar código sin cambiar comportamiento

#### 🐛 Debugging y Testing  
- **[03 - Debugging](03_Debugging.md)** - Depurar con análisis de causa raíz
- **[04 - Testing](04_Testing.md)** - Escribir tests efectivos (happy path, edge cases, errores)

#### 🔍 Análisis y Exploración
- **[05 - Exploración de Proyectos](05_Exploracion_Proyectos.md)** - Entender arquitectura y convenciones
- **[07 - Revisión y Justificación](07_Revision_y_Justificacion.md)** - Evaluar decisiones y alternativas

#### 📚 Documentación
- **[06 - Documentación](06_Documentacion.md)** - Generar docs útiles y actualizadas

#### ⛓️ Metodología Avanzada
- **[08 - Encadenamiento de Patrones](08_Metodologia_Encadenamiento.md)** - Combinar patrones en flujos complejos

---

### 🔹 Colección 2: Prompts Especializados

#### Exploración de Proyectos
**Archivo:** [`Promp_exploraciondeproyectos.txt`](Promp_exploraciondeproyectos.txt)

Dos prompts para analizar y entender bases de código:
- ✅ Análisis de arquitectura y convenciones
- ✅ Trazado de flujos de peticiones  
- ✅ Implementación siguiendo patrones existentes

#### Presentaciones de Arquitectura
**Archivo:** [`Promp_presentaciones.md`](Promp_presentaciones.md)

Prom1️⃣ Encuentra el Patrón que Necesitas
Consulta el **[Índice](00_INDICE.md)** o la **[Guía de Selección Rápida](#-guía-de-selección-rápida)**

### 2️⃣ Usa el Template
Cada patrón incluye:
- 📖 Descripción del problema que resuelve
- 🏗️ Estructura (contexto, tarea, restricciones, formato, verificación)
- ✅ Ejemplo completo listo para copiar
- 💡 Explicación de por qué funciona
- 🎯 Casos de uso recomendados

### 3️⃣ Personaliza y Aplica
1. Copia el ejemplo del patrón
2. Reemplaza los placeholders con tu contexto específico
3. Pégalo en Claude Code o tu asistente de IA
4. Verifica el resultado según el componente de verificación

### 4️⃣ Para Tareas Complejas
Usa el **[Encadenamiento de Patrones](08_Metodologia_Encadenamiento.md)** para combinar múltiples prompts en un flujo verificable.Copia el contenido completo
3. Pégalo en tu asistente de IA preferido (ChatGPT, Claude, Copilot, etc.)
4. Ajusta los parámetros específicos de tu proyecto si es necesario

### Método 2: Referencia Directa
Si usas GitHub Copilot u otra herramienta con acceso al workspace:
```
@workspace usa el prompt de exploración de proyectos
```

## 💡 Mejores Prácticas

### ✅ Principios Fundamentales
1. **Explora antes de implementar** - Entiende el código existente primero
2. **Sé específico** - Más detalle = mejor resultado
3. **Usa restricciones** - Protege lo que ya funciona
4. **Verifica cada paso** - Detecta problemas temprano
5. **Encadena para tareas complejas** - No uses mega-prompts

### 🎯 La Estructura Universal
Todo prompt efectivo tiene hasta 5 componentes:
- **Contexto** - Qué necesita saber
- **Tarea** - Qué tiene que hacer
- **Restricciones** - Qué NO debe hacer  
- **Formato** - Cómo quieres el resultado
- **Verificación** - Cómo confirmar que está bien

Ver más en **[Estructura Base](Estructura_Base_Prompts.md)**

## � Guía de Selección Rápida

| Si necesitas... | Usa el patrón... |
|----------------|------------------|
| Añadir una feature | [01 - Implementación](01_Implementacion_Features.md) |
| Limpiar código | [02 - Refactorización](02_Refactorizacion.md) |
| Arreglar un bug | [03 - Debugging](03_Debugging.md) |
| Escribir tests | [04 - Testing](04_Testing.md) |
| Entender un proyecto | [05 - Exploración](05_Exploracion_Proyectos.md) |
| Crear documentación | [06 - Documentación](06_Documentacion.md) |
| Evaluar una implementación | [07 - Revisión](07_Revision_y_Justificacion.md) |
| T🎓 Flujo de Trabajo Recomendado

Para cualquier tarea significativa, sigue esta secuencia:

```
1. EXPLORAR    → Entiende el código existente
2. IMPLEMENTAR → Añade lo que necesitas  
3. TESTEAR     → Verifica que funciona
4. JUSTIFICAR  → Revisa decisiones
5. DOCUMENTAR  → Registra los cambios
```

Cada paso produce algo verificable antes de continuar al siguiente.

---

## 📚 Recursos

- **[Índice Completo](00_INDICE.md)** - Todos los patrones organizados
- **[Estructura Base](Estructura_Base_Prompts.md)** - Template universal para prompts
- **[Metodología de Encadenamiento](08_Metodologia_Encadenamiento.md)** - Cómo combinar patrones

---

## 📝 Características

- ✅ **Independientes del lenguaje** - Aplican a cualquier stack
- ✅ **Basados en principios** - No en tecnologías específicas  
- ✅ **Verificables** - Cada prompt incluye cómo comprobar el resultado
- ✅ **Modulares** - Combínalos según necesites
- ✅ **Probados** - Patrones extraídos de uso real

---

## 🎯 Casos de Uso Reales

### Para Desarrolladores
- ✅ Onboarding en proyectos nuevos
- ✅ Implementar features manteniendo consistencia
- ✅ Refactorizar sin romper funcionalidad
- ✅ Escribir tests completos y útiles

### Para Tech Leads
- ✅ Auditorías de código estructuradas
- ✅ Documentación de decisiones arquitectónicas
- ✅ Revisión de implementaciones del equipo
- ✅ Capacitaciones y tech talks

### Para Arquitectos
- ✅ Análisis de impacto de cambios
- ✅ Evaluación de alternativas técnicas
- ✅ Presentaciones comparativas
- ✅ ADRs (Architecture Decision Records)

---

## 📄 Licencia

Uso libre para proyectos personales y comerciales.

---

**Última actualización:** Agosto 2026  
**Mantenido por:** David Tayu Panta
