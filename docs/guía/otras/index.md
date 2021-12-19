---
hide:
# - toc
# - navigation
title: Otras consideraciones sobre archivos CSV
---

# Otras consideraciones sobre archivos CSV

- El tipo MIME más apropiado para denotar el tipo de contenido de los archivos CSV transmitidos por Internet se indica mediante el siguiente valor de la propiedad
Content-Type:

	**Content-Type: text/csv**
	
- También, aunque menos habitual, se puede expresar utilizando:

	**Content-Type: application/octet-stream**
	**Content-Type: text/comma-separated-values**

- Como se ha indicado, es recomendable codificar los archivos CSV utilizando UTF-8, si se utiliza otro tipo de encoding puede especificarse a través del parámetro charset en la cabecera Content-Type. Por ejemplo:

	**Content-Type: text/csv;charset=ISO-8859-1**
	
- Si un archivo CSV no contiene línea de cabecera es posible indicarlo usando el parámetro header del tipo MIME. Por ejemplo:

	**Content-Type: text/csv;header=absent**
	
-  La implementación de estas propiedades ayudan a procesar los archivos CSV automáticamente y de forma consistente.
	