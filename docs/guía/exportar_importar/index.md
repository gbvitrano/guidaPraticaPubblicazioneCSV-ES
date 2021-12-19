---
hide:
 - toc
# - navigation
title: Pautas para exportar/importar datos tabulares desde herramientas de hojas de cálculo a CSV
---

# Pautas para exportar/importar datos tabulares desde herramientas de hojas de cálculo a CSV

- Las herramientas para el procesamiento de hojas de cálculo, por ejemplo, Microsoft Excel o Libreoffice Calc, pueden ocasionar problemas si se exportan tablas de datos directamente porque pueden contener: celdas combinadas, formulas,  macros, pestañas de expansión de datos, u otras características derivadas de la aplicación de funcionalidades propias de estas herramientas.
- A tener en cuenta:
	- Con el fin de exportar adecuadamente datos tabulares a partir de herramientas de procesamiento de hojas de cálculo, es necesario contemplar las siguientes pautas:
	
		- Dependiendo de los ajustes regionales, puede ser más conveniente usar como separador  `;` que `,`. En Europa, la `,` no es un separador apropiado dado que se utiliza como separador decimal, por tanto, es preferible usar “;”. En cambio, en países como UK o USA, el separador apropiado es `,`, dado que el separador decimal que se utiliza es `,`. No obstante, para evitar ambigüedades se suele utilizar otro tipo de separador como el separador **pipe**,`|`.

		- No usar celdas combinadas.

		- No dejar celdas, filas y/o columnas en blanco entre los datos.

		- No usar campos  alculados.


- Una práctica adecuada para verificar que los datos exportados están formateados correctamente en CSV consiste en abrir el archivo en un programa de texto como el bloc de notas o editor de texto. Si la exportación es correcta, se verán los datos exportados exactamente como están formateados por el software de exportación.
- Cuando Excel importa datos CSV elimina los ceros a la izquierda de los campos antes de mostrarlos, si los campos no están entre comillas. Esto puede ocasionar problemas cuando, por ejemplo, esos campos contienen claves numéricas. Igualmente, elimina siempre los espacios iniciales.
- Es recomendable exportar datos tabulares en formato CSV usando la [codificación estándar de caracteres UTF-8](https://www.w3.org/International/questions/qa-choosing-encodings).
	- Las hojas de cálculo de Excel que contienen algunos símbolos especiales, como la letra "ñ", tildes, acentos, etc. o algún otro tipo de carácter especial, pueden generar problemas al realizar una exportación de a CSV y su posterior recuperación, porque el comando "Guardar como CSV" distorsiona cualquier carácter que no sea ASCII.
	- Si la versión de Excel utilizada no permite guardar directamente el archivo de datos codificado como UTF-8, es recomendable utilizar algún procedimiento de conversión de formatos que garantice está codificación de caracteres. Además de Excel (a partir de la versión 16), herramientas útiles para realizar esta tarea son Google Spreadsheet y LibreOffice Calc.
