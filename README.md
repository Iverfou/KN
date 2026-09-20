# KN Digital · kndigital.es

Landing de KN Digital (agencia de IA en Alicante). HTML/CSS/JS estático, sin build ni dependencias. Idiomas: ES (por defecto), FR, EN.

## Contenido

```
index.html          ← toda la página (HTML + CSS + JS)
assets/             ← logo, favicon, imagen para redes (og-image.png)
CNAME               ← dominio personalizado: kndigital.es
robots.txt · sitemap.xml · 404.html · .nojekyll
```

## Publicar en GitHub Pages

1. Crea un repositorio (p. ej. `kndigital-web`) y sube todo el contenido de esta carpeta a la rama `main` (la raíz, no una subcarpeta).
2. En GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch → `main` / `(root)`** → Save.
3. **Settings → Pages → Custom domain**: `kndigital.es` (ya lo indica el fichero `CNAME`). Activa **Enforce HTTPS** cuando esté disponible.
4. En el proveedor del dominio (DNS de `kndigital.es`), crea:
   - 4 registros **A** para `@` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - 1 registro **CNAME** para `www` → `TU-USUARIO.github.io`
   
   (Comprueba las IP actuales en la documentación oficial de GitHub Pages.) La propagación puede tardar de minutos a 24 h.

## Formulario de citas

Por defecto, al enviar, se abre el correo del visitante con la solicitud redactada hacia **contact@kndigital.es** (funciona sin servidor).

Para recibir las solicitudes directamente sin que el visitante use su correo, edita al inicio del `<script>` de `index.html`:

```js
const CONFIG = {
  email: 'contact@kndigital.es',
  formEndpoint: 'https://formspree.io/f/XXXXXXX'   // o webhook de Make / n8n que acepte JSON
};
```

## Editar textos

Todos los textos (ES/FR/EN) están en el objeto `COPY` del `<script>` de `index.html`. Se pueden abrir con `?lang=fr` o `?lang=en`.

## Pendiente antes de lanzar

- Confirmar el usuario de Instagram (`@kndigia`) y el enlace en `index.html`.
- Páginas legales (Aviso legal, Política de privacidad, cookies si añades analítica), obligatorias en España (LSSI-CE / RGPD).
- Dirección o teléfono/WhatsApp si quieres mostrarlos.
