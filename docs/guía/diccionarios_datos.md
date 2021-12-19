---
hide:
#   - navigation
title: Diccionarios de Datos
---

# Diccionarios de Datos

- El diccionario de datos es un complemento esencial de cualquier conjunto de datos ya que aporta al usuario de los datos información suficiente para procesar y comprender su contenido sin ambigüedad.
- Su propósito es garantizar que la estructura del conjunto de datos se define en términos fácilmente entendibles por los usuarios.
- Cada conjunto de datos publicable debe incluir su diccionario de datos como un documento separado, accesible normalmente mediante una URL desde el punto de descarga del archivo de datos.
- El contenido de un Diccionario de Datos puede ser expresado de diferentes formas, incluso como un archivo de texto que describe el contenido de cada columna del dataset.
- Las características o anotaciones que se expresan en el Diccionario de Datos son las propiedades de las tablas, columnas, filas y celdas que componen el conjunto de datos.
- A continuación, se expone un ejemplo de diccionario de datos expresado como un archivo de texto que puede ser suministrado a través de un servidor Web. Por ejemplo, a través de la URL: [example.org/automoviles.csv-metadata.txt](http://example.org/automoviles.csv-metadata.txt).

## Ejemplo de diccionario de datos expresado como un archivo de texto

```
Archivo de datos: http://example.org/automoviles.csv Descripción: Tabla con datos de automóviles clásicos Publicador: Autor del ejemplo
Columna 1:
	Titulo: marca
	Descripción: Este campo contiene información sobre la marca y modelo de cada vehículo.
	Tipo de datos: string
Columna 2:
	Titulo: año
	Descripción: Este campo contiene información sobre el año de fabricación de cada vehículo.
	Tipo de datos: date 
Columna 3:
	Titulo: cilindros
	Descripción: Este campo contiene información sobre el número de
	cilindros de cada vehículo.
	Tipo de datos: integer 
Columna 4:
	Título: consumo
	Descripción: Este campo contiene información sobre el consumo medio de cada vehículo, medido en litros / 100 kms.
	Tipo de datos: decimal 
Columna 5:
	Título: potencia
	Descripción: Este campo contiene información sobre la potencia de cada vehículo, medida en CV.
	Tipo de datos: decimal
Columna 6:
1
```

- Una buena práctica es que el Diccionario de Datos se exprese en un formato procesable, por ejemplo, [JSON](https://www.w3schools.com/js/js_json_intro.asp) o [JSON-LD](https://www.w3.org/TR/json-ld11/), mediante un vocabulario estandarizado que permita definir cada una de las características o anotaciones sobre cada uno de
los elementos del archivo de datos.
- En algunas plataformas de Datos Abiertos, por ejemplo, las implementadas con [CKAN](https://ckan.org/), se especifica el Diccionario de Datos como una sección asociada a cada recurso de un dataset.
- Según la [Norma Técnica de Interoperabilidad de Recursos de Información (NTI)](https://datos.gob.es/es/documentacion/norma-tecnica-de-interoperabilidad-de-reutilizacion-de-recursos-de-informacion), la forma de especificar el modelo de datos es utilizando la propiedad "`dct:relation`" en los metadatos de la distribución de los recursos del dataset.
- Para ajustar los valores de las propiedades es recomendable utilizar un lenguaje claro y conciso, dado que los usuarios finales de los datos no tienen porqué estar familiarizados con los datos.
- W3C recomienda un [modelo para datos tabulares](https://www.w3.org/TR/tabular-data-model/) y propone un vocabulario para la descripción de estas propiedades.
- El vocabulario de W3C es muy exhaustivo, no obstante, hay una serie de propiedades que es recomendable tener en cuenta para cualquier archivo tabular:

	- Para las tablas:
		- Título de tabla `["dc:title"]`
		- Descripción `["dc:description"]`
		- Publicador `["dc:creator"]`
		- Ubicación del archivo que se describe `["url"]`

	- Para las columnas:
		- Nombre de columna `["name"]`
		- Título de columna `["titoli"]`
		- Descripción `["dc:description"]`
		- Tipos de datos: `["datatype"]`

- Además, es posible anotar por medio del uso de diferentes propiedades, entre otros metadatos, los siguientes: orden de columnas, valores esperados, valores requeridos, valores únicos, claves externas, listas de valores, idiomas de las cadenas, formatos, restricciones, validaciones, instrucciones para la transformación del CSV a otro formato.
- A continuación, se expone un ejemplo de diccionario de datos expresado como un esquema en formato JSON que puede ser suministrado a través de un servidor Web. Por ejemplo, a través de la URL: [example.org/automoviles.csv-metadata.json](http://example.org/automoviles.csv-metadata.json).

## Ejemplo de diccionario de datos utilizando el formato json-ld

```json
{ 
"@context": "http://www.w3.org/ns/csvw", 
"@type": "Table", 
"url": "http://example.org/automoviles.csv", 
“dc:description”: “Tabla con datos de automóviles clásicos”
“dc:creator”: “Autor del ejemplo”
"tableSchema": { 
"columns": [{ 
"name": ”identificador", 
"titles": ”marca", 
”dc:description”: “Este campo contiene información sobre 
la marca y modelo de cada vehículo”
"datatype": "string" },
{ "name": ”annio", 
"titles": ”año", 
”dc:description”: “Este campo contiene información sobre 
el año de fabricación de cada vehículo”
"datatype": {
“base”: ”date" ,
“format”: “yyyy”}},
{ "name": ”cilindros", 
"titles": cilindros", 
”dc:description”: “Este campo contiene información sobre 
el número de cilindros de cada vehículo”
"datatype": ”integer" },
{ "name": ”consumo", 
"titles": ”consumo", 
”dc:description”: “Este campo contiene información sobre 
el consumo medio de cada vehículo, medido en litros / 
100 kms.”
"datatype": ”decimal" },
{ "name": ”potencia", 
"titles": ”potencia", 
”dc:description”: “Este campo contiene información sobre 
la portencia de cada vehículo, medida en CV.”
"datatype": ”decimal" },
{ "name": ”aceleracion", 
"titles": ”aceleración", 
”dc:description”: “Este campo contiene datos sobre la 
aceleración de cada vehículo medida en m/seg2”
"datatype": ”decimal" 
}}] 
}
}
```

- El diccionario de datos que se muestra como ejemplo está asociado al conjunto de datos que se muestra en esta guía.

- Entre  otras  propiedades,  se  está  describiendo  el  nombre  de  cada  una  de  las columnas utilizando la propiedad **"name"*.

- El uso de la propiedad **"title"** sirve para especificar la línea de cabecera de la tabla. La ausencia de esta propiedad indica que la tabla carece de línea de cabecera.

- Este encabezamiento de cada columna puede estar acompañado de un código de idioma de tal forma que la línea de cabecera se pueda expresar en diferentes idiomas.

- Se usa la propiedad **"datatype"** para describir los tipos de datos en los que se expresa cada valor de la columna correspondiente.

- La propiedad **"description"** permite incluir un texto descriptivo del contenido de cada columna.

- Herramientas como las que se describen en el apartado **“Toolbox para archivos CSV”** de esta guía, por ejemplo, CSVlint, permiten verificar la consistencia del conjunto de datos comparando el contenido del diccionario de datos y la estructura del archivo de datos.
- Entre otras comprobaciones se puede validar el número de columnas y su nombre, el tipo de valores permitidos, si éstos deben ser únicos o si existen vinculaciones de estos valores con otras tablas (claves externas).

