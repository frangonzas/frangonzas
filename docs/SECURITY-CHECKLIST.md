# Lista de verificación de ingeniería de seguridad

## Repositorio y dependencias

- [ ] No se incluyen contraseñas, claves API, tokens, certificados ni claves privadas.
- [ ] \`.gitignore\` excluye secretos y archivos de compilación locales.
- [ ] La documentación pública no revela infraestructura privada.
- [ ] Las dependencias son necesarias y han sido revisadas.

## Autenticación y autorización

- [ ] Se distinguen ambos conceptos.
- [ ] Las acciones privilegiadas requieren autorización explícita.
- [ ] La caducidad y revocación de sesiones están definidas.
- [ ] Se documenta la eliminación de cuentas o identidades.

## Criptografía

- [ ] Se utilizan primitivas reconocidas o proporcionadas por la plataforma.
- [ ] No se inventan algoritmos propios de cifrado.
- [ ] Se ha definido el ciclo de vida de las claves.
- [ ] Se respetan los requisitos de \`nonce\` e IV.
- [ ] Se comprueban integridad y autenticidad.
- [ ] No se escriben valores sensibles en registros.

## Almacenamiento

- [ ] Se minimizan los datos sensibles.
- [ ] La clase de protección y el almacenamiento son adecuados.
- [ ] Las cachés tienen una política de conservación.
- [ ] Se prueba la eliminación destructiva.

## Red y comunicaciones

- [ ] Las API públicas utilizan TLS.
- [ ] Se validan las respuestas externas.
- [ ] Los tiempos de espera están definidos.
- [ ] Se limita el número de reintentos.
- [ ] Se gestionan los modos sin conexión y degradados.
- [ ] El descubrimiento P2P no concede confianza automáticamente.

## Entradas de datos

- [ ] Los datos externos se consideran no fiables.
- [ ] Los errores de decodificación se gestionan de forma segura.
- [ ] Existen límites de tamaño.
- [ ] Las URL y enlaces profundos se validan antes de abrirlos.

## Privacidad

- [ ] Se recopila solo lo necesario.
- [ ] Los textos de permisos coinciden con el comportamiento.
- [ ] Se documentan las analíticas y los SDK de terceros.
- [ ] La política de privacidad corresponde a la versión publicada.

## Publicación

- [ ] Se ha revisado el modelo de amenazas.
- [ ] Se han revisado los registros de depuración.
- [ ] Se han retirado las credenciales de prueba.
- [ ] Se han probado acciones destructivas en dispositivo físico.
- [ ] Se ha revisado el tratamiento de errores sensibles.
- [ ] Se ha probado la recuperación ante fallos.
