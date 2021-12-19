---
hide:
 - toc
# - navigation
title:  Campos de texto
---

# Campos de texto

- Los campos de tipo texto deben incluir cadenas de texto sin espacios en blanco iniciales o finales. Si no es así, los caracteres (espacios o tabuladores) que existan adyacentes a los separadores de campo serán ignorados.
	- A tener en cuenta:
		- Los campos de texto siempre se pueden delimitar con comillas dobles y las aplicaciones que realicen operaciones de lectura de datos analizarán y descartarán tales delimitadores.
		- Si el valor de un campo contiene alguna cadena de texto que presente alguno de los casos siguientes, debe tratarse de la forma indicada:
			- Si los espacios en blanco al principio o final de una cadena de texto son significativos y es necesario preservarlos, el campo debe estar delimitado con comillas dobles.
			- Cadenas que incluyen comas: el campo debe estar delimitado con comillas dobles.
			- Cadenas que incluyen texto entrecomillado: los caracteres de comillas dobles incrustados deben duplicarse y el campo debe delimitarse con comillas dobles.
			- Cadenas que incluyen saltos de línea: los campos deben estar entre comillas dobles.
			
# Ejemplo 1: comportamiento de la exportación de una tabla con valores que contienen espacios en blanco (iniciales o finales). Al exportar la tabla como CSV, los valores en blanco desaparecen.			

<table class="tabella">
  	<tbody>
  		<tr class="arancione_grassetto">
    	<td>
				<p>marca</p>
			</td>
			<td>
				<p>a&ntilde;o</p>
			</td>
			<td>
				<p>cilindros</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>BBBBBBchevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>1970</p>
			</td>
			<td>
				<p></p>
				<p>8</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>BBBBBbuick skylark 320BBBB</p>
			</td>
			<td>
				<p>1970</p>
			</td>
			<td>
				<p>8</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p>1970</p>
			</td>
			<td>
				<p>8</p>
			</td>
		</tr>
	</tbody>
</table>

```
marca,año,cilindros
“chevrolet chevelle malibu",1970,8
”buick skylark 320",1970,8
"plymouth satellite",1970,8
```

# Ejemplo 2: comportamiento de la importación de un archivo CSV con valores que contienen espacios en blanco (iniciales o finales¡) y caracteres entrecomillados.

```
campo1,campo2,campo3
"valor del campo1",
"valor del campo2 con espacios iniciales",
"valor del campo ""3"" que incluye un dato entre comillas"
```
    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
			<td>
				<p>campo1</p>
			</td>
			<td>
				<p>campo2</p>
			</td>
			<td>
				<p>campo3</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>valor del campo1</p>
			</td>
			<td>
				<p>BBBBvalor del campo2 con espacios</p>
				<p>iniciales</p>
			</td>
			<td>
				<p>valor del campo "3" que incluye un dato entre comillas</p>
			</td>
		</tr>
	</tbody>
</table>

En estos ejemplos, se están indicado los espacios en blanco usando el carácter ‘B’ de modo ilustrativo.