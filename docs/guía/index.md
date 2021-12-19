---
hide:
# - toc
# - navigation
title: Introducción
---

# Introducción

Hoy en día disponemos cada vez de más fuentes de datos a nuestro alcance. Sin embargo, paradójicamente, aun cuando los datos son más asequibles que nunca, las posibilidades de reutilizarlos son bastante limitadas. Los potenciales usuarios de esos datos tienen que hacer frente muchas veces a múltiples barreras que dificultan su acceso y su uso: baja calidad de datos, metadatos escasamente descriptivos y estandarizados, imprecisión de licencias o el uso inadecuado de formatos.

Estas dificultades para reutilizar los datos se mencionan una y otra vez en varios estudios de referencia como el [Open Data Barometer](https://blog.okfn.org/files/2017/06/FinalreportTheStateofOpenGovernmentDatain2017.pdf) o el  [Global OpenData](https://blog.okfn.org/files/2017/06/FinalreportTheStateofOpenGovernmentDatain2017.pdf), y son debidas, en buena parte, al convencimiento inicial de los productores de los datos de que lo importante era publicar la mayor cantidad de información cuanto antes sin importar su calidad.

Como consecuencia, los catálogos de datos publican decenas de miles de datasets con deficiencias de calidad que solo pueden ser identificadas después de comenzar el proceso de reutilización, generando una carga de depuración y preparación en muchos casos inasumible para el usuario de datos abiertos. Este hecho produce frustración y perdida de interés en el sector reutilizador afectando a la credibilidad de las instituciones publicadoras y a rebajar considerablemente las expectativas de retorno y generación de valor a partir de la reutilización de datos abiertos.

Por todo ello, y teniendo en cuenta el estado actual de madurez de las iniciativas de datos abiertos, resulta oportuno fortalecer la mejora de la calidad de los datos que se publican. Se inicia con esta guía la publicación de un compendio de pautas recopiladas con el objetivo de orientar a los publicadores en el uso adecuado de formatos y medios de acceso a datos abiertos. En esta ocasión, el foco es el formato CSV que es el más frecuentemente utilizado en la publicación de datos abiertos.

## ¿Por qué CSV?
-  La forma tabular de los datos es la más habitual en las transferencias e intercambios de información y se produce de múltiples maneras: archivos de datos con columnas delimitadas o campos de longitud fija, hojas de cálculo, tablas HTML, o descargas de tablas de datos SQL, entre otras.
- Se trata del formato más popular y utilizado en el contexto de la reutilización de Datos Abiertos. La mayoría de los recursos disponibles en los catálogos de Datos Abiertos, se encuentran en formato CSV.
- El portal de datos europeo dispone de más de 120 mil conjuntos de datos [en formato CSV, siendo el formato que más abunda en este catálogo de  Datos Abiertos.]
- Por su parte, el catálogo nacional [datos.gob.es] cuenta con casi 14 mil datasets en formato CSV, siendo igualmente, el formato mayoritario.
- Es conciso, fácil de interpretar tanto para personas como para máquinas y adecuado para la estructura natural de la mayoría de los datos. Se caracteriza por [contener datos dispuestos en forma de tablas], donde los campos están individualizados por un carácter separador y los registros por saltos de línea.
- No se requiere ningún software específico para abrir archivos en formato CSV, tan solo es suficiente usar cualquier editor de texto disponible en todos los sistemas operativos.

  [en formato CSV, siendo el formato que más abunda en este catálogo de  Datos Abiertos.]: https://www.europeandataportal.eu/data/datasets?locale=es
  [datos.gob.es]: https://datos.gob.es/es/catalogo
  [contener datos dispuestos en forma de tablas]: https://datos.gob.es/es/documentacion/como-generar-valor-partir-de-los-datos-formatos-tecnicas-y-herramientas-para-analizar%20que%20cataloga%20el%20CSV%20como%20un%20formato%20que%20para%20personas%20y%20para%20m%C3%A1quinas%20(hibrido)

## Pero…

- La simplicidad de CSV tiene como contrapartida que el formato no incluye ningún mecanismo para indicar el tipo de datos que hay en una columna o si los valores de ésta deben ser expresados obligatoriamente. Por lo tanto, es propenso a errores como valores ausentes o a la mezcla de diferentes tipos de datos dentro de una columna.
- La solución a estos problemas radica en la aplicación de buenas prácticas en la fase de preparación de conjuntos de datos, la articulación de medidas de control de calidad y la vinculación del archivo de datos tabulares con esquemas que expresen el modelo de datos por medio de metadatos.


