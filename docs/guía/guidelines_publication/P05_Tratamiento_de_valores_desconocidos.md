---
hide:
 - toc
# - navigation
title:  Tratamiento de valores desconocidos
---

# Tratamiento de valores desconocidos

- Los valores de los datos deben ser completos y deben estar expresados de forma precisa y coherente con el tipo de datos del campo para que puedan ser procesados en función de su valor real.
- Como norma general, hay que rellenar todas las celdas de una tabla y mantener un código común para los datos desconocidos.
- A tener en cuenta:
	- Los valores desconocidos, cuando se dejan sin explicar o simplemente están ausentes, suelen generar confusión, especialmente cuando la columna de datos es numérica. Por otro lado, generan resultados erróneos en tareas de ordenación.
	- Recomendaciones para evitar valores de datos desconocidos:
		- Si la celda en blanco representa un cero, entonces el valor debe ser 0.
		- Si la celda en blanco representa un valor "desconocido" o "no obtenido", entonces esta posibilidad debe explicarse en el diccionario de datos e indicarse con un código específico.
		- Si un valor en blanco tiene un significado, se debe valorar la opción de añadir una nueva columna para incluir la explicación del valor "en blanco" como un valor posible.
		- Una terminología aceptada para indicar valores desconocidos o ausentes es el valor o código específico NA o N/A.[^1]
		- El código que se utilice para indicar los valores desconocidos o ausentes, por ejemplo NA, debe especificarse en el diccionario de atos

## Ejemplo 1: Ventas de coches por año (en miles).

!!! failure "Mala práctica"

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
				<p>consumo</p>
			</td>
			<td>
				<p></p>
				<p>ventas</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
				<p>Alto</p>
			</td>
			<td>
				<p></p>
				<p>2,50</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>Bajo</p>
			</td>
			<td>
				<p></p>
				<p>2,63</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>Medio</p>
			</td>
			<td>
				<p></p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
			</td>
			<td>
				<p></p>
				<p>3,40</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>Medio</p>
			</td>
			<td>
				<p></p>
				<p>3,57</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>Medio</p>
			</td>
			<td>
				<p></p>
				<p>N/A</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
			</td>
			<td>
				<p></p>
				<p>2,40</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
			</td>
			<td>
				<p></p>
				<p>2,52</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>Alto</p>
			</td>
			<td>
				<p></p>
				<p>3,60</p>
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
				<p>consumo</p>
			</td>
			<td>
				<p></p>
				<p>ventas</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
				<p>Alto</p>
			</td>
			<td>
				<p></p>
				<p>2,50</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>Bajo</p>
			</td>
			<td>
				<p></p>
				<p>2,63</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>Medio</p>
			</td>
			<td>
				<p></p>
				<p>0</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
				<p>NA</p>
			</td>
			<td>
				<p></p>
				<p>3,40</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>Medio</p>
			</td>
			<td>
				<p></p>
				<p>3,57</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>Medio</p>
			</td>
			<td>
				<p></p>
				<p>NA</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
				<p>NA</p>
			</td>
			<td>
				<p></p>
				<p>2,40</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>NA</p>
			</td>
			<td>
				<p></p>
				<p>2,52</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>Alto</p>
			</td>
			<td>
				<p></p>
				<p>3,60</p>
			</td>
		</tr>
	</tbody>
</table>			
			

En el ejemplo se observa que el valor 0 en la columna “ventas” indica que para ese año las ventas de coches de ese modelo han sido 0. En cambio, cuando el dato de “ventas”, al igual que el de “consumo” se desconoce, se indica con NA. Todos los valores desconocidos en cualquier columna se indican con el mismo código: NA.

## Ejemplo 2: Ventas de coches por año (en miles).

!!! failure "Mala práctica"

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
				<p>consumo</p>
			</td>
			<td>
				<p></p>
				<p>ventas</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
				<p>Alto</p>
			</td>
			<td>
				<p></p>
				<p>2,50</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>Bajo</p>
			</td>
			<td>
				<p></p>
				<p>2,63</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>Medio</p>
			</td>
			<td>
				<p></p>
				<p>3,75</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
				<p>NA</p>
			</td>
			<td>
				<p></p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>Medio</p>
			</td>
			<td>
				<p></p>
				<p>3,57</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>Medio</p>
			</td>
			<td>
				<p></p>
				<p>5,10</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
				<p>NA</p>
			</td>
			<td>
				<p></p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>NA</p>
			</td>
			<td>
				<p></p>
				<p>2,52</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>Alto</p>
			</td>
			<td>
				<p></p>
				<p>3,60</p>
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
				<p>consumo</p>
			</td>
			<td>
				<p></p>
				<p>ventas</p>
			</td>
			<td>
				<p>Significado valor ausente ventas</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
				<p>Alto</p>
			</td>
			<td>
				<p></p>
				<p>2,50</p>
			</td>
			<td>
				<p></p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>1999</p>
			</td>
			<td>
				<p></p>
				<p>Bajo</p>
			</td>
			<td>
				<p></p>
				<p>2,63</p>
			</td>
			<td>
				<p></p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>2000</p>
			</td>
			<td>
				<p></p>
				<p>Medio</p>
			</td>
			<td>
				<p></p>
				<p>3,75</p>
			</td>
			<td>
				<p></p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>1998</p>
			</td>
			<td>
				<p></p>
				<p>NA</p>
			</td>
			<td>
				<p></p>
			</td>
			<td>
				<p></p>
			</td>
		</tr>
	</tbody>
</table>

En el ejemplo se añade una nueva columna para explicar el significado del valor ausente en la columna “ventas”. <br><br>
Hay circunstancias en las que no se pueden registrar determinadas medidas, porque los aparatos o sistemas que se utilizan para medir determinadas magnitudes solo registran valores a partir de un determinado umbral (por ejemplo, un sensor de contaminación ambiental). En esos casos, se explicará en el diccionario de datos y se indicará en la tabla con un código común

		
		
[^1]: Del inglés, not available (no disponible), not applicable (no corresponde en el caso) o no answer (sin respuesta; aunque este significado solo se usa en ciertas situaciones). [https://es.wikipedia.org/wiki/N/a](https://es.wikipedia.org/wiki/N/a)




