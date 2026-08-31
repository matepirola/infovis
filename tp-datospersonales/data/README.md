# Datos del trabajo práctico

## Fuente

Los datos provienen de una exportación personal del historial de reproducciones de YouTube realizada mediante Google Takeout.

El historial disponible abarca desde el 16 de enero de 2017 hasta el 30 de agosto de 2026.

## Archivos

### videos_por_mes_y_anio.csv

Este archivo contiene la cantidad de reproducciones registradas agrupadas por mes y año. Es la fuente utilizada para construir la visualización realizada con RAWGraphs.

Campos incluidos:

- Año: año correspondiente al registro agregado.
- Mes: nombre del mes.
- Orden_mes: valor numérico de 1 a 12 utilizado para preservar el orden cronológico.
- Videos: cantidad de reproducciones registradas durante ese mes.
- Cobertura: indica si el período corresponde a cobertura completa o parcial.

## Procesamiento

El procesamiento aplicado fue:

- se conservaron únicamente reproducciones;
- se excluyeron registros identificados como anuncios y otras interacciones automáticas;
- las fechas fueron convertidas a hora local de Argentina;
- las reproducciones fueron agrupadas por mes y año;
- enero de 2017 y agosto de 2026 tienen cobertura parcial.

Después del procesamiento quedaron 30.715 reproducciones consideradas válidas.

## Privacidad

Los archivos originales exportados mediante Google Takeout no se publican porque contienen información privada y permiten reconstruir el historial individual de la cuenta.

El repositorio contiene únicamente datos procesados y agregados utilizados para las visualizaciones.
