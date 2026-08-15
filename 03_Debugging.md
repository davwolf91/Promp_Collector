# 🐛 Patrón: Depurar un Problema

## Descripción
El error más común al reportar un bug a Claude es decir "no funciona" y esperar que adivine. Claude necesita lo mismo que necesitaría un compañero de equipo: el error exacto, dónde ocurre y qué estabas haciendo.

---

## Estructura del Patrón

### Contexto
`[Qué estaba haciendo cuando ocurrió]`

### Tarea
```
Tengo este error:
[pegar error completo con stack trace]
Archivo: [archivo y línea si lo sabes]
```

### Formato
```
Antes de corregir nada, necesito que:
1. Identifica la causa raíz, no el síntoma
2. Explica por qué ocurre
3. Propón el fix y justifícalo
4. ¿Qué más podría verse afectado?
```

### Verificación
```
Añade un test que reproduzca el bug antes del fix
y que pase después. Ejecuta todos los tests.
```

---

## Ejemplo Completo

**Contexto:** Estoy probando el registro de usuarios en Snap.

**Tarea:** Cuando intento registrar un usuario con el email
"Ana@Email.COM" y después otro con "ana@email.com", el segundo
registro se crea sin error. Debería fallar porque es el mismo
email. El error no lanza excepción, simplemente crea un duplicado.

**Formato:** Antes de corregir:
1. Identifica la causa raíz, no el síntoma
2. Explica por qué ocurre
3. Propón el fix y justifícalo
4. ¿Qué más podría verse afectado?

**Verificación:** Escribe un test que registre el mismo email con
distintas mayúsculas y verifique que el segundo intento falla.
Ejecuta los tests.

---

## Por qué funciona

El escenario reproducible vale más que cualquier descripción. El formato de "antes de corregir" obliga a Claude a pensar antes de actuar, lo que produce fixes más precisos. Y pedir que identifique efectos secundarios previene que un arreglo cree dos problemas nuevos.

---

## Casos de uso
- ✅ Errores en runtime
- ✅ Bugs de lógica de negocio
- ✅ Comportamientos inesperados
- ✅ Casos edge no manejados
- ✅ Problemas de validación

---

## 💡 Tips para Mejor Debugging

1. **Incluye el stack trace completo** - No lo resumas
2. **Describe los pasos exactos** para reproducir el error
3. **Menciona qué esperabas** vs qué obtuviste
4. **Adjunta valores de variables** relevantes si los tienes
5. **Pide análisis antes de solución** - Previene fixes superficiales
