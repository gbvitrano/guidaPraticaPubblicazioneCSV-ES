---
hide:
 - toc
# - navigation
title:  Campos codificados
---

# Campos codificados

- Referenciar correctamente esquemas de conceptos, es decir, listas  de  códigos (code lists) y taxonomías de términos como valores prescritos para propiedades o atributos definidos.
- A tener en cuenta:
	- Son muy útiles para realizar análisis de datos categorizados (por ejemplo: para extraer patrones, realizar filtrados, sumarios, ordenaciones, etc.), pero pueden ser difíciles de interpretar para personas no familiarizadas con tales codificaciones, si no están explicados con precisión en el propio conjunto de datos o por medio del Diccionario de Datos.
	- El anexo I de esta guía recoge una reseña de términos reutilizables que incluye taxonomías, clasificaciones y estándares armonizados a nivel nacional e internacional.
	- Si es posible, se debe añadir una columna incluyendo el valor estándar del atributo en cuestión. Por ejemplo. si el campo se refiere a Ayuntamientos, es aconsejable mantener dos columnas: "Código Ayuntamiento" y "Ayuntamiento". El Código será el referido en el "Directorio Común de Unidades Orgánicas y Oficinas" (DIR3) y el valor de la columna "Ayuntamiento", el nombre de esa institución.
	- En línea con lo anterior, no se debe incluir el nombre del campo dentro del valor de campo. Por ejemplo, si el nombre de la columna es "Ayuntamiento" el valor en cada fila no debe incluir las palabras "Ayuntamiento de".

# Ejemplo: uso de campos codificados

!!! failure "Mala práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
			<td>
				<p>marca</p>
			</td>
			<td>
				<p>consumo</p>
			</td>
			<td>
				<p>potencia</p>
			</td>
			<td>
				<p>cambio</p>
			</td>
			<td>
				<p>aceleraci&oacute;n</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>18</p>
			</td>
			<td>
				<p>130</p>
			</td>
			<td>
				<p>M</p>
			</td>
			<td>
				<p>12</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p>15</p>
			</td>
			<td>
				<p>165</p>
			</td>
			<td>
				<p>A</p>
			</td>
			<td>
				<p>11,5</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p>18</p>
			</td>
			<td>
				<p>150</p>
			</td>
			<td>
				<p>A</p>
			</td>
			<td>
				<p>11</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>amc rebel sst</p>
			</td>
			<td>
				<p>16</p>
			</td>
			<td>
				<p>150</p>
			</td>
			<td>
				<p>M</p>
			</td>
			<td>
				<p>12</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>ford torino</p>
			</td>
			<td>
				<p>17</p>
			</td>
			<td>
				<p>140</p>
			</td>
			<td>
				<p>M</p>
			</td>
			<td>
				<p>10,5</p>
			</td>
		</tr>
	</tbody>
</table>

!!! success "Buena práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
			<td>
				<p></p>
				<p>marca</p>
			</td>
			<td>
				<p></p>
				<p>consumo</p>
			</td>
			<td>
				<p></p>
				<p>potencia</p>
			</td>
			<td>
				<p></p>
				<p>cambio</p>
			</td>
			<td>
				<p>cambio- descripci&oacute;n</p>
			</td>
			<td>
				<p></p>
				<p>aceleracion</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>18</p>
			</td>
			<td>
				<p></p>
				<p>130</p>
			</td>
			<td>
				<p></p>
				<p>M</p>
			</td>
			<td>
				<p></p>
				<p>Manual</p>
			</td>
			<td>
				<p></p>
				<p>12</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>15</p>
			</td>
			<td>
				<p></p>
				<p>165</p>
			</td>
			<td>
				<p></p>
				<p>A</p>
			</td>
			<td>
				<p></p>
				<p>Autom&aacute;tico</p>
			</td>
			<td>
				<p></p>
				<p>11,5</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>18</p>
			</td>
			<td>
				<p></p>
				<p>150</p>
			</td>
			<td>
				<p></p>
				<p>A</p>
			</td>
			<td>
				<p></p>
				<p>Autom&aacute;tico</p>
			</td>
			<td>
				<p></p>
				<p>11</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>amc rebel sst</p>
			</td>
			<td>
				<p></p>
				<p>16</p>
			</td>
			<td>
				<p></p>
				<p>150</p>
			</td>
			<td>
				<p></p>
				<p>M</p>
			</td>
			<td>
				<p></p>
				<p>Manual</p>
			</td>
			<td>
				<p></p>
				<p>12</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>ford torino</p>
			</td>
			<td>
				<p></p>
				<p>17</p>
			</td>
			<td>
				<p></p>
				<p>140</p>
			</td>
			<td>
				<p></p>
				<p>M</p>
			</td>
			<td>
				<p></p>
				<p>Manual</p>
			</td>
			<td>
				<p></p>
				<p>10,5</p>
			</td>
		</tr>
	</tbody>
</table>