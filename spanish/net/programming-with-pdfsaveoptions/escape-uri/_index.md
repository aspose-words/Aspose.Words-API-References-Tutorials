---
title: URI de escape en documento PDF
linktitle: URI de escape en documento PDF
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso Cómo escapar URI en documento PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/escape-uri/
---

Este artículo proporciona una guía paso a paso sobre cómo escapar URI en un documento PDF con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo insertar hipervínculos con Uri escapado en un documento.

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

 Utilizar el`InsertHyperlink` metodo de la`DocumentBuilder` objeto para insertar hipervínculos en el documento. Uri debe ser escapado usando el`Uri.EscapeUriString` función para evitar errores de formato.

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

## Conclusión

En este tutorial, cubrimos cómo escapar de los URI en un documento PDF usando Aspose.Words para .NET. Al escapar los URI, puede evitar errores de formato y asegurarse de que los hipervínculos se interpreten y muestren correctamente en el documento PDF. Siga los pasos descritos para insertar hipervínculos con URI escapados en su documento PDF. Asegúrate de escapar.

### Preguntas frecuentes

#### P: ¿Qué es el URI de escape en un documento PDF y por qué es importante?
R: URI de escape en un documento PDF se refiere al método de convertir caracteres especiales en una URL en secuencias de escape para evitar errores de formato. Esto es importante porque los caracteres especiales en una URL pueden alterar la estructura de la URL y provocar una mala interpretación o una representación incorrecta. Al escapar los caracteres especiales, garantizamos que la URL se interprete y muestre correctamente en el documento PDF.

#### P: ¿Cómo puedo usar Aspose.Words para .NET para escapar de los URI en un documento PDF?
R: Para escapar de los URI en un documento PDF usando Aspose.Words para .NET, siga estos pasos:

 Establezca la ruta del directorio donde se encuentran sus documentos reemplazando`"YOUR DOCUMENT DIRECTORY"` con la ruta real de su directorio de documentos.

 Crear una nueva instancia de la`Document` clase y un`DocumentBuilder` objeto para construir el documento.

 Utilizar el`InsertHyperlink` metodo de la`DocumentBuilder` objeto para insertar hipervínculos en el documento. Asegúrese de escapar del URI usando el`Uri.EscapeUriString` función para evitar errores de formato.

 Utilizar el`Save` metodo de la`Document` objeto para guardar el documento en formato PDF especificando el nombre del archivo de salida.

#### P: ¿Cuáles son los beneficios de escapar URI en un documento PDF?
R: Los beneficios de escapar URI en un documento PDF son:

Prevención de errores de formato: el escape de URI ayuda a evitar errores de formato causados por caracteres especiales en una URL, lo que garantiza que la URL se interprete y muestre correctamente en el documento PDF.

Compatibilidad con lectores de PDF: los URI escapados generalmente son compatibles con los lectores de PDF, lo que garantiza una mejor compatibilidad y una experiencia de usuario uniforme.

#### P: ¿Qué caracteres especiales se deben escapar en un URI?
 R: Los caracteres especiales que se deben escapar en un URI son: espacio, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.