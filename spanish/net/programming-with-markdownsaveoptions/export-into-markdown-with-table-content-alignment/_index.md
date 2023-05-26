---
title: Exportar a Markdown con alineación de contenido de tabla
linktitle: Exportar a Markdown con alineación de contenido de tabla
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a exportar contenido de tablas con diferentes alineaciones a archivos Markdown usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Aquí hay una guía paso a paso para explicar el siguiente código fuente de C# que ayuda a exportar contenido a un archivo Markdown con alineación de contenido de tabla usando la biblioteca Aspose.Words para .NET. Asegúrese de haber incluido la biblioteca Aspose.Words en su proyecto antes de usar este código.

## Paso 1: establecer la ruta del directorio del documento

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Asegúrese de especificar la ruta correcta a su directorio de documentos donde se guardará el documento editado.

## Paso 2: Crear un documento y un generador de documentos

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Aquí creamos una instancia de la`Document` clase y una instancia de la`DocumentBuilder` class que nos permitirá manipular el documento y añadir elementos.

## Paso 3: inserte celdas en la tabla con diferentes alineaciones de párrafo

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Usamos el Generador de documentos para insertar celdas en la tabla y establecer diferentes alineaciones de párrafo para cada celda.

## Paso 4: establezca las opciones de exportación de Markdown y guarde el documento modificado

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

Configuramos las opciones de exportación de Markdown con diferentes alineaciones de contenido de tabla, luego guardamos el documento modificado usando cada opción de alineación.

### Código fuente de ejemplo para exportar a Markdown con alineación de contenido de tabla usando Aspose.Words para .NET

```csharp

            
	// La ruta al directorio de documentos.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Hace que todos los párrafos dentro de la tabla estén alineados.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// La alineación en este caso se tomará del primer párrafo en la columna de la tabla correspondiente.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Guardar el documento modificado
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
