---
title: Repetir filas en páginas posteriores
linktitle: Repetir filas en páginas posteriores
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a repetir las filas de la tabla en las páginas siguientes de un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

En este tutorial, aprenderemos a repetir las filas de una tabla en las páginas siguientes de un documento de Word utilizando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá especificar filas para repetir en las páginas siguientes de su tabla en sus documentos de Word.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Creación del documento e inicialización del generador de documentos
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

## Paso 3: construir la tabla con filas repetidas
A continuación, crearemos una tabla con filas repetidas en las páginas siguientes. Usa el siguiente código:

```csharp
// Comienzo de la mesa
builder. StartTable();

// Configuración de los parámetros de la primera línea (líneas de cabecera)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Inserta la primera celda de la primera fila
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Inserta la segunda celda de la primera fila
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Configura los parámetros de las siguientes líneas
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Bucle para insertar las celdas en las siguientes filas
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// final de la mesa
builder. EndTable();
```

 Aquí usamos el generador de documentos para crear una tabla con dos filas de encabezado y varias filas de datos. El`RowFormat.HeadingFormat`Los parámetros se utilizan para marcar las filas de encabezado que deben repetirse en las páginas siguientes.

## Paso 4: Guardar el documento modificado
finalmente nosotros

  necesita guardar el documento modificado con las filas de encabezado repetidas en las páginas siguientes de la tabla. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Código fuente de muestra para Repetir filas en páginas posteriores usando Aspose.Words para .NET 

```csharp
//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Conclusión
En este tutorial, aprendimos a repetir las filas de una tabla en las páginas siguientes de un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# provisto, puede especificar qué líneas repetir según sus necesidades específicas en sus documentos de Word.