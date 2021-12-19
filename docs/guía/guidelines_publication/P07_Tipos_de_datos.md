---
hide:
 - toc
# - navigation
title:  Tipos de datos
---

# Tipos de datos

- Los valores de una tabla de datos deben estar formateados acorde al tipo de datos
de que se trate. Específicamente, los números siempre deben estar en celdas de formato/tipo "número", los campos de tipo textual deben estar en celdas de formato/tipo “texto” y los campos de tipo fecha deben estar en celdas de formato/tipo “fecha”.

<table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
			<td>
				<p>Dato</p>
			</td>
			<td>
				<p>Tipo</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Cadena de caracteres</p>
			</td>
			<td>
				<p>string</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>N&uacute;mero</p>
			</td>
			<td>
				<p>integer, decimal, float, double</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Fecha</p>
			</td>
			<td>
				<p>date, time, datetime, Year, Month, Day</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>binario</p>
			</td>
			<td>
				<p>boolean</p>
			</td>
		</tr>
	</tbody>
</table>

- A tener en cuenta:
	- Mantener el formato correcto de las celdas según el tipo de datos que contengan aumenta las probabilidades de que una exportación a otro formato se realice correctamente y logra que los datos sean más operables en la propia tabla de datos.

# Ejemplo: tipos de datos en tres columnas (string, integer, integer).


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
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>18</p>
			</td>
			<td>
				<p>130 CV</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p>15 litros</p>
			</td>
			<td>
				<p>165</p>
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
				<p>150 CV</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>amc rebel sst</p>
			</td>
			<td>
				<p>16 l.</p>
			</td>
			<td>
				<p>150 CV</p>
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
		</tr>
	</tbody>
</table>		








!!! success "Buena práctica"

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
		</tr>
	</tbody>
</table>

Las buenas prácticas indican que las unidades de medida deben describirse en el diccionario de datos y no en el nombrado de los campos. En última instancia y si se carece de diccionario, es posible indicar la unidad de medida en el nombre del campo, por ejemplo:
”consumo_litros” o “potencia_cv”, siempre y cuando todos los valores de la columna tengan asociada la misma unidad de medida.






















