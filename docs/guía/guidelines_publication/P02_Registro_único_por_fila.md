---
hide:
 - toc
# - navigation
title:  P2 Registro único por fila
---
# P2 Registro único por fila

- Las tablas de datos contienen observaciones sobre los datos y cada observación o registro de datos debe ocupar una fila. En cada registro debe haber exactamente el mismo número de campos.

- A tener en cuenta:
	- Cada registro o fila está marcado por una secuencia de uno o más caracteres invisibles denominados carácter de control, concretamente el retorno de carro (CR, carriage return) y salto de línea (LF, line feed). Desafortunadamente, los sistemas operativos representan los finales de línea usando diferentes secuencias:
	
	- Todas las versiones de DOS / Microsoft Windows representan finales de línea como CR seguidos de LF, es decir, CRLF o lo que es lo mismo ("\r\n").

	- Los sistemas operativos UNIX y similares, incluido  MacOS, representan las terminaciones de línea como LF o lo que es lo mismo ("\n").

- El documento de referencia RFC4180 para datos en formato CSV, define que las filas deben ser terminadas con los caracteres de control CRLF. Por tanto, es importante saber que  esta cuestión puede generar algún problema  cuando se intercambian, importan o exportan, archivos CSV con origen en diferentes sistemas operativos.

- La existencia de caracteres de retorno de carro [CR] dentro del valor de un campo, por ejemplo, campos que contienen múltiples líneas o comentarios, deben  ir siemp    entre  omillas dob    

## Ejemplo  1:  Comportamiento  de  una  importación  de  un  archivo  CSV  que  contiene espacios en blanco y/o retornos de carro en varias circunstancias.

- Caso 1:  Importación de un CSV con valores de campos que incluyen espacios en blanco entrecomillados y separados por `,`

```
marca,año,cilindros
"chevrolet chevelle malibu",1970,8
"buick skylark 320",1970,8
"plymouth satellite",1970,8

```
