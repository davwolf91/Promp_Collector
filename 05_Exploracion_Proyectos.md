# 🔍 Patrón: Explorar un Proyecto

## Descripción
Este patrón no produce código. Produce comprensión. Es el primer paso antes de cualquier cambio significativo, y es el que más gente se salta.

---

## Estructura del Patrón

### Tarea
```
Analiza [proyecto/módulo/archivo] y responde:
- [pregunta sobre estructura]
- [pregunta sobre patrones]
- [pregunta sobre dependencias]
- [pregunta sobre convenciones]
```

### Formato
`[Si quieres un diagrama, una lista, una explicación narrativa, etc.]`

### Restricciones
`No modifiques nada. Solo lectura.`

---

## Ejemplo Completo

**Tarea:** Analiza el proyecto Snap tal como está y responde:
1. ¿Qué patrón sigue para separar rutas de lógica de negocio?
2. ¿Cómo se inicializa y se accede a la base de datos?
3. ¿Qué convenciones de naming usan los archivos y funciones?
4. Si quiero añadir un módulo nuevo (ej: "notifications"),
   ¿qué archivos necesitaría crear para seguir el mismo patrón?

**Formato:** Dame un resumen breve por pregunta y un diagrama ASCII
de la estructura de carpetas relevante.

**Restricciones:** No crees ni modifiques ningún archivo.

---

## Por qué funciona

Cuando Claude explora antes de implementar, ancla sus decisiones en la realidad del código en lugar de en suposiciones genéricas. El resultado directo: el código que genere después será consistente con lo que ya existe. El resultado indirecto: tú también entiendes mejor tu propio proyecto al leer el análisis.

---

## Preguntas Útiles para Exploración

### Arquitectura
- ¿Qué patrón arquitectónico sigue? (MVC, Hexagonal, Layered, etc.)
- ¿Cómo se organizan las carpetas?
- ¿Cuáles son los entry points principales?

### Flujos
- Traza el flujo completo de [operación específica]
- ¿Qué archivos intervienen en [funcionalidad]?
- ¿Cómo fluyen los datos desde entrada hasta salida?

### Convenciones
- ¿Qué convenciones de naming se usan?
- ¿Cómo se manejan los errores?
- ¿Qué patrones de imports se siguen?
- ¿Qué estructura tienen las funciones?

### Dependencias
- ¿Qué partes del código dependen de [módulo X]?
- Si modifico [archivo], ¿qué podría romperse?
- ¿Qué módulos son más críticos?

---

## Casos de uso
- ✅ Onboarding en proyectos nuevos
- ✅ Antes de refactorizaciones grandes
- ✅ Auditorías de código
- ✅ Planificación de features complejas
- ✅ Análisis de deuda técnica

---

## 💡 Mejores Prácticas

1. **Explora antes de implementar** - Siempre
2. **Haz preguntas específicas** - No genéricas
3. **Pide ejemplos concretos** - No solo teoría
4. **Solicita diagramas** cuando sea útil
5. **Enfócate en un módulo a la vez** - No todo el proyecto
