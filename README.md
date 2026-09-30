# tenaz-web

El sitio público de **Tenaz**: qué es, qué registra y por qué. La aplicación vive
en otro repo (`appentreno`) y en otro dominio.

| | Dónde | Repo |
|---|---|---|
| Este sitio | `tenaz.com.ar` | `tenaz-web` |
| La app | `app.tenaz.com.ar` | `appentreno` |

Son dos sitios de GitHub Pages con un dominio propio cada uno. GitHub permite un
dominio por repo, así que la separación no tiene truco.

## Qué hay acá

```
index.html          la landing, en un solo archivo
privacidad.html     política de privacidad
borrar-cuenta.html  cómo eliminar la cuenta   ← Google Play exige esta URL
img/                capturas del producto, en WebP
.nojekyll           imprescindible, ver abajo
```

**Las dos páginas legales viven acá y no en el repo de la app**, aunque las
enlace la app. El motivo: quien quiere borrar su cuenta y ya desinstaló la app va
a buscar el sitio público; y Play las enlaza desde la ficha, donde el usuario
todavía no instaló nada.

## `.nojekyll`

GitHub Pages corre Jekyll por defecto y Jekyll **ignora todo lo que empieza con
punto o guión bajo**. El archivo vacío `.nojekyll` desactiva ese paso. Sin él, el
día que haga falta servir algo como `/.well-known/` se commitea, se ve en GitHub
y **nunca se sirve**, sin ningún error que lo delate.

## Las capturas

Salen del arnés de vista previa que está en el repo `appentreno-docs`
(`preview/capturar.mjs`), que levanta la app real contra **datos falsos con
semilla fija**. Dos consecuencias que importan:

- Son el producto de verdad, no una maqueta que puede divergir de lo que se
  despliega.
- No exponen datos de nadie, así que se pueden publicar sin pensarlo.

Para rehacerlas: capturar en `appentreno-docs`, y convertir a WebP a 640px de
ancho, que es lo más grande que la landing llega a mostrar.

## El diseño

Usa **los mismos tokens y las mismas tipografías que la app** —el verde, el
naranja, Bricolage Grotesque, Hanken Grotesk, Sometype Mono— para que el sitio y
el producto se lean como una sola cosa y no como una campaña por un lado y un
software por el otro. Los íconos de las cuatro tarjetas son, literalmente, los
mismos SVG que usa la app.

Sin dependencias, sin build, sin framework: se edita y se publica.

## Probarlo

Alcanza con abrir `index.html` en el navegador. Para revisarlo como lo hago yo,
con medición de desbordes y capturas a varios anchos, está el arnés de
`appentreno-docs/preview/`.
