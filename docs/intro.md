---
sidebar_position: 1
---

# Introducción

Descubramos **Docusaurus en menos de 5 minutos**.

## Comenzando

Comienza por **crear un nuevo sitio**.

O **prueba Docusaurus de inmediato** con **[docusaurus.new](https://docusaurus.new)**.

### Lo que necesitarás

- [Node.js](https://nodejs.org/en/download/) versión 18.0 o superior:
  - Al instalar Node.js, se recomienda marcar todas las casillas relacionadas con las dependencias.

## Generar un nuevo sitio

Genera un nuevo sitio de Docusaurus utilizando la **plantilla clásica**.

La plantilla clásica se añadirá automáticamente a tu proyecto después de ejecutar el siguiente comando:

```bash
npm init docusaurus@latest mi-sitio-web classic
```

Puedes escribir este comando en el Símbolo del sistema, Powershell, Terminal, o cualquier otra terminal integrada de tu editor de código.

El comando también instala todas las dependencias necesarias que necesitas para ejecutar Docusaurus.

## Inicia tu sitio

Ejecuta el servidor de desarrollo:

```bash
cd mi-sitio-web
npm run start
```

El comando `cd` cambia el directorio en el que estás trabajando. Para trabajar con tu sitio de Docusaurus recién creado, necesitarás navegar la terminal hasta allí.

El comando `npm run start` construye tu sitio web localmente y lo sirve a través de un servidor de desarrollo, listo para que lo veas en http://localhost:3000/.

Abre `docs/intro.md` (esta página) y edita algunas líneas: el sitio **se recarga automáticamente** y muestra tus cambios.
