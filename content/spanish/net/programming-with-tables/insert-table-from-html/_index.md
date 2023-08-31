---
title: Insertar tabla desde HTML
linktitle: Insertar tabla desde HTML
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar una tabla desde HTML en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/insert-table-from-html/
---

En este tutorial, aprenderemos cómo insertar una tabla en un documento de Word desde HTML usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá insertar tablas desde HTML en sus documentos de Word mediante programación.

## Paso 1: configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: crear el documento e inicializar el generador de documentos
Para iniciar el procesamiento de textos con el documento y el generador de documentos, siga estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creación de documentos
Document doc = new Document();

// Inicializar el generador de documentos
DocumentBuilder builder = new DocumentBuilder(doc);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: Insertar la tabla desde HTML
continuación, insertaremos la tabla en el documento usando código HTML. Utilice el siguiente código:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Aquí utilizamos el`InsertHtml` Método del creador de documentos para insertar el HTML que contiene la tabla. El HTML especificado crea una tabla con dos filas y dos celdas en cada fila. Puede personalizar el contenido de la tabla modificando el código HTML según sus necesidades.

## Paso 4: guardar el documento modificado
Finalmente, debemos guardar el documento modificado con la tabla insertada desde HTML. Utilice el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Código fuente de muestra para Insertar tabla desde HTML usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Tenga en cuenta que AutoFitSettings no se aplica a tablas insertadas desde HTML.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Conclusión
En este tutorial, aprendimos cómo insertar una tabla en un documento de Word desde HTML usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# proporcionado, puede insertar tablas desde HTML en sus documentos de Word mediante programación. Esta función le permite convertir e importar datos tabulares de fuentes HTML a sus documentos de Word.
