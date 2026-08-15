# 📚 Patrón: Documentar

## Descripción
El patrón más sencillo en estructura pero el que más se beneficia de especificar el formato. Sin indicar qué quieres, Claude produce documentación genérica que no ayuda a nadie.

---

## Estructura del Patrón

### Contexto
`[Qué va a leer esta documentación y para qué]`

### Tarea
```
Genera documentación para [archivo/módulo/API] incluyendo:
- [qué secciones necesitas]
- [qué nivel de detalle]
```

### Formato
```
[Markdown, JSDoc, README section, etc.]
[Incluir o no ejemplos de uso]
```

### Verificación
```
Lee el resultado y verifica que cubre todos los
[endpoints/funciones/módulos] que existen actualmente.
```

---

## Ejemplo Completo

**Contexto:** Nuevos desarrolladores van a incorporarse al proyecto
Snap y necesitan una referencia de la API para empezar a trabajar.

**Tarea:** Genera un archivo docs/API.md con la documentación completa:
- Descripción breve del proyecto
- Instrucciones para instalar, ejecutar y testear
- Cada endpoint: método HTTP, ruta, si requiere autenticación,
  qué parámetros espera, qué devuelve, y los posibles errores
- Un ejemplo con curl para cada endpoint

**Formato:** Markdown con secciones por módulo (Auth, URLs, Dashboard).

**Verificación:** Compara el archivo generado con las rutas registradas
en el código. Si falta algún endpoint, añádelo.

---

## Por qué funciona

Definir quién va a leer la documentación cambia radicalmente el resultado. "Documentación para onboarding de desarrolladores" produce algo distinto a "documentación para el equipo de QA" o "documentación para el cliente". Y la verificación cruzada contra el código real previene la documentación desactualizada desde el minuto cero.

---

## Tipos de Documentación

### 1. README del Proyecto
✅ Descripción general
✅ Instalación y setup
✅ Estructura del proyecto
✅ Comandos principales

### 2. Documentación de API
✅ Endpoints disponibles
✅ Autenticación
✅ Request/Response examples
✅ Códigos de error

### 3. Documentación de Código
✅ JSDoc / Docstrings
✅ Comentarios inline
✅ Descripciones de funciones
✅ Parámetros y retornos

### 4. Documentación de Arquitectura
✅ Diagramas de sistema
✅ Decisiones de diseño
✅ Patrones utilizados
✅ Flujos principales

### 5. Guías de Contribución
✅ Cómo contribuir
✅ Estándares de código
✅ Proceso de PR
✅ Testing guidelines

---

## Audiencias y sus Necesidades

| Audiencia | Qué necesitan |
|-----------|---------------|
| **Nuevos Devs** | Setup, arquitectura, convenciones |
| **Colaboradores** | API reference, guías de contribución |
| **QA/Testing** | Casos de prueba, endpoints, estados |
| **Product/Business** | Funcionalidades, limitaciones, roadmap |
| **DevOps** | Deploy, configuración, monitoreo |

---

## Casos de uso
- ✅ Onboarding de nuevos desarrolladores
- ✅ Documentación de API pública
- ✅ Guías de uso interno
- ✅ Decisiones de arquitectura (ADRs)
- ✅ Troubleshooting guides

---

## ✅ Checklist: Documentación de Calidad

- [ ] Define la audiencia claramente
- [ ] Incluye ejemplos concretos
- [ ] Mantiene consistencia con el código actual
- [ ] Es fácil de actualizar
- [ ] Incluye fecha de última actualización
- [ ] Tiene índice/tabla de contenidos (si es largo)
- [ ] Los enlaces funcionan
- [ ] Los ejemplos de código son ejecutables
