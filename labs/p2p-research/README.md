# P2P Research — Fiabilidad y confianza

> Experimentos con aplicaciones P2P en el ecosistema Apple.

## Pregunta principal

¿Cómo pueden descubrirse dispositivos cercanos e intercambiar información sin confundir **descubrimiento** con **autorización** y manteniendo comprensibles los estados de error?

## Capas del sistema

~~~text
Interfaz de usuario
↓
Estado de sesión
↓
Política de autorización
↓
Validación de mensajes
↓
Abstracción del transporte
↓
Descubrimiento de dispositivos
~~~

## Secuencia de referencia

~~~mermaid
sequenceDiagram
    participant A as Dispositivo A
    participant D as Capa de descubrimiento
    participant B as Dispositivo B
    A->>D: anunciar capacidad
    B->>D: buscar servicio autorizado
    D-->>A: dispositivo descubierto
    D-->>B: dispositivo descubierto
    A->>B: propuesta de identidad
    B-->>A: decisión de autorización
    A->>B: mensaje validado
    B-->>A: confirmación
~~~

## Aspectos técnicos

- **Descubrimiento:** visibilidad de un extremo compatible, sin conceder confianza.
- **Autorización:** estado independiente de la conectividad.
- **Validación:** cada mensaje entrante es no fiable hasta decodificarlo y validarlo.
- **Persistencia:** conservar únicamente el estado necesario para restaurar una experiencia segura.
- **Fallos:** caducidades, desconexiones y estados obsoletos son situaciones previstas.

## Matriz de pruebas

| Situación | Comportamiento esperado |
|---|---|
| Desaparece un extremo durante una sesión | Cierre ordenado |
| Descubrimiento duplicado | No repetir solicitud de autorización |
| Mensaje de extremo desconocido | Rechazo |
| Mensaje malformado | Error controlado |
| Reinicio de aplicación | Restaurar confianza solo cuando se guardó expresamente |
| Sin red | Mostrar estado degradado claro |

**Solo pruebas defensivas en dispositivos propios o autorizados.** © 2026 Fran Gonzas
