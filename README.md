# Sitio web del colegio

Base informativa construida con Astro. Está preparada para desplegarse como sitio estático y crecer sin cambiar su estructura principal.

## Ejecutar en el equipo

1. Instala Node.js 20 o superior.
2. Ejecuta `npm install`.
3. Ejecuta `npm run dev` y abre la dirección que aparezca en pantalla.
4. Ejecuta `npm run build` antes de publicar. El resultado queda en `dist/`.

## Personalización imprescindible

- Reemplaza **Colegio Horizonte** por el nombre real, correo, teléfono, dirección y horarios.
- Actualiza la propiedad `site` de `astro.config.mjs` con el dominio final.
- Sube los PDF a `public/documentos/` conservando los nombres usados en `src/pages/manual-de-convivencia.astro`, o cambia allí los enlaces.
- Sustituye el texto y los indicadores de admisiones por la información oficial.

## Despliegue recomendado: Netlify

1. Crea un repositorio en GitHub y sube este proyecto.
2. En Netlify selecciona **Add new site > Import an existing project** y conecta el repositorio.
3. Confirma `npm run build` como comando y `dist` como carpeta de publicación (el archivo `netlify.toml` ya lo define).
4. Cada cambio enviado a la rama principal publicará una nueva versión.
5. Para el formulario, Netlify detectará el atributo `data-netlify="true"` al primer despliegue; revisa los mensajes en la sección Forms.

## Decap CMS (cuando el personal vaya a editar contenido)

La ruta `/admin/` está deshabilitada deliberadamente hasta que se configure Netlify Identity y Git Gateway. No carga scripts externos ni permite registros. Cuando se habilite, invita únicamente a los administradores aprobados, usa una versión fija y revisada de Decap CMS, y ajusta la CSP de `netlify.toml` para los orígenes estrictamente necesarios. La configuración inicial permite administrar documentos y noticias en el repositorio.

Para usar GitHub Pages en vez de Netlify, elimina o cambia el formulario: GitHub Pages no procesa envíos ni ofrece autenticación para Decap por sí mismo. Puedes mantener el sitio estático, pero los formularios y CMS requerirán servicios adicionales.
