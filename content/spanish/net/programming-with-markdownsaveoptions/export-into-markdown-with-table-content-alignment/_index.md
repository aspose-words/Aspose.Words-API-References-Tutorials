---
title: Exportar a Markdown con alineación del contenido de la tabla
linktitle: Exportar a Markdown con alineación del contenido de la tabla
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a exportar contenido de tabla con diferentes alineaciones a archivos Markdown usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Aquí hay una guía paso a paso para explicar el siguiente código fuente de C# que ayuda a exportar contenido a un archivo Markdown con alineación del contenido de la tabla utilizando la biblioteca Aspose.Words para .NET. Asegúrese de haber incluido la biblioteca Aspose.Words en su proyecto antes de usar este código.

## Paso 1: establecer la ruta del directorio de documentos

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Asegúrese de especificar la ruta correcta al directorio de documentos donde se guardará el documento editado.

## Paso 2: crear un documento y un generador de documentos

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Aquí creamos una instancia del`Document` clase y una instancia de la`DocumentBuilder` clase que nos permitirá manipular el documento y agregar elementos.

## Paso 3: inserta celdas en la tabla con diferentes alineaciones de párrafos

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Usamos el Generador de documentos para insertar celdas en la tabla y establecer diferentes alineaciones de párrafos para cada celda.

## Paso 4: configure las opciones de exportación de Markdown y guarde el documento modificado

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

Configuramos las opciones de exportación de Markdown con diferentes alineaciones del contenido de la tabla, luego guardamos el documento modificado usando cada opción de alineación.

### Código fuente de ejemplo para exportar a Markdown con alineación del contenido de la tabla usando Aspose.Words para .NET

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

	// La alineación en este caso se tomará del primer párrafo en la columna correspondiente de la tabla.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Guardar el documento modificado
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
