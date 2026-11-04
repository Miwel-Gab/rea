---
name: reverse-engineer-anything
description: Realiza ingeniería inversa en objetivos nativos, administrados, Electron/JavaScript, empaquetados, de firmware y de navegador con REA, y construye entornos de agentes (paquetes AgentEnv) de aplicaciones web a partir de una instancia en vivo o una captura.
metadata:
  version: "49"
---

# Metodología de Ingeniería Inversa

Aplica esta metodología estructurada al analizar binarios, APKs o sistemas:

1. **Exploración del paquete**: Inspecciona componentes declarados, permisos y estructura general.
2. **Localización de código clave**: Busca las clases principales, puntos de entrada (`MainActivity`, servicios) y métodos relevantes.
3. **Análisis de métodos**: Descompila la lógica en Java o examina el ensamblador/Smali cuando el código fuente no esté disponible.
4. **Rastreo de referencias**: Identifica qué módulos o métodos llaman a las funciones críticas.
5. **Síntesis y Documentación**: Reconstruye la regla de negocio o comportamiento observado.

## Uso de REA

Usa REA cuando una afirmación dependa de un binario o paquete enviado, descompilación, evidencia de tiempo de ejecución solicitada o comparación con un comportamiento no establecido por el código fuente disponible. Para el análisis ordinario de un repositorio fuente completo, utiliza las herramientas normales del repositorio y no ejecutes comandos de preparación de REA.

## Conexión y Recuperación

La instalación de esta habilidad proporciona instrucciones; no registra el servidor MCP de REA, no instala motores de análisis ni agrega herramientas a un agente en ejecución.

Si las herramientas de REA están disponibles, procede directamente al objetivo. Si faltan herramientas, un proveedor requerido no está disponible o surge un error de conexión, consulta la guía de recuperación y asegúrate de verificar el estado de los motores necesarios (como JDK 17+ y JADX para Android).

### Enrutamiento del objetivo principal

Elige la primera herramienta según el objetivo proporcionado:
- **APK de Android o código**: `inspect_android_package`, seguido de herramientas especializadas de Android.
- **Árbol de JavaScript / ASAR / Electron**: `analyze_javascript_application`.
- **Archivos comprimidos / Paquetes (ZIP, IPA, etc.)**: `open_binary` e `inspect_artifact.
