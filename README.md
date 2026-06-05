# endless echo

Un campo de **"e"** (echo) en cursiva —bucles enlazados que fluyen en bandas, como
oleaje— dibujado con **puntillismo** y movido por el viento real de Lima, para que las
vocales se sientan como una fuerza de la naturaleza: derivan con el aire, respiran en
profundidad (se acercan y se alejan) y se dispersan con cada ráfaga. Pensado como espejo
entre un espacio físico (un cuarto de servicio intervenido) y la web. Quien entra deja un
rastro: ecos, dibujos o mensajes que les llegan a las demás personas conectadas.

Estética de cableado desordenado, ASCII y ASMR.

- **Campo en vivo** dibujado con [p5.js](https://p5js.org/): bandas de "e" cursiva
  (trocoides de bucles enlazados) rendereadas como puntillismo, con deriva por viento y
  acercamiento/alejamiento.
- **Capa colaborativa** con [playhtml](https://playhtml.fun/): cursores en vivo,
  ecos compartidos, dibujos persistentes y mensajes que derivan. Sin backend propio.
- **Modo proyección** (botón o tecla `P`): oculta la interfaz para mapear sobre la tela del cuarto.
- Si playhtml no conecta, la pieza sigue corriendo en solitario.

Es un solo archivo (`index.html`), sin paso de build.

## Probarlo localmente

Abrir `index.html` en el navegador alcanza para ver el campo, pero la sala
colaborativa se comporta raro como archivo local. Mejor servirlo:

```bash
python3 -m http.server 8000
# luego abrir http://localhost:8000
```

## Publicar en GitHub Pages

Este proyecto ya trae un workflow (`.github/workflows/static.yml`) que despliega
solo con cada push a `main`, así que la fuente de Pages es **GitHub Actions** (no
"Deploy from a branch").

1. Subir estos archivos a la raíz de la rama `main` del repo:

   ```bash
   git init
   git add .
   git commit -m "endless echo v2 — campo de e cursivas en puntillismo"
   git branch -M main
   git remote add origin https://github.com/jeseniar/eeeee.git
   git push -u origin main
   ```

2. En el repo: **Settings → Pages**.
3. En *Build and deployment → Source*, elegir **GitHub Actions**.
4. Esperar a que termine el workflow en la pestaña **Actions** (~1 min). La pieza queda en:
   `https://jeseniar.github.io/eeeee/`

Compartí ese link: dos o más personas abriéndolo a la vez se ven los cursores y
los ecos en tiempo real.

## Notas para la sala compartida

- Los **cursores** usan una sala fija (`"endless-echo"`), así la presencia es la
  misma en local, en Pages y en un dominio propio.
- Los **ecos / mensajes / dibujos** se guardan en canales con nombre
  (`ee-echoes`, `ee-messages`, `ee-ink`) y están topados (40 / 18 / 30) para no
  crecer sin fin.
- Es una sala **pública**: cualquiera con el link participa. Para una versión
  privada o moderada habría que montar backend propio (no incluido).

## Próximos pasos

- Reemplazar la fuente de ritmo (viento de Lima) por el **sensor real** del cuarto.
- Layout de **proyección** dedicado.

## Créditos y licencias

- Código de esta pieza: ver `LICENSE` (MIT).
- [p5.js](https://github.com/processing/p5.js) — LGPL-2.1.
- [playhtml](https://github.com/spencerc99/playhtml) — MIT.
- Datos de viento: [Open-Meteo](https://open-meteo.com/) (CC BY 4.0).
- Tipografía: [Space Mono](https://fonts.google.com/specimen/Space+Mono) (OFL).
