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

- **Caso 1**:  **Importación de un CSV** con valores de campos que incluyen espacios en blanco entrecomillados y separados por `,`

```
marca,año,cilindros
"chevrolet chevelle malibu",1970,8
"buick skylark 320",1970,8
"plymouth satellite",1970,8
```

<table  class="tabella" xmlns="http://www.w3.org/1999/xhtml">
	<tbody>
		<tr class="arancione">
			<td>marca</td>
			<td>a&ntilde;o</td>
			<td>cilindros</td>
		</tr>
		<tr>
			<td>chevrolet chevelle malibu</td>
			<td>1970</td>
			<td>8</td>
		</tr>
		<tr>
			<td>buick skylark 320</td>
			<td>1970</td>
			<td>8</td>
		</tr>
		<tr>
			<td>plymouth satellite</td>
			<td>1970</td>
			<td>8</td>
		</tr>
	</tbody>
</table>


- **Caso 2**:	Importación de un CSV con valores de campos que incluyen espacios en blanco y un carácter CR no entrecomillados.

```
marca,año,cilindros
chevrolet chevelleCRmalibu,1970,8 buick skylark 320,1970,8
plymouth satellite,1970,8
```

<table class="tabella" xmlns="http://www.w3.org/1999/xhtml">
	<tbody>
		<tr class="arancione">
			<td>marca</td>
			<td>a&ntilde;o</td>
			<td>cilindros</td>
		</tr>
		<tr>
			<td>chevrolet chevelle</td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>malibu</td>
			<td>1970</td>
			<td>8</td>
		</tr>
		<tr>
			<td>buick skylark 320</td>
			<td>1970</td>
			<td>8</td>
		</tr>
		<tr>
			<td>lymo th ellite</td>
			<td>1970</td>
			<td>8</td>
		</tr>
	</tbody>
</table>

En el ejemplo anterior se están incluyendo el carácter de control de retorno de carro (CR) a modo ilustrativo. Tanto el carácter ‘CR’ como ‘LF’ no son visibles

## Ejemplo 2: Comportamiento de la exportación de una tabla con campos que incluyen espacios en blanco o saltos de línea dentro de sus valores.

El **CSV** que se genera a partir de la tabla debe incluir el valor de cada campo entre comillas, incluyendo los caracteres de control, en un registro único.

<table class="tabella">
	<tbody>
		<tr class="arancione">
			<td>
				<p>campo_1</p>
			</td>
			<td>
				<p>campo_2</p>
			</td>
			<td>
				<p>campo_3</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>aaaaa</p>
			</td>
			<td>
				<p>Bbbb Bbb Bbbb</p>
				<p>Bb</p>
			</td>
			<td>
				<p></p>
				<p>ccccc</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Aa aa</p>
			</td>
			<td>
				<p>Bb,bb</p>
			</td>
			<td>
				<p>c</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Aaa aaaaaa</p>
			</td>
			<td>
				<p>Bbbbb bbb bb</p>
			</td>
			<td>
				<p>Ccc ccccc</p>
			</td>
		</tr>
	</tbody>
</table>

```
campo_1,campo_2,campo_3CRLF
"aaaaa", "BbbbCRLFBbbCRLFBbbbCRLFbb","ccccc"CRLF
“Aa aa”,” bb,bb”,”c”CRLF
“AaaCRLFaaaaaa”,” Bbbbb bbb bb”,” CccCRLFccccc”LF
```

Se están incluyendo los caracteres de control de fin de línea (LF) y retorno de carro (CR) a modo ilustrativo, dado que éstos no son visibles.