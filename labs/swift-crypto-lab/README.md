# Swift Crypto Lab — Criptografía aplicada

> Ejercicios pequeños y auditables de seguridad en plataformas Apple.

## Propósito

Comprender los componentes criptográficos disponibles en Swift **sin reimplementar algoritmos de cifrado desde cero**.

~~~text
Utilizar primitivas contrastadas
Componer con cuidado
Almacenar claves con protección
Rotar cuando sea necesario
No registrar secretos
~~~

## Materias tratadas

Fundamentos de CryptoKit, cifrado simétrico, identidad con clave pública, firmas, derivación de claves, almacenamiento seguro, unicidad de nonce, codificación de datos y ciclo de vida de claves.

## Flujo conceptual

~~~mermaid
flowchart TD
    A[Datos de aplicación] --> B[Codificación canónica]
    B --> C[Primitiva CryptoKit]
    D[Material de clave] --> C
    C --> E[Texto cifrado o firma]
    E --> F[Transporte o almacenamiento]
    F --> G[Verificación o descifrado]
    G --> H[Datos validados]
~~~

## Lista de verificación

- [ ] Se usan primitivas de plataforma.
- [ ] Las claves no están en Git.
- [ ] Se utiliza almacenamiento protegido.
- [ ] Los nonce son únicos cuando corresponde.
- [ ] Se verifica la autenticidad antes de aceptar datos descifrados.
- [ ] Los errores no filtran información sensible.
- [ ] Los logs no guardan secretos.
- [ ] Existe un modelo de amenazas.

Este repositorio no desarrolla algoritmos criptográficos nuevos ni herramientas ofensivas.

[Lista de seguridad compartida](../../docs/SECURITY-CHECKLIST.md). © 2026 Fran Gonzas
