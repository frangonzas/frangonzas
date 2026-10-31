# OnyxKode Security Lab — Investigación defensiva

> Notas de arquitectura para comunicaciones móviles seguras.

## Objetivo

Estudiar cómo un sistema privado de comunicación móvil puede **reducir la confianza implícita**, proteger identidades y seguir funcionando con conectividad limitada.

Este laboratorio documenta conceptos defensivos. **No publica** contraseñas, claves privadas, credenciales ni infraestructura operativa.

## Áreas de investigación

~~~text
Identidad
├── Identidad criptográfica local
├── Ciclo de vida de claves
├── Autorización de dispositivos
└── Restablecimiento de identidad

Transporte
├── Descubrimiento P2P
├── Sesiones autenticadas
├── Mensajes cifrados
└── Funcionamiento sin conexión

Resiliencia
├── Gestión de tiempos de espera
├── Estrategias de reconexión
├── Redes degradadas
└── Experiencia de emergencias
~~~

## Arquitectura de referencia

~~~mermaid
flowchart LR
    A[Dispositivo A] -->|Descubrimiento| B[Capa P2P]
    B -->|Sesión autenticada| C[Dispositivo B]
    A --> D[Almacén de identidad]
    C --> E[Almacén de identidad]
    D --> F[Capa criptográfica]
    E --> G[Capa criptográfica]
    F -->|Mensaje cifrado| B
    G -->|Descifrar y verificar| C
~~~

## Objetivos de seguridad

| Objetivo | Requisito |
|---|---|
| Confidencialidad | Cifrar mensajes sensibles antes del transporte |
| Integridad | Detectar modificaciones de mensajes |
| Autenticación | Verificar la identidad de cada extremo |
| Mínimo privilegio | Acceso limitado a los datos necesarios |
| Recuperación | Restablecimiento de identidad explícito, auditable y controlado |
| Privacidad | Reducir exposición de metadatos siempre que sea viable |

## Suposiciones y límites

Se contemplan redes hostiles, entradas malformadas, pérdidas accidentales de datos, sesiones caducadas y dispositivos no autorizados. No se asume que una aplicación pueda proteger completamente un sistema operativo ya comprometido.

[Modelo de amenazas compartido](../../docs/THREAT-MODEL.md).

**Investigación solo sobre entornos propios o autorizados.** © 2026 Fran Gonzas
