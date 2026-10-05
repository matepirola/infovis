# Mi historial de YouTube

Trabajo final de Visualización de Datos Personales para Infovis. La página recorre el historial personal de YouTube de Mateo Pirola Paulovich entre enero de 2017 y agosto de 2026 mediante cuatro preguntas sobre publicidad, suscripciones, concentración del consumo y duración de los videos.

Sitio publicado: <https://matepirola.github.io/infovis/tp-datospersonales/>

## Fuente y alcance

- Fuente principal: historial de reproducciones exportado mediante Google Takeout.
- Período: enero de 2017 a agosto de 2026; ambos extremos son parciales.
- Base limpia: 30.715 reproducciones.
- Aproximadamente 27.010 reproducciones tienen un canal identificable.
- YouTube Data API v3 recuperó duración para aproximadamente 27.007 reproducciones.

La lista de suscripciones representa el estado al momento de la exportación en 2026. No permite reconstruir la fecha histórica de cada suscripción.

## Visualizaciones

1. **Publicidad** — eventos publicitarios registrados por cada 100 reproducciones, publicado con Datawrapper.
2. **Suscripciones** — coincidencia mensual entre el consumo histórico y los canales seguidos actualmente, publicado con Flourish.
3. **Concentración** — distribución anual (2017–2026, barras apiladas al 100%) del consumo entre el canal más visto, los canales 2–5, los canales 6–10 y el resto, con el ranking recalculado para cada año; publicado con Tableau Public. 2017 y 2026 son parciales.
4. **Duración** — composición porcentual anual por rango de duración, creado con RAWGraphs y publicado como SVG.

## Herramientas

- Google Takeout para obtener el historial personal.
- YouTube Data API v3 para enriquecer los videos con duración.
- Datawrapper para la visualización de publicidad.
- Flourish para suscripciones.
- Tableau Public para la concentración anual del consumo.
- RAWGraphs para la distribución anual de duración (SVG insertado con `<object>`).
- HTML, CSS y JavaScript vanilla para la experiencia editorial.

## Procesamiento y limitaciones

Se consideraron reproducciones reales identificadas mediante registros cuyo título comenzaba con “Has visto”. Los eventos identificados como publicidad se excluyeron de la base de reproducciones limpias.

Los eventos publicitarios registrados por Takeout no equivalen necesariamente a cortes completos. La duración informada por la API corresponde al contenido y no al tiempo efectivamente visto. Algunos videos no pudieron enriquecerse porque fueron eliminados, pasaron a ser privados o dejaron de estar disponibles. Las relaciones visuales no implican causalidad.

## Privacidad

Los JSON originales de Google Takeout, credenciales y claves de API no se publican. El repositorio incluye únicamente archivos necesarios para el sitio y datos procesados o agregados aptos para compartir.

## Estructura

```text
tp-datospersonales/
├── index.html
├── styles.css
├── script.js
├── README.md
├── assets/
│   ├── favicon.svg
│   └── stacked.svg
└── data/
    ├── README.md
    └── videos_por_mes_y_anio.csv
```

El archivo `youtube_mes_anio_editado.svg` se conserva como material previo, pero no forma parte de la narrativa final de cuatro visualizaciones.

## Cómo abrir el proyecto

No requiere instalación, compilación ni dependencias del proyecto. Como los gráficos externos no siempre se cargan desde una URL `file://`, la vista local debe abrirse mediante un servidor HTTP estático. Por ejemplo, desde la raíz del repositorio:

```bash
python3 -m http.server 8000
```

Luego abrir <http://localhost:8000/tp-datospersonales/>. GitHub Pages ya sirve el sitio por HTTP y no requiere este paso.

Los embeds de Datawrapper y Flourish requieren conexión a internet. El gráfico de duración es local y se carga desde `assets/stacked.svg`.
