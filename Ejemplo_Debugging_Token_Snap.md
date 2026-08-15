Contexto: Estoy en el dashboard de Snap con un usuario logueado.
Si navego normalmente todo funciona, pero al refrescar la página
con F5 me aparece "no autorizado", como si el token se perdiera.
Me ocurrió al actualizar para comprobar que el contador de clicks
se había incrementado.

Tarea: El token no sobrevive a un refresh de página. Necesito
encontrar dónde se almacena el token en el frontend y por qué
no persiste al recargar.

Formato: Antes de corregir nada:
1. Identifica la causa raíz, no el síntoma
2. Explica por qué ocurre
3. Propón el fix y justifícalo
4. ¿Qué más podría verse afectado?

Verificación: Tras el fix, debo poder hacer login, ver el
dashboard, refrescar la página con F5, y seguir viendo el
dashboard sin que me pida login de nuevo.