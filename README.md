# Hello Docusaurus! 🦖

Proyecto de ejemplo de uso de Docusaurus para crear documentación de proyectos de manera sencilla y eficiente, configurado para su despliegue automático en GitHub Pages.

## Creación del proyecto

Abrimos un terminal y ejecutamos el siguiente comando:

```bash
npx create-docusaurus@latest hello-docusaurus classic
```

> ⚠️ Necesitas tener `node.js` instalado.

> `classic` es un template de Docusaurus que incluye una estructura básica de documentación, con una página de inicio y una barra de navegación.

## Ejecución en local

Para ejecutar el proyecto en local, debemos seguir estos pasos:

1. Abrir un terminal y navegar hasta la carpeta del proyecto.
2. Ejecutar el siguiente comando para instalar las dependencias:

```bash
npm install
```

3. Una vez instaladas las dependencias, podemos iniciar el servidor de desarrollo con el siguiente comando:

```bash
npm run serve
```

Esto abrirá una nueva ventana en el navegador con la dirección `http://localhost:3000`, donde podremos ver nuestra documentación en vivo.

## Configuración

### Docusaurus

Para configurar **Docusaurus**, debemos editar el archivo `docusaurus.config.js` en la raíz del proyecto. En este archivo podemos modificar la configuración del sitio, como el título, la descripción, el idioma, entre otros.

A continuación se muestran algunos de los parámetros que se pueden configurar:

```js
const config: Config = {
  title: 'Hello Docusaurus',
  tagline: 'Dinosaurs are cool',
  url: 'https://<mi_usuario>.github.io/<nombre_del_repositorio>/',
  baseUrl: '/hello-docusaurus/',
  organizationName: '<mi_usuario>', // Usually your GitHub org/user name.
  projectName: '<nombre_del_repositorio>', // Usually your repo name.
  i18n: {
    defaultLocale: 'es',
    locales: ['es', 'en'],
  },
  presets: [
    [
      'classic',
      {
        docs: {
          sidebarPath: require.resolve('./sidebars.js'),
          // Please change this to your repo.
          editUrl: 'https://github.com/<mi_usuario>/<nombre_del_repositorio>/edit/main/',
        },
        blog: {
          showReadingTime: true,
          // Please change this to your repo.
          editUrl: 'https://github.com/<mi_usuario>/<nombre_del_repositorio>/edit/main/',
        },
        theme: {
          customCss: require.resolve('./src/css/custom.css'),
        },
      },
    ],
  ],
};
```

### Página principal (portada)

Podemos personalizar la portada de nuestro web de documentación editando el archivo `src/pages/index.tsx`. En este archivo podemos modificar el contenido de la página principal, como el título, la descripción y los enlaces a la documentación.

> `.tsx` es una extensión de archivo utilizada por TypeScript y React que permite escribir componentes de interfaz de usuario.

### Autores de los artículos del blog

Docusaurus incluye una funcionalidad de blog lista para usar, pero es conveniente que configuremos los distintos autores de los artículos del blog editando el fichero `blog/authors.yml`.

```yml
fvarrui:
  name: Fran Vargas
  title: Software engineer, vocational training teacher and application analyst.
  url: https://linkedin.com/in/fvarrui
  image_url: https://github.com/fvarrui.png
  page: true
  socials:
    x: fvarrui
    linkedin: fvarrui
    github: fvarrui
```

## Creación de contenidos

### Documentación 

Para publicar nuestra documentación o nuestro tutorial en **Docusaurus** sólo tenemos que incluir los documentos formato Markdown en la carpeta `docs`.

#### Ordenar los documentos

Es posible **ordenar** los documentos en el menú de navegación incluyendo la siguiente cabecera (frontmatter) en cada documento Markdown:

```yml
---
position: <n>
---
```

> Siendo `n` la posición del documento en el menú de navegación.

#### Agrupar los documentos en categorías

Para **agrupar u organizar** los documentos en categorías podemos crear subcarpetas dentro de `docs` y crear un archivo `_category_.js` para definir la categoría:

```json
{
  "label": "Mi categoría",
  "position": 3,
  "link": {
    "type": "generated-index"
  }
}
```

> `position` define la posición de la categoría en el menú de navegación.

## Publicación en GitHub Pages

Para poder publicar nuestra documentación en **GitHub Pages**, debemos seguir estos pasos:

1. Crear un repositorio en GitHub con el nombre del proyecto.
2. Habilitar **GitHub Pages** en la rama `gh-pages` del repositorio.
3. Dar permisos a las **GitHub Actions** sobre la rama `gh-pages`.

> La acción `deploy` se encargará de construir y desplegar la documentación en la rama `gh-pages`.

Una vez hecho esto, ya sólo tenemos que hacer push de los cambios a la rama `main` y esperar a que se complete el flujo de trabajo.

Una vez completados estos pasos, nuestra documentación estará disponible en `https://<mi_usuario>.github.io/<nombre_del_repositorio>/`.
