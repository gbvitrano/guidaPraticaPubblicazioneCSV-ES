---
hide:
 - toc
# - navigation
title:  P3-Nombrado de columnas
---

# P3-Nombrado de columnas

- Los  nombres  de  los  campos  o  columnas  de  una  tabla  de  datos  deben  ser entendibles por las personas.
- A tener en cuenta:
	- En numerosas ocasiones las columnas de las tablas de datos mantienen los nombres asignados por  los  sistemas de  gestión de bases de datos, normalmente sujetos a convenciones de índole técnico y difícilmente comprensibles para las personas.

	- Algunas recomendaciones para el nombrado de campos:
		- No repetir nombres de campo.
		- Usar nombres cortos (del orden de 20 caracteres) pero siempre teniendo en cuenta que el ahorro de caracteres no debe  inducir malas interpretaciones del nombre del campo.
		- Evitar el uso de abreviaturas.
		- Utilizar solo caracteres ASCII en minúsculas (a-z; 0-9)
		- No usar caracteres especiales (por ejemplo: äüöàéèê, etc.)
		- No incluir tildes ni signos de puntuación.
		- Usar guiones bajos "_" para separar palabras que componen los nombres de columnas en lugar de espacios en blanco.
		- Evitar el uso de códigos, y si fuese absolutamente necesario, debe estar totalmente explicado en el diccionario de datos que documenta el dataset.
		- Los nombres de campo deben coincidir con los especificados en el diccionario de datos.
		
## Ejemplo: nombrado comprensible de columnas	

!!! failure "Mala práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
			<td>
				<p></p>
				<p>Identificador_M</p>
			</td>
			<td>
				<p></p>
				<p>Annio</p>
			</td>
			<td>
				<p></p>
				<p>Cil.</p>
			</td>
			<td>
				<p>Consumo_por_cada_100_k ms_de_recorrido_urbano</p>
			</td>
			<td>
				<p></p>
				<p>HP</p>
			</td>
			<td>
				<p></p>
				<p>m/seg^2</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>1970</p>
			</td>
			<td>
				<p>8</p>
			</td>
			<td>
				<p>18</p>
			</td>
			<td>
				<p>130</p>
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
				<p>1970</p>
			</td>
			<td>
				<p>8</p>
			</td>
			<td>
				<p>15</p>
			</td>
			<td>
				<p>165</p>
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
				<p>1970</p>
			</td>
			<td>
				<p>8</p>
			</td>
			<td>
				<p>18</p>
			</td>
			<td>
				<p>150</p>
			</td>
			<td>
				<p>11</p>
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
				<p>a&ntilde;o</p>
			</td>
			<td>
				<p>cilindros</p>
			</td>
			<td>
				<p>consumo</p>
			</td>
			<td>
				<p>potencia</p>
			</td>
			<td>
				<p>aceleracion</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>1970</p>
			</td>
			<td>
				<p>8</p>
			</td>
			<td>
				<p>18</p>
			</td>
			<td>
				<p>130</p>
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
				<p>1970</p>
			</td>
			<td>
				<p>8</p>
			</td>
			<td>
				<p>15</p>
			</td>
			<td>
				<p>165</p>
			</td>
			<td>
				<p>11,5</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth</p>
				<p>satellite</p>
			</td>
			<td>
				<p>1970</p>
			</td>
			<td>
				<p>8</p>
			</td>
			<td>
				<p>18</p>
			</td>
			<td>
				<p>150</p>
			</td>
			<td>
				<p>11</p>
			</td>
		</tr>
	</tbody>
</table>

- Si existe una entidad que engloba varias características separadas en campos diferentes, es conveniente comenzar nombrando los campos con esa entidad y luego con los atributos más específicos (de lo más general a lo más específico). <br>
**Por ejemplo**:

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
			<td>
				<p>cliente_nombre</p>
			</td>
			<td>
				<p>cliente_cargo</p>
			</td>
			<td>
				<p>solicitante_tipo_documento</p>
			</td>
			<td>
				<p>solicitante_numero_documento</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
			</td>
			<td>
				<p></p>
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

- Los campos que sean identificadores, pueden incluir el sufijo "_id" en el nombre del campo, salvo casos excepcionales donde un nombre alternativo sea más conveniente porque ofrece información sobre el sistema de identificación usado.
- En cuanto a los campos que contengan la descripción de ese identificador, se recomienda que incluyan el sufijo "_nombre", salvo que exista una forma más conveniente de nombrar el campo

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
			<td>
				<p>concesionario_id</p>
			</td>
			<td>
				<p>concesionario_nombre</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
			</td>
			<td>
				<p></p>
			</td>
		</tr>
	</tbody>
</table>