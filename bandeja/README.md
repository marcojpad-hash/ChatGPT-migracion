# Bandeja entre modelos

Deja aquí un archivo Markdown por asunto usando PLANTILLA.md. Esta carpeta es un buzón persistente, no un chat ni una notificación automática.
Los resueltos se mueven a resueltos/. La coordinación y las reglas están en ../docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md.

## Flujo
1. El emisor crea el aviso con ID estable y destinatario.
2. El destinatario confirma lectura y cambia el estado a RECIBIDO; si no puede, marca BLOQUEADO con evidencia.
3. El destinatario trabaja en el repositorio especializado y deja enlaces a commits/artefactos.
4. El emisor o auditor relee y verifica el resultado.
5. Solo después de verificar se mueve el aviso a resueltos/.

## Estados
PENDIENTE → RECIBIDO → EN_PROCESO → ENTREGADO → VERIFICADO.
Si hay impedimento real: BLOQUEADO, con causa, evidencia y alternativa.

No asumir recepción por la mera existencia del archivo. No poner secretos, tokens, contraseñas ni datos privados.