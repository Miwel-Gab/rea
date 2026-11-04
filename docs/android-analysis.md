# Análisis estático de APKs de Android

REA envuelve un motor JADX headless existente a través de `src/android/`. Su código fuente se mantiene como un submódulo de Git sin modificar y fijado a un commit específico; consulta la [procedencia original](https://github.com/morluto/rea/blob/main/third_party/README.md). Tanto la CLI como MCP utilizan el mismo flujo de trabajo de la aplicación y devuelven Evidencia vinculada a artefactos de forma integrada.

Esta familia de herramientas está presente en la rama `main` del repositorio y en npm 4.1.0. Comprueba los [límites del paquete publicado](installation.md#released-package-and-main) y la lista de herramientas del servidor conectado antes de seleccionarla.

En Linux, JADX inicia un proceso propiedad de REA y requiere un ejecutable `ps` compatible con procps en el `PATH` de REA; consulta los [requisitos previos de procesos de Linux](installation.md#linux-owned-process-prerequisite).

## Entrega opcional de paquetes

La solicitud MCP `inspect_android_package` conserva la salida completa cuando se omite el parámetro `detail` o se establece en `"complete"`. Selecciona explícitamente `detail: "summary"` para recibir todas
