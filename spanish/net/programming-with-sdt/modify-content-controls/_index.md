---
title: Modificar controles de contenido
linktitle: Modificar controles de contenido
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a modificar texto, listas desplegables e imágenes dentro de los controles de contenido en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/modify-content-controls/
---

Este tutorial explica cómo modificar diferentes tipos de controles de contenido en un documento de Word utilizando Aspose.Words para .NET. Puede actualizar el texto, el valor seleccionado de una lista desplegable o reemplazar una imagen dentro de los controles de contenido.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y Procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde se encuentra su documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargar el documento e iterar sobre los controles de contenido
 Cargue el documento de Word usando el`Document`constructor, pasando la ruta al documento como parámetro. Iterar sobre todas las etiquetas de documentos estructurados en el documento usando un`foreach` bucle.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Realizar acciones según el tipo de control de contenido
}
```

## Paso 3: modificar el control de contenido de texto sin formato
 Para controles de contenido de tipo`SdtType.PlainText`, elimine todos los elementos secundarios existentes, cree un nuevo párrafo y agregue una secuencia con el texto deseado.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## Paso 4: modificar el control de contenido de la lista desplegable
 Para controles de contenido de tipo`SdtType.DropDownList` , actualice el valor seleccionado ajustándolo a un valor específico`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Paso 5: modificar el control de contenido de la imagen
 Para controles de contenido de tipo`SdtType.Picture`, recupere la forma dentro del control de contenido y reemplace su imagen por una nueva.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## Paso 6: Guarde el documento modificado
 Guarde el documento modificado en el directorio especificado usando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.ModifyContentControls.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Ejemplo de código fuente para modificar controles de contenido usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

¡Eso es todo! Ha modificado con éxito diferentes tipos de controles de contenido en su documento de Word utilizando Aspose.Words para .NET.