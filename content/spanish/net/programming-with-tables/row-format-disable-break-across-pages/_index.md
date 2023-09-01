---
title: Formato de fila Desactivar salto entre páginas
linktitle: Formato de fila Desactivar salto entre páginas
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo deshabilitar el salto de línea para una tabla en varias páginas en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/row-format-disable-break-across-pages/
---

En este tutorial, aprenderemos cómo deshabilitar el salto de línea de una tabla de varias páginas en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá desactivar el salto de línea para todas las filas de su tabla en sus documentos de Word.

## Paso 1: configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento
Para iniciar el procesamiento de textos con el documento, siga estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos y proporcione el nombre de archivo correcto.

## Paso 3: deshabilite el salto de fila de la tabla
A continuación, desactivaremos la división de filas para todas las filas de la tabla. Utilice el siguiente código:

```csharp
// recuperar la mesa
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Deshabilitar el salto de fila para todas las filas de la tabla
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Aquí usamos el documento para buscar la primera tabla y luego recorrer todas las filas de la tabla usando un bucle foreach. Dentro del bucle, deshabilitamos la división de filas para cada fila configurando el`RowFormat.AllowBreakAcrossPages` propiedad a`false`.

## Paso 4: guardar el documento modificado
Finalmente, debemos guardar el documento modificado con el salto de línea de la tabla deshabilitado. Utilice el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Código fuente de muestra para formato de fila Deshabilitar salto entre páginas usando Aspose.Words para .NET 

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Deshabilite la división entre páginas para todas las filas de la tabla.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Conclusión
En este tutorial, aprendimos cómo deshabilitar el salto de línea de una tabla de varias páginas en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# proporcionado, puede aplicar esta desactivación a sus tablas en sus documentos de Word.