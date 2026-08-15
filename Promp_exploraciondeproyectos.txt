----- Prompt 1 -----

# Entender la arquitectura
¿Cómo está organizado este proyecto? Describe la estructura
de carpetas, los patrones principales y los entry points.

# Trazar un flujo
Traza el flujo completo de una petición a GET /health:
desde que llega la request hasta que se envía la response.
¿Qué archivos toca y en qué orden?

# Entender convenciones
Mira 3-4 archivos de ejemplo y extrae las reglas implícitas:
naming, imports, manejo de errores, estructura de funciones.

# Análisis de impacto
¿Qué partes del código dependen de src/db/database.ts?
Si lo modifico, ¿qué podría romperse?


----- Prompt 2 -----

Siguiendo exactamente el mismo patrón que ya existe, añade
la funcionalidad core de Snap:
- Recibir una URL larga y generar un código corto aleatorio
- Guardar la asociación en SQLite
- Redirigir cuando alguien visita el código corto
- Listar todas las URLs creadas

Crea la tabla necesaria en SQLite. Añade tests y ejecútalos.