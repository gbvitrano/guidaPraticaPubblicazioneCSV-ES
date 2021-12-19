---
hide:
 - toc
# - navigation
title:  Estandarización de valores de los campos
---

# Estandarización de valores de los campos

- El uso de valores estandarizados permite la correlación de datos entre conjuntos de datos, la comparación inter-administraciones (entre agencias y/o sectores), la interoperabilidad y el enlazado de datos. Para ello, los valores de determinados campos deben ser consistentes entre datasets.

- A tener en cuenta:
	- Solo es posible saber si una magnitud es grande o pequeña si se puede comparar con otra teniendo en cuenta las similitudes y diferencias, por ejemplo, entre conjuntos de datos originados por diferentes administraciones.
	- La [norma AENOR 137801:2015, Ciudades Inteligentes, Datos Abiertos](http://vocab.linkeddata.es/datosabiertos/), considera datos técnicamente correctos aquellos que, entre otras características:
	- Utilizan la misma codificación y normalización para el mismo tipo de dato publicado en diferentes datasets de un catálogo. Por ejemplo, las direcciones se publican siempre con la misma estructura, tipo, formatos en cualquier conjunto de datos y los elementos de georreferenciación utilizan el mismo sistema de coordenadas de referencia.  
	- La codificación y normalización utilizada se basa en algún estándar común reconocido y utilizado por otras organizaciones codificación. Por ejemplo: estándares aprobados por [EUROSTAT](https://ec.europa.eu/eurostat/ramon/nomenclatures/index.cfm?TargetUrl=LST_NOM_DTL&StrNom=NACE_REV2&StrLanguageCode=ES&IntPcKey=&StrLayoutCode=HIERARCHIC&IntCurrentPage=1) o el [INE](https://www.ine.es/ss/Satellite?L=0&c=Page&cid=1254735839296&p=1254735839296&pagename=MetodologiaYEstandares%2FINELayout).
	- Es recomendable:
		- Usar vocabularios de uso común para normalizar la estructura y valores de la información publicada en los conjuntos de datos.[^1]
		- En el caso de no usar vocabularios de referencia, el valor que se asigne a un determinado atributo debe ser único y coherente en toda utilización de dicho valor a lo largo de la tabla. Es decir, si se opta por usar el valor "Barcelona", para referirse a esta ciudad, no se debe usar el valor “Ciudad de Barcelona”.
[^1]:  La Norma AENOR 137801:2015 incluye una relación de vocabularios de referencia disponibles en: [http://vocab.linkeddata.es/datosabiertos/](http://vocab.linkeddata.es/datosabiertos/)

# Ejemplo: estandarización de la denominación y código de actividad económica.

!!! failure "Mala práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
				<td>
				<p>marca</p>
			</td>
			<td>
				<p>actividad_vendedor</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet</p>
			</td>
			<td>
				<p>Venta de coches</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick</p>
			</td>
			<td>
				<p>Venta de veh&iacute;culos</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth</p>
			</td>
			<td>
				<p>Venta</p>
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
				<p>codigo_vendedor</p>
			</td>
			<td>
				<p>actividad_vendedor</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>chevrolet</p>
			</td>
			<td>
				<p></p>
				<p>45.11</p>
			</td>
			<td>
				<p>Venta de autom&oacute;viles y veh&iacute;culos de motor ligeros</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>buick</p>
			</td>
			<td>
				<p></p>
				<p>45.11</p>
			</td>
			<td>
				<p>Venta de autom&oacute;viles y veh&iacute;culos de motor ligeros</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth</p>
			</td>
			<td>
				<p>45.19</p>
			</td>
			<td>
				<p>Venta de otros veh&iacute;culos de motor</p>
			</td>
		</tr>
	</tbody>
</table>

En este ejemplo, os valores del campo ‘código_vendedor’ son los correspondientes a [la nomenclatura estadística de actividades económicas de la Comunidad Europea](https://ec.europa.eu/eurostat/ramon/nomenclatures/index.cfm?TargetUrl=LST_NOM_DTL&amp;StrNom=NACE_REV2&amp;StrLanguageCode=ES&amp;IntPcKey&amp;StrLayoutCode=HIERARCHIC&amp;IntCurrentPage=1) (NACE, Rev. 2) de EUROSTAT para la estandarización de las actividades económicas de los vendedores de vehículos.			
