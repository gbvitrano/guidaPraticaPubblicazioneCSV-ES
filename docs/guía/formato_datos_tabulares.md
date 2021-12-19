---
hide:
# - toc
# - navigation
title: Formato de Datos tabulares
---

# Formato de Datos tabulares

Los conjuntos de **datos tabulares** bien organizados se ajustan a un esquema predefinido, son fáciles de manipular, modelar y visualizar, y tienen una estructura específica basada en las siguientes reglas:

- Cada variable es una **columna**.
- Cada observación o registro es una **fila**.
- Cada intersección de fila y columna es una **celda**.
- Cada conjunto de observaciones es una **tabla**.

!!! example "Características de coches clásicos"

    | marca | año | cilindros | consumo | potencia | aceleracion |
    | --- | --- | --- | --- | --- | --- |
    | chevrolet chevelle malibu | 1970 | 8 | 18 | 130 | 12 |
    | buick skylark 320 | 1970 | 8 | 15 | 165 | 11.5 |
    | plymouth satellite | 1970 | 8 | 18 | 150 | 11 |
    | amc rebel sst | 1970 | 8 | 16 | 150 | 12 |
    | ford torino | 1970 | 8 | 17 | 140 | 10.5 |

Aunque no hay un estándar oficial para el formato de “valores separados por comas” (CSV, por sus siglas en inglés), el Internet Engineering Task Force (IETF) publica el documento de referencia [RFC4180](https://tools.ietf.org/html/rfc4180).

## Características fundamentales

- Cada archivo debe contener una sola tabla de datos.
- Cada registro o fila es una línea.
- Todos los registros contienen el mismo número de campos o columnas, al menos una.
- Opcionalmente, puede haber una primera línea de cabecera que contiene exclusivamente los nombres de los campos.
- Las  celdas  de  una  misma  columna  proporcionan  valores  para  la  misma propiedad de las observaciones descritas en cada fila.
- Todos los valores de una misma columna deben ser del mismo tipo de datos (texto, enteros, decimales, fecha, etc.)
- Cada campo está separado del siguiente por un carácter singular: por ejemplo, una coma `,`, un punto y coma `;`, un carácter pipe `|` o un carácter tabulador `TAB`.
- Cuando los campos están separados por un carácter tabulador `TAB`, el formato de archivo es [**TSV**](https://www.iana.org/assignments/media-types/text/tab-separated-values).
- Alternativamente, los campos pueden tener una longitud fija de caracteres.
- Los valores de los campos que incluyen comillas, comas o retornos de carro deben ir entre comillas.
- Los archivos en formato CSV deben utilizar la codificación de caracteres UTF-8.
- Respecto a los nombres de los archivos, es recomendable utilizar minúsculas con los caracteres de la a-z, los dígitos 0-9 y carácter guion bajo (`_`) en lugar de espacios en blanco, para asegurar el procesamiento correcto de nombres de archivo tanto en servidores como en aplicaciones cliente.
- Cualquier información que no sea valores de datos, como metadatos, descripciones, comentarios o unidades de medida, deben indicarse de forma anexa al archivo de datos en forma de diccionario de datos.

## Ejemplo de archivo CSV

```
marca,año,cilindros,consumo,potencia,aceleración
chevrolet chevelle malibu,1970,8,18,130,12
buick skylark 320,1970,8,15,165,11.5
plymouth satellite,1970,8,18,150,11
amc rebel sst,1970,8,16,150,12
ford torino,1970,8,17,140,10.5
```
