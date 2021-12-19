---
hide:
 - toc
# - navigation
title:  Estructuras de datosverticales vs horizontales
---

# Estructuras de datosverticales vs horizontales

- Cuando se diseñan estructuras de datos tabulares es recomendable evitar el crecimiento horizontal de valores.


- Siempre que sea posible es preferible situar las variables o atributos de los datos en las columnas de una tabla y añadir los valores correspondientes a las observaciones de los mismos en las filas.
- El crecimiento horizontal de una estructura de datos tabular puede dificultar su mantenimiento y la confección de visualizaciones.
- Por lo general, es más fácil identificar relaciones entre variables en columnas que entre filas y es más fácil hacer comparaciones entre grupos de observaciones, en filas, que entre grupos de columnas.
- No obstante, esta recomendación debe ajustarse según las necesidades de actualización de los datos:
	- Si es necesario registrar nuevas variables o atributos que no se habían registrado previamente, por ejemplo: una serie temporal, entonces es razonable el crecimiento horizontal de la estructura de datos. es decir, añadir nuevas columnas. Esto permitirá insertar observaciones para las nuevas variables manteniendo valores en blanco en las observaciones previas a la actualización para estas nuevas columnas, si es que no existe un valor asignable a esas observaciones. Al añadir nuevas observaciones, necesariamente tienen que introducirse nuevas filas.

## Ejemplo: crecimiento horizontal vs vertical
<figure markdown> 
  ![Image title](../../imgs/tab.png){ width="auto" }
  <figcaption></figcaption>
</figure>

!!! failure "Mala práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
			<td>
				<p>marca</p>
			</td>
			<td>
				<p>averias_radiador</p>
			</td>
			<td>
				<p>averias_carburador</p>
			</td>
			<td>
				<p>averias_suspension</p>
			</td>
			<td>
				<p>averias_embrague</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>0</p>
			</td>
			<td>
				<p>7</p>
			</td>
			<td>
				<p>1</p>
			</td>
			<td>
				<p>0</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p>1</p>
			</td>
			<td>
				<p>2</p>
			</td>
			<td>
				<p>2</p>
			</td>
			<td>
				<p>2</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p>0</p>
			</td>
			<td>
				<p>4</p>
			</td>
			<td>
				<p>4</p>
			</td>
			<td>
				<p>1</p>
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
				<p>tipo_averia</p>
			</td>
			<td>
				<p>cantidad_averias</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>radiador</p>
			</td>
			<td>
				<p>0</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>carburador</p>
			</td>
			<td>
				<p>7</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>suspensi&oacute;n</p>
			</td>
			<td>
				<p>1</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>embrague</p>
			</td>
			<td>
				<p>0</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p>radiador</p>
			</td>
			<td>
				<p>1</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p>carburador</p>
			</td>
			<td>
				<p>2</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p>suspensi&oacute;n</p>
			</td>
			<td>
				<p>2</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p>embrague</p>
			</td>
			<td>
				<p>2</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p>radiador</p>
			</td>
			<td>
				<p>0</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p>carburador</p>
			</td>
			<td>
				<p>4</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p>suspensi&oacute;n</p>
			</td>
			<td>
				<p>4</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p>embrague</p>
			</td>
			<td>
				<p>1</p>
			</td>
		</tr>
	</tbody>
</table>

En el ejemplo se observa una forma de disponer los datos evitando el crecimiento horizontal de la estructura de datos agregando nuevas variables similares a las existentes. La trasposición a una estructura vertical mediante la creación de dos variables nuevas, “tipo_averia” y “cantidad_averias”, permite añadir fácilmente nuevas observaciones en forma de filas.	

En cambio, cuando se publican series temporales, por ejemplo, el histórico de demanda de vehículos entre los años 1972-1977, es razonable el crecimiento horizontal de la estructura si surge la necesidad, por ejemplo, de completar la serie histórica de los años ‘70.

!!! success "Buena práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
			<td>
				<p>marca</p>
			</td>
			<td>
				<p>1972</p>
			</td>
			<td>
				<p>1973</p>
			</td>
			<td>
				<p>1974</p>
			</td>
			<td>
				<p>1975</p>
			</td>
			<td>
				<p>1976</p>
			</td>
			<td>
				<p>1977</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>345</p>
			</td>
			<td>
				<p>423</p>
			</td>
			<td>
				<p>1234</p>
			</td>
			<td>
				<p>1690</p>
			</td>
			<td>
				<p>2345</p>
			</td>
			<td>
				<p>2134</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p>124</p>
			</td>
			<td>
				<p>252</p>
			</td>
			<td>
				<p>785</p>
			</td>
			<td>
				<p>914</p>
			</td>
			<td>
				<p>1353</p>
			</td>
			<td>
				<p>896</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p>57</p>
			</td>
			<td>
				<p>71</p>
			</td>
			<td>
				<p>165</p>
			</td>
			<td>
				<p>315</p>
			</td>
			<td>
				<p>1104</p>
			</td>
			<td>
				<p>1561</p>
			</td>
		</tr>
	</tbody>
</table>