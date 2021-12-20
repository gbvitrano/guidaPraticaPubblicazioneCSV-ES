---
hide:
 - toc
# - navigation
title:  Campos con direcciones postales
---

# Campos con direcciones postales

- Usar una codificación  precisa de las direcciones  postales  es fundamental para manejar dimensiones geográficas con los datos. Las direcciones postales bien estructuradas pueden ser geolocalizadas, generando las coordenadas de latitud y longitud, usando aplicaciones especificas para ello.
- A tener en cuenta:
	- Si bien existe una norma técnica para el diseño de registros de los ficheros  de intercambio de información referente al Padrón municipal  (INE, Callejero de Censo Electoral), es aconsejable codificar una dirección postal como una cadena de caracteres con los elementos necesarios para localizar un domicilio dentro de una localidad.
	- Estos elementos son:
		- tipo de vía (calle, avenida, plaza, ...)
		- nombre de la vía, número, bloque, planta, letra, etc.
		- localidad (nombre)
		- código postal (5 caracteres numéricos)
	- Siempre que sea posible, es recomendable usar además campos diferenciados para los  valores de  latitud y longitud correspondientes al punto geográfico de la dirección postal.
	
# Ejemplo: codificación de direcciones postales en campos separados.


!!! failure "Mala práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
				<td>
				<p></p>
				<p>Marca</p>
			</td>
			<td>
				<p></p>
				<p>Direcci&oacute;n del Concesionario</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>Calle Automoci&oacute;n, 23, Bajo, Alicante</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>C/ Industria, 33, 33201, Asturias</p>
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
				<p>concesionario_direcci&oacute; n_tipo_via</p>
			</td>
			<td>
				<p></p>
				<p>concesionario_direcc i&oacute;n_mombre_via</p>
			</td>
			<td>
				<p></p>
				<p>concesionario_direcci &oacute;n_localidad</p>
			</td>
			<td>
				<p></p>
				<p>concesionario_direcci &oacute;n_c&oacute;digo_postal</p>
			</td>
		</tr>
		<tr>
			<td>
				<p></p>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p></p>
				<p>Calle</p>
			</td>
			<td>
				<p></p>
				<p>automoci&oacute;n, 23, Bajo</p>
			</td>
			<td>
				<p></p>
				<p>Alicante</p>
			</td>
			<td>
				<p></p>
				<p>03011</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p></p>
				<p>Avenida</p>
			</td>
			<td>
				<p></p>
				<p>industria, 33</p>
			</td>
			<td>
				<p></p>
				<p>Oviedo</p>
			</td>
			<td>
				<p></p>
				<p>33201</p>
			</td>
		</tr>
	</tbody>
</table>