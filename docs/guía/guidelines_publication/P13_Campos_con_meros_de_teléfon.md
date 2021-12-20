---
hide:
 - toc
# - navigation
title:  Campos con meros de teléfon
---

# Campos con meros de teléfon

- Cuando se incluyen valores con números de teléfono, lo más importante es asegurar la consistencia en el formato de esos números a lo largo de todos los valores de la columna. Es decir, se podría usar +34-6660000 ó (34)6660000 ó 34-666-00-00, pero siempre el mismo formato.
- A tener en cuenta:
	- Cuando sea necesario incluir más de un número de teléfono como valor de un campo, deberán agregarse nuevos campos.
	- Es recomendable incluir el código de país precediendo al número de teléfono.
	- Para números de teléfono que requieran la inclusión de un número interno, por ejemplo, una extensión, deberá considerarse la inclusión de otro campo de tipo texto, ya que los números de uso interno pueden incluir determinados caracteres. Por ejemplo: "*86", “#36”, etc.

# Ejemplo: tabla con una columna consistente que contiene números de teléfono

!!! failure "Mala práctica"

    <table class="tabella">
    	<tbody>
    		<tr class="arancione_grassetto">
				<td>
				<p>marca</p>
			</td>
			<td>
				<p>concesionario_n&uacute;mero_tel&eacute;fono</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>+34-6760000</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p>(34)6960001</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p>34-676-00-03</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>amc rebel sst</p>
			</td>
			<td>
				<p>346960004</p>
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
				<p>concesionario_n&uacute;mero_tel&eacute;fono</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>chevrolet chevelle malibu</p>
			</td>
			<td>
				<p>+34-6760000</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>buick skylark 320</p>
			</td>
			<td>
				<p>+34-6960001</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>plymouth satellite</p>
			</td>
			<td>
				<p>+34-6760003</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>amc rebel sst</p>
			</td>
			<td>
				<p>+34-6960004</p>
			</td>
		</tr>
	</tbody>
</table>