# lasplendida.cl

Página "Pronto" de La Splendida, una pizzería napolitana que todavía no
abre: el logo, un botón para escribir al correo y otro para ir a Instagram.

En vivo: https://www.lasplendida.cl

Es un solo `index.html`, sin frameworks ni dependencias. El logo va
incrustado en el HTML (base64) para que la página funcione aunque se suba
sin la imagen; `logo.png` queda en la carpeta solo como imagen de vista
previa cuando se comparte el enlace (`og:image`).

## Publicación

- **Hosting:** Netlify, subiendo la carpeta con Netlify Drop.
- **DNS:** el dominio `.cl` está registrado en NIC Chile y delega sus DNS a
  Cloudflare. Ahí, `@` y `www` son registros CNAME hacia el sitio de Netlify,
  en modo "Solo DNS" (nube gris) para que Netlify pueda emitir el
  certificado.
- **HTTPS:** certificado de Let's Encrypt emitido y renovado por Netlify.
- **Dominio principal:** `www.lasplendida.cl`; `lasplendida.cl` y `http://`
  redirigen ahí.
- **Correo:** los registros MX, SPF y DKIM de Zoho siguen en Cloudflare;
  la web no los toca.

Para actualizar: editar `index.html` y volver a arrastrar la carpeta en
Netlify → Deploys.
