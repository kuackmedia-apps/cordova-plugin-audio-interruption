# Fork de kuackmedia

Fork de [WinGood/cordova-plugin-audio-interruption](https://github.com/WinGood/cordova-plugin-audio-interruption) en la versión `0.1.3` publicada en npm (Apache 2.0, declarada en `plugin.xml` (upstream no tiene archivo de licencia)). Lo usan las apps Cordova de
Kuack Media para la pausa y la vuelta de la música en una llamada (`utils/PlayerInterruptions.js`, `AudioInterruption.addListener`).

Base: `49379f0` (upstream no tiene tag de esa versión), idéntico al paquete `cordova-plugin-audio-interruption@0.1.3` de npm que las apps instalaban hasta noviembre de 2026.

**Lo publicado es el commit fijado en `_common/configTemplates/config-app*.xml`** del repo de las apps
(`github:kuackmedia-apps/cordova-plugin-audio-interruption#<sha>`), no la punta de una branch: un push a este repo no llega a ningún
binario hasta que se mueve ese pin, y mover el pin es un diff que se revisa. La branch `kuack` es la línea de
Kuack; `master` queda como el de upstream.

## Cambios respecto de upstream

Ninguno en el código: el fork existe para que el app dependa sólo de Apache Cordova y de repos de Kuack (fila A18 del RFP de Claro, CM-RFP-001).

## Para actualizar desde upstream

`git fetch upstream --tags`, en una branch merge (o rebase) de la versión nueva sobre `kuack`, revisar los
cambios de arriba, probarlo en un app con `config-app-local.xml` (path local del checkout), llevarlo a `kuack` y
mover el pin en los `config-app*.xml`. Nunca cambiar el `id` del plugin ni sus `clobbers`: el bundle remoto lo
comparten los binarios publicados.
