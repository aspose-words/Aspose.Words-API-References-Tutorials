---
title: Control de contenido del cuadro combinado
linktitle: Control de contenido del cuadro combinado
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a crear un control de contenido de cuadro combinado en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/combo-box-content-control/
---

Este tutorial explica cómo crear un control de contenido de cuadro combinado en un documento de Word utilizando Aspose.Words para .NET. Los controles de contenido del cuadro combinado permiten a los usuarios seleccionar un elemento de una lista desplegable.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y Procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: crear un documento y una etiqueta de documento estructurado
 Crear una nueva instancia de la`Document` clase y un`StructuredDocumentTag` para representar el control de contenido del cuadro combinado. Especificar`SdtType.ComboBox` como el tipo y`MarkupLevel.Block` como nivel de marcado para crear un cuadro combinado a nivel de bloque.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Paso 3: agregue elementos al cuadro combinado
 Agregue elementos al cuadro combinado utilizando el`ListItems`propiedad de la`StructuredDocumentTag` Cada elemento está representado por un`SdtListItem` objeto, que toma un texto de visualización y un valor. En este ejemplo, agregamos tres elementos al cuadro combinado.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Paso 4: agregue la etiqueta de documento estructurado al documento
 Agregue el control de contenido del cuadro combinado al cuerpo del documento mediante el`AppendChild` método del cuerpo de la primera sección del documento.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Paso 5: Guarde el documento
 Guarde el documento en el directorio especificado usando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Ejemplo de código fuente para Combo Box Content Control usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

¡Eso es todo! Ha creado con éxito un control de contenido de cuadro combinado en su documento de Word utilizando Aspose.Words para .NET.