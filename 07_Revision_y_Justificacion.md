# 🤔 Patrón: Pedir Justificación

## Descripción
Este no es un patrón de implementación. Es un patrón de revisión. Lo usas después de que Claude haya hecho algo para entender por qué tomó esas decisiones y si hay alternativas mejores.

---

## Estructura del Patrón

### Tarea
```
Sobre [la implementación que acabas de hacer]:
1. ¿Qué alternativas consideraste y por qué elegiste esta?
2. ¿Qué trade-offs tiene tu decisión?
3. ¿Qué podría fallar con este enfoque?
4. ¿Qué harías diferente con más tiempo o a mayor escala?
```

---

## Ejemplo Completo

**Sobre la implementación del tracking de clicks:**

1. ¿Qué alternativas consideraste para registrar los clicks
   sin bloquear el redirect?
2. ¿Qué pasa si la escritura en base de datos falla? ¿Se pierde
   el click silenciosamente?
3. Si una URL recibe 10.000 clicks por segundo, ¿qué parte
   del sistema falla primero?
4. Si tuvieras que escalar esto para millones de URLs,
   ¿qué cambiarías de la arquitectura?

---

## Por qué funciona

Claude no suele explicar sus decisiones a menos que se lo pidas. Y muchas veces la primera solución que propone es correcta pero no es la mejor. Este patrón convierte a Claude en un revisor de su propio código. Las respuestas te ayudan a decidir si aceptas la implementación tal cual, si pides cambios, o si necesitas un enfoque completamente distinto.

---

## Preguntas Clave para Revisión

### Alternativas
- ¿Qué otros enfoques consideraste?
- ¿Por qué elegiste este sobre los demás?
- ¿Hay patrones estándar para este problema?

### Trade-offs
- ¿Qué ventajas tiene esta solución?
- ¿Qué desventajas o limitaciones tiene?
- ¿Qué sacrificaste para obtener qué beneficio?

### Riesgos
- ¿Qué podría fallar?
- ¿Qué casos edge no cubre?
- ¿Qué efectos secundarios podría tener?

### Escalabilidad
- ¿Cómo se comporta con 10x más carga?
- ¿Qué parte falla primero bajo presión?
- ¿Qué cambiarías para producción?

### Mantenibilidad
- ¿Es fácil de entender para otros devs?
- ¿Es fácil de testear?
- ¿Es fácil de modificar en el futuro?

---

## Casos de uso
- ✅ Después de implementaciones complejas
- ✅ Antes de mergear código importante
- ✅ Para entender decisiones de diseño
- ✅ Durante code reviews
- ✅ Para evaluar diferentes soluciones

---

## 💡 Cuándo Usar Este Patrón

### ✅ Úsalo cuando:
- La solución funciona pero parece "demasiado simple"
- Tienes dudas sobre la escalabilidad
- Necesitas documentar decisiones de arquitectura
- Quieres aprender del proceso

### ⚠️ No lo uses cuando:
- Es un cambio trivial y obvio
- Ya conoces todas las alternativas
- El tiempo es crítico (pero revisa después)

---

## Ejemplo de Conversación Completa

**Usuario:** Implementa un sistema de caché para las consultas de usuario.

**Claude:** [Implementa Redis con TTL de 5 minutos]

**Usuario:** Sobre la implementación del caché:
1. ¿Por qué Redis y no memcached o caché en memoria?
2. ¿Por qué 5 minutos de TTL?
3. ¿Qué pasa si Redis cae?
4. ¿Cómo invalidas el caché cuando se actualiza un usuario?

**Claude:** [Explica decisiones, revela posibles problemas]

**Usuario:** Modifica la implementación para manejar el caso de Redis caído con fallback a DB.

---

## Beneficios

1. **Aprendes el razonamiento** detrás del código
2. **Descubres edge cases** no considerados
3. **Evalúas trade-offs** informadamente
4. **Mejoras la solución** antes de comprometerte
5. **Documentas decisiones** para el futuro
