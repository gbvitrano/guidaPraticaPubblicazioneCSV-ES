---
hide:
 - toc
# - navigation
title:  Subtotales, totales o agrupamientos
---

# Subtotales, totales o agrupamientos

- No se deben incluir filas o columnas de totales o subtotales, a menos que sea absolutamente necesario, manteniendo el máximo nivel de desagregación de datos posible.
- A tener en cuenta:
	- Un archivo que contiene resultados y/o operaciones realizadas con los datos no se puede considerar un archivo de datos en sentido estricto, sino un archivo de resultados de un determinado análisis de datos.
	- Cuando se incluyen filas o columnas con valores de datos agregados por ejemplo como resultado de una operación, resulta muy difícil y en ocasiones imposible recuperar el dato desagregado.
	- Un dataset debe ser consistente en el nivel de granularidad de los datos que contiene. Si el nivel de granularidad se establece según una determinada dimensión, por ejemplo: ventas mensuales, no se deben mezclar datos con otro nivel de granularidad, por ejemplo, ventas anuales.
	- Un nivel de granularidad superior siempre se puede obtener a partir de un nivel inferior, pero no a la inversa. Siguiendo el ejemplo, es posible obtener las ventas anuales a partir de los datos de ventas mensuales, pero no es posible recuperar los datos de ventas mensuales a partir de las ventas anuales.
	- Se debe evitar el agrupamiento de filas relacionadas con una entidad dejando ciertas celdas vacías repitiendo la entidad para todas las filas del agrupamiento. Este problema es común y puede ocasionar problemas cuando se modifica el orden original de las filas.

# Ejemplo 1: Venta semestral de coches (en miles), con subtotales (mezcla de niveles de granularidad) y sin subtotales (mismo nivel de granularidad).	

!!! failure "Mala práctica"

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
				<p>ventas_semestrales</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
				<p>2,5</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
				<p>2,63</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>Subtotal anual</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>5,13</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>3,4</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>3,57</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>Subtotal anual</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>6,97</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>2,4</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>2,52</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>Subtotal anual</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>4,92</p>
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
				<p>a&ntilde;o</p>
			</td>
			<td>
				<p></p>
				<p>ventas_s1</p>
			</td>
			<td>
				<p></p>
				<p>ventas_s2</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
				<p>2,5</p>
			</td>
			<td>
				<p></p>
				<p>2,63</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>3,4</p>
			</td>
			<td>
				<p></p>
				<p>3,57</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>2,4</p>
			</td>
			<td>
				<p></p>
				<p>2,52</p>
			</td>
		</tr>
	</tbody>
</table>

# Ejemplo 2: No usar agrupamientos en base al uso de celdas vacías.