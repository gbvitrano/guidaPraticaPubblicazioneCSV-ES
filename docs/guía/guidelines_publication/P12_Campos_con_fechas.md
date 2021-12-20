---
hide:
 - toc
# - navigation
title:  Campos con fechas
---

# Campos con fechas

- Codificar las fechas usando un estándar es critico para facilitar el análisis de series temporales de datos. El estándar de referencia en la NTI de reutilización es [ISO 8601](https://es.wikipedia.org/wiki/ISO_8601), que codifica los valores de fecha con el formato YYYY-MM-DD, en su forma abreviada o YYYY-MM-DDTHH:MM:SS, en versión extendida.
	- A tener en cuenta:
		- Recomendaciones en el caso de fechas:
			- Rellenar con ceros los valores de 0-9 para indicar MM, DD, HH, MM y SS, dado que cada valor debe tener un número fijo de dígitos.
			- Usar "-" como separador para fechas y ":" para horas.
			- Usar la letra “T” como carácter separador entre una fecha y una hora cuando se usa la versión extendida.
			- Es preferible usar fechas completas (YYYY-MM-DD) a indicar solo meses o años, siempre que esto sea posible a partir del origen de datos.
			- Si solo se dispone de un dato mensual, la mejor opción es incluir una fecha completa ajustada al ultimo día del mes. Por ejemplo, para Septiembre, 2019-09-30.
			- Si la fecha completa no se puede incluir, es preferible expresar año y mes en columnas separadas. Incluso es razonable incluir una columna para indicar el nombre del mes.
		- Recomendaciones en el caso de horas:
			- Es preferible usar el formato de 24 horas (HH:MM:SS) en vez del formato de 12 horas AM/PM (HH:MM:SS AM/PM).
			- Es preferible usar un campo único para incluir valores que representan fecha y hora combinadas usando el formato YYYY-MM- DDTHH:MM:SS.
	
# Ejemplo 1: campos con fechas (forma abreviada)

!!! failure "Mala práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
				<td>
				<p>marca</p>
			</td>
			<td>
				<p>fecha_lanzamiento</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>Enero de 1970</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p>23/07/1970</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p>1-Febrero-1970</p>
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
				<p>fecha_lanzamiento</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>1970-01-31</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p>1970-07-23</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p>1970-02-01</p>
			</td>
		</tr>
	</tbody>
</table>


# Ejemplo 2: campos con fechas y horas (forma extendida)

!!! failure "Mala práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
				<td>
				<p>Identificador_vehiculo</p>
			</td>
			<td>
				<p>fecha_venta</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>0003407G236</p>
			</td>
			<td>
				<p>12 de Enero de 1970, a las 3:10 de la tarde</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>0003507H003</p>
			</td>
			<td>
				<p>23/07/1970 ? 04:34PM</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>0003407G237</p>
			</td>
			<td>
				<p>1-Febrero-1970-12-23-34</p>
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
				<p>fecha_venta</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>0003407G236</p>
			</td>
			<td>
				<p>1970-01-31T15:10:00</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>0003407G236</p>
			</td>
			<td>
				<p>1970-07-23T16:34:00</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>0003407G236</p>
			</td>
			<td>
				<p>1970-02-01T12:23:34</p>
			</td>
		</tr>
	</tbody>
</table>