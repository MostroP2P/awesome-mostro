<h1 align="center">Awesome Mostro <a href="https://awesome.re"><img src="https://awesome.re/badge.svg" alt="Awesome"></a></h1>

<p align="center">
  <img src="assets/logo.png" alt="Mostro" width="360">
</p>

<p align="center"><a href="README.md">English</a> · <b>Español</b></p>

Una lista colaborativa y seleccionada de recursos, clientes, herramientas y proyectos para [Mostro](https://mostro.network), el exchange peer-to-peer de Bitcoin sobre Lightning Network y Nostr.

## ¿Qué es Mostro?

Mostro es una plataforma peer-to-peer y sin custodia para comprar y vender Bitcoin por Lightning Network, que usa [Nostr](https://nostr.com) como capa de comunicación. No hay cuentas ni KYC, y nadie custodia los fondos de los usuarios: los sats del vendedor quedan bloqueados con una hold invoice hasta que termina el intercambio.

Cualquiera puede montar su propio nodo Mostro (`mostrod`) y dar servicio a su comunidad. Visita [mostro.network](https://mostro.network) para saber más.

## Contenido

- [El protocolo Mostro](#el-protocolo-mostro)
- [Daemon](#daemon)
- [Clientes](#clientes)
- [Librerías](#librerías)
- [Disputas y administración](#disputas-y-administración)
- [Operación de nodos](#operación-de-nodos)
- [Estadísticas y monitorización](#estadísticas-y-monitorización)
- [IA y agentes](#ia-y-agentes)
- [Herramientas de desarrollo y pruebas](#herramientas-de-desarrollo-y-pruebas)
- [Documentación](#documentación)
- [Sitios web y comunidad](#sitios-web-y-comunidad)
- [Archivados](#archivados)
- [Contribuir](#contribuir)

## El protocolo Mostro

Mostro es un protocolo abierto: las órdenes, los intercambios, las disputas y las calificaciones son eventos de Nostr que cualquier cliente puede leer y usar.

- [Especificación del protocolo](https://mostro.network/protocol/) ([código](https://github.com/MostroP2P/protocol)) es el sitio de documentación de las especificaciones de Mostro.
- [NIP-69](https://github.com/nostr-protocol/nips/blob/master/69.md) es el estándar de Nostr para eventos de órdenes peer-to-peer (kind 38383) que Mostro usa para publicar sus órdenes, de modo que distintas plataformas P2P puedan compartir la misma liquidez.

## Daemon

- [mostro](https://github.com/MostroP2P/mostro) es `mostrod`, el daemon de Mostro en Rust que empareja órdenes, gestiona las hold invoices y se comunica con los clientes por Nostr.
- [mostro-startos](https://github.com/MostroP2P/mostro-startos) es el paquete para correr un nodo Mostro en StartOS.

## Clientes

- [Mostro App](https://github.com/MostroP2P/app) es el cliente oficial para Android, Windows, macOS, Linux, iOS y la [web](https://mostro.network/app/), con un núcleo en Rust y una interfaz en Flutter.
- [mostro-cli](https://github.com/MostroP2P/mostro-cli) es el cliente de línea de comandos, con una interfaz JSON versionada (`--output json`) para usarlo desde otros programas.
- [Mostrix](https://github.com/MostroP2P/mostrix) es un cliente de terminal (TUI) para Mostro, con un modo de administración para quienes resuelven disputas.

## Librerías

- [mostro-core](https://github.com/MostroP2P/mostro-core) es el crate de Rust con los tipos comunes que comparten Mostro y sus clientes.
- [dart-nip44](https://github.com/MostroP2P/dart-nip44) es una implementación en Dart del cifrado NIP-44 (fork).

## Disputas y administración

- [Bosstro](https://github.com/MostroP2P/bosstro) es la app de Android para quienes resuelven disputas: tomarlas, chatear con ambas partes y pagar al comprador o devolver al vendedor desde el teléfono.
- [Serbero](https://github.com/MostroP2P/serbero) es un asistente de disputas que se asegura de que cada disputa llegue a los solvers, habla con ambas partes y, cuando hace falta, pasa el caso a un solver con un resumen claro.
- [Serbero (legacy)](https://github.com/MostroP2P/serbero_legacy) es el sistema anterior de coordinación y notificación de disputas.
- [mostro-watchdog](https://github.com/MostroP2P/mostro-watchdog) es un bot de notificaciones para administradores de Mostro que vigila los eventos de disputa y envía alertas en tiempo real por Telegram.

## Operación de nodos

- [Mostromancer](https://github.com/MostroP2P/mostromancer) es un asistente web que configura un nodo Mostro y genera un instalador con Docker, opcionalmente con LND, Bitcoin Core y Lightning Terminal. Funciona por completo en el navegador.
- [mostro-push-server](https://github.com/MostroP2P/mostro-push-server) es el servidor de notificaciones push de la app móvil de Mostro.
- [scripts-mostro](https://github.com/21Mill/scripts-mostro) es un conjunto de scripts de gestión, monitorización y automatización para un nodo Mostro: actualizaciones verificadas y rollbacks, instantáneas de solo lectura de la base de datos, contabilidad y bots de Telegram y Nostr que publican ofertas.

## Estadísticas y monitorización

- [Semáforo](https://status.mostro.network) ([código](https://github.com/MostroP2P/semaforo)) es la página pública de estado de las instancias de Mostro de confianza, construida a partir de eventos de salud firmados (kind 38389) que se verifican en el navegador.
- [Bestiario](https://github.com/MostroP2P/bestiario) calcula estadísticas de la red Mostro a partir de los eventos públicos de Nostr que publican sus instancias; [bestiario-fe](https://github.com/MostroP2P/bestiario-fe) es su frontend, que verifica los eventos firmados en el navegador.
- [mostro-score](https://github.com/MostroP2P/mostro-score) es una herramienta de línea de comandos que calcula estadísticas de reputación de nodos Mostro a partir de eventos públicos de Nostr; [mostro-score-web](https://github.com/MostroP2P/mostro-score-web) es su versión web.
- [mstats](https://github.com/MostroP2P/mstats) es una herramienta de línea de comandos de estadísticas de trading que cruza los eventos de comisión de desarrollo (kind 8383) con los de órdenes (kind 38383) para dar cifras globales y por nodo.
- [tasaK](https://github.com/Forte11Cuba/tasak) calcula la tasa de cambio de una moneda local a partir de las órdenes completadas en uno o varios nodos Mostro, con cada orden verificable en Nostr. La configuración de ejemplo es Kmbalache (CUP 🇨🇺).

## IA y agentes

- [mostro-mcp](https://github.com/MostroP2P/mcp) es un servidor [MCP](https://modelcontextprotocol.io) que permite a agentes de IA operar en Mostro a través de `mostro-cli`.
- [mostro-skill](https://github.com/MostroP2P/mostro-skill) es una skill de IA para operar en Mostro que permite a los agentes interactuar con él por Nostr.
- [mostro-cli-book](https://github.com/MostroP2P/mostro-cli-book) explica cómo usar `mostro-cli` desde un programa: la interfaz JSON, cada campo, error y ejemplo (en inglés).

## Herramientas de desarrollo y pruebas

- [mostro-regtest](https://github.com/MostroP2P/mostro-regtest) es un entorno regtest en Docker con Mostro, un relay de Nostr, bitcoind, LND y ThunderHub.
- [mostro-webtool](https://github.com/MostroP2P/mostro-webtool) es una herramienta web para generar claves deterministas y construir mensajes del protocolo Mostro.
- [mortsom](https://github.com/MostroP2P/mortsom) es un entorno de pruebas end-to-end para la aplicación móvil de Mostro.
- [mostro-chat](https://github.com/MostroP2P/mostro-chat) es un chat peer-to-peer minimalista en Rust sobre Nostr.

## Documentación

- [docs-english](https://github.com/MostroP2P/docs-english) es el sitio de documentación para usuarios en inglés.
- [docs-spanish](https://github.com/MostroP2P/docs-spanish) es el sitio de documentación para usuarios en español.

## Sitios web y comunidad

- [mostro.network](https://mostro.network) ([código](https://github.com/MostroP2P/MostroP2P.github.io)) es el sitio web oficial de Mostro.
- [Blog de Mostro](https://github.com/MostroP2P/blog) es el blog de Mostro.
- [Comunidad Mostro](https://github.com/MostroP2P/community) es la página de inicio de la comunidad Mostro.
- [Mostro Foundation](https://github.com/MostroP2P/mostro-foundation-website) es el sitio web de la Fundación Mostro.
- [Mostro Store](https://store.mostro.network) ([código](https://github.com/MostroP2P/store)) es la tienda de camisetas de Mostro, con pago por Lightning y pedidos enviados cifrados por Nostr (NIP-17).

## Archivados

Proyectos que ya no se mantienen y se conservan como referencia.

- [mobile](https://github.com/MostroP2P/mobile) fue el primer cliente móvil en Flutter, reemplazado por la [Mostro App](https://github.com/MostroP2P/app).
- [documentation](https://github.com/MostroP2P/documentation) fue la documentación original de Mostro.
- [mostro.network](https://github.com/MostroP2P/mostro.network) es un repositorio de sitio web obsoleto, reemplazado por [MostroP2P.github.io](https://github.com/MostroP2P/MostroP2P.github.io).
- [old-blog](https://github.com/MostroP2P/old-blog) fue el antiguo blog en Zola.

## Contribuir

¡Las contribuciones son bienvenidas! Lee antes la [guía de contribución](CONTRIBUTING.md) (en inglés).

## Licencia

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/deed.es)

En la medida en que lo permita la ley, los contribuidores han renunciado a todos los derechos de autor y derechos conexos sobre esta obra.
