---
hide:
 - toc
# - navigation
title:  Campos con coordenadas geográficas
---

# Campos con coordenadas geográficas

- El formato más adaptable para representar coordenadas geográficas en mapas es la especificación de latitud y longitud en grados decimales, cuyos valores deben presentarse en columnas separadas, con cabeceras de columna que deben llamarse: Latitud y Longitud, respectivamente.
- A tener en cuenta:
	- Si es necesario especificar el nombre de una entidad de la cual se consignan las coordenadas, se usarán los sufijos “_latitud” y “_longitud”.
	- Se pueden usar conversores de coordenadas UTM o de grados sexagesimales a grados decimales. Por ejemplo: la [herramienta de conversión](http://www.juntadeandalucia.es/economiainnovacioncienciayempleo/pam/ConvED50.action) de la Junta de Andalucía.
	- Para datos geográficos que no sean puntos, por ejemplo: líneas o polígonos, es recomendable seguir especificación [Well-known text representations of coordinate reference systems, (WKT-CRS)](https://www.opengeospatial.org/standards/wkt-crs) del Open Geospatial Consortium.
	- Es aconsejable, siempre que se publiquen datos geográficos, en formatos como por ejemplo [SHP](https://es.wikipedia.org/wiki/Shapefile) o [KML](https://es.wikipedia.org/wiki/KML), acompañar estos archivos de un archivo CSV donde también se incluyan las coordenadas geográficas para facilitar su reutilización.


# Ejemplo: coordenadas geográficas usando notación decimal.




!!! failure "Mala práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
				<td>
				<p>concesionario</p>
			</td>
			<td>
				<p>latitud</p>
			</td>
			<td>
				<p>longitud</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet</p>
			</td>
			<td>
				<p>43&ordm; 14? 04?</p>
			</td>
			<td>
				<p>5&ordm;07?24?</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick</p>
			</td>
			<td>
				<p>43&ordm;20?44?</p>
			</td>
			<td>
				<p>5&ordm;14?14?</p>
			</td>
		</tr>
	</tbody>
</table>
			
!!! success "Buena práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
				<td>
				<p>concesionario</p>
			</td>
			<td>
				<p>latitud</p>
			</td>
			<td>
				<p>longitud</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet</p>
			</td>
			<td>
				<p>43,2345678</p>
			</td>
			<td>
				<p>-5,1234567</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick</p>
			</td>
			<td>
				<p>43,3456789</p>
			</td>
			<td>
				<p>-5,2345678</p>
			</td>
		</tr>
	</tbody>
</table>