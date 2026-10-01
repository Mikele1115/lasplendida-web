# lasplendida.cl

Página "Pronto" de La Splendida, una pizzería napolitana que todavía no
abre: el logo, un botón para escribir al correo y otro para ir a Instagram.

En vivo: https://www.lasplendida.cl

Es un solo `public/index.html`, sin frameworks ni dependencias.

Tiene dos diseños de color, con un switch arriba a la derecha:

- **Rojo** (por defecto): fondo rojo y logo crema, `public/logo.png`.
- **Crema:** fondo crema, logo rojo con bajada verde, `public/logo-crema.png`.

Los colores son variables CSS que cambian según `data-tema` en `<html>`. La
elección del visitante se guarda en su navegador (`localStorage`) y se
aplica antes de pintar la página, para que no parpadee.

Netlify publica únicamente la carpeta `public/` (lo indica `netlify.toml`),
así que este README no queda accesible en el sitio.

## Publicación

- **Hosting:** Netlify, conectado a este repositorio: cada push a `main`
  se publica solo.
- **DNS:** el dominio `.cl` está registrado en NIC Chile y delega sus DNS a
  Cloudflare. Ahí, `@` y `www` son registros CNAME hacia el sitio de Netlify,
  en modo "Solo DNS" (nube gris) para que Netlify pueda emitir el
  certificado.
- **HTTPS:** certificado de Let's Encrypt emitido y renovado por Netlify.
- **Dominio principal:** `www.lasplendida.cl`; `lasplendida.cl` y `http://`
  redirigen ahí.
- **Correo:** los registros MX, SPF y DKIM de Zoho siguen en Cloudflare;
  la web no los toca.

Para actualizar: editar `public/index.html`, hacer commit y push a `main`.
