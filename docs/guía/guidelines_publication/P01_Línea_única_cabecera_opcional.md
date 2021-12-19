---
hide:
 - toc
# - navigation
title:  P1 Línea única de cabecera opcional
---
# P1 Línea única de cabecera opcional

Las tablas de datos pueden contener, opcionalmente, una y solo una línea de cabecera para especificar los nombres de los campos.

A tener en cuenta:

- La existencia de múltiples líneas de cabecera, aunque pueden incrementar la interpretación de los datos para las personas por su expresividad y formato, dificultan el procesamiento para  las máquinas, por tanto, cualquier información adicional sobre los datos debe incluirse en la descripción de los mismos utilizando los metadatos apropiados en el Diccionario de Datos.

- **Los nombres de las columnas** que se incluyen en la línea de cabecera son un tipo de anotación o metadato que describe cada columna y **no forma parte de los datos**, es decir, no se debe considerar cuando se cuenta el número de filas de datos en una tabla.

- Para nombrar las columnas se deben usar **celdas simples** y en ningún caso, celdas combinadas.

- Hay que tener en cuenta que no existe un mecanismo para discernir automáticamente si el primer registro de un CSV es una línea de cabecera ya que ésta se codifica como cualquier otro registro. Por tanto, es buena práctica especificar la presencia o ausencia de línea de cabecera, a través del diccionario de datos incluyendo la propiedad  "**`title`**".

- Otra forma de indicar la presencia o ausencia de la línea de cabecera es mediante un parámetro del tipo de contenido cuando el archivo de datos es    tr    smitido     vía     HTTP,     de     la     forma:      **Content-Type: text/csv;header=absent**.


## Ejemplo 1: No usar múltiples celdas de cabecera

!!! failure "Mala práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
    			<td rowspan="1" colspan="3">Datos sobre la de ventas de coches (años 1998 – 1999)</td>
    		</tr>
    		<tr class="arancione_grassetto">
    			<td rowspan="1" colspan="3">Unidades expresadas en miles</td>
    		</tr>
    		<tr class="arancione_grassetto">
    			<td>marca </td>
    			<td>año</td>
    			<td>ventas_por_año</td>
    		</tr>
    		<tr>
    			<td>chevrolet chevelle malibu</td>
    			<td>1998</td>
    			<td>2.5</td>
    		</tr>
    		<tr>
    			<td>chevrolet chevelle malibu</td>
    			<td>1999</td>
    			<td>2.63</td>
    		</tr>
    		<tr>
    			<td>buick skylark 320</td>
    			<td>1998</td>
    			<td>3.4</td>
    		</tr>
    		<tr>
    			<td>buick skylark 320</td>
    			<td>1999</td>
    			<td>3.57</td>
    		</tr>
    	</tbody>
    </table>

!!! success "Buena práctica"

    <table xmlns="http://www.w3.org/1999/xhtml" class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
    			<td>marca</td>
    			<td>año</td>
    			<td>ventas_por_año</td>
    		</tr>
    		<tr>
    			<td>chevrolet chevelle malibu</td>
    			<td>1998</td>
    			<td>2.5</td>
    		</tr>
    		<tr>
    			<td>chevrolet chevelle malibu</td>
    			<td>1999</td>
    			<td>2.63</td>
    		</tr>
    		<tr>
    			<td>buick skylark 320</td>
    			<td>1998</td>
    			<td>3.4</td>
    		</tr>
    		<tr>
    			<td>buick skylark 320</td>
    			<td>1999</td>
    			<td>3.57</td>
    		</tr>
    	</tbody>
    </table>

La información “Datos sobre la de ventas de coches (años 1998 – 1999)” y “Unidades expresadas en miles”, se debe trasladar al diccionario de datos utilizando la propiedad "description`”.

## Ejemplo 2: No usar celdas combinadas


!!! failure "Mala práctica"

    <table xmlns="http://www.w3.org/1999/xhtml" class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
    			<td rowspan="2" colspan="1">marca</td>
    			<td rowspan="1" colspan="2">contacto_concesionario</td>
    		</tr>
    		<tr class="arancione_grassetto">
    			<td>concesionario_mail</td>
    			<td>concesionario_telefono</td>
    		</tr>
    		<tr>
    			<td>chevrolet chevelle malibu</td>
    			<td>mail@concesionario_chevrolet.com</td>
    			<td>+34-1111111</td>
    		</tr>
    		<tr>
    			<td>buick skylark 320</td>
    			<td>mail@concesionario_buick.com</td>
    			<td>+34-2222222</td>
    		</tr>
    	</tbody>
    </table>


!!! success "Buena práctica"

    <table xmlns="http://www.w3.org/1999/xhtml" class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
    			<td>marca</td>
    			<td>contacto_concesionario_mail</td>
    			<td>contacto_concesionario_telefono</td>
    		</tr>
    		<tr>
    			<td>chevrolet chevelle malibu</td>
    			<td>mail@concesionario_chevrolet.com</td>
    			<td>+34-1111111</td>
    		</tr>
    		<tr>
    			<td>buick skylark 320</td>
    			<td>mail@concesionario_buick.com</td>
    			<td>+34-2222222</td>
    		</tr>
    	</tbody>
    </table>

