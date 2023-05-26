---
title: Escapar Uri
linktitle: Escapar Uri
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para escapar de Uri con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/escape-uri/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función de escape de Uri con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo insertar hipervínculos con Uri escapado en un documento.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cree un documento y un DocumentBuilder

 A continuación, debemos crear un nuevo`Document` objeto y un`DocumentBuilder` objeto para construir el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: inserte hipervínculos con Uri escapado

 Utilizar el`InsertHyperlink` metodo de la`DocumentBuilder`objeto para insertar hipervínculos en el documento. Uri debe ser escapado usando el`Uri.EscapeUriString` función para evitar errores de formato.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), falso);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), falso);
```

## Paso 4: Guarde el documento como PDF

 Finalmente, podemos guardar el documento como PDF usando el`Save` metodo de la`Document` objeto. Especifique el nombre del archivo de salida.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

Eso es todo ! Ha insertado con éxito hipervínculos con Uri escapados en un documento usando Aspose.Words para .NET.

### Ejemplo de código fuente para Uri escapando con Aspose.Words para .NET


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", falso);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", falso);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```
