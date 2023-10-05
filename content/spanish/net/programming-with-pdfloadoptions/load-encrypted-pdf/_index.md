---
title: Cargar PDF cifrado
linktitle: Cargar PDF cifrado
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para cargar un PDF cifrado usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

Cuando procesa Words con documentos PDF en su aplicación .NET, puede ser necesario cargar archivos PDF protegidos con contraseña. Aspose.Words para .NET es una potente biblioteca que proporciona funcionalidad para cargar documentos PDF cifrados. En este artículo, lo guiaremos paso a paso para comprender y utilizar esta función.

## Comprensión de la función Cargar PDF cifrado

La función Cargar PDF cifrado de Aspose.Words para .NET le permite cargar archivos PDF protegidos con contraseña. Puede especificar la contraseña al cargar el documento para poder acceder a su contenido y manipularlo según sea necesario.

## Paso 1: cargar el documento PDF cifrado

El primer paso es cargar el documento PDF cifrado en su aplicación. He aquí cómo hacerlo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 Asegúrese de especificar la ruta correcta al archivo PDF cifrado en el`dataDir` variable.

## Paso 2: cifrar el documento PDF

 Si también desea cifrar su documento PDF, puede hacerlo utilizando el`PdfSaveOptions` clase y especificando los detalles de cifrado:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

Esto creará una versión cifrada del documento PDF en el directorio especificado.

## Paso 3: guardar el documento PDF cifrado

Después de cargar y, opcionalmente, cifrar el documento PDF, puede guardarlo en otro formato o procesarlo más según sus necesidades específicas.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Paso 5: cargar el documento PDF cifrado con contraseña

mantenimiento

Sin embargo, si desea cargar el documento PDF cifrado con una contraseña, debe utilizar el`PdfLoadOptions` clase y especifique la contraseña al cargar el documento:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 Asegúrese de proporcionar la contraseña correcta en el`Password` variable.

### Ejemplo de código fuente para cargar PDF cifrado usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## Conclusión

En este artículo, exploramos cómo utilizar la función Cargar PDF cifrado de Aspose.Words para .NET. Aprendió cómo cargar archivos PDF cifrados, cómo cifrar un documento PDF, cómo cargar un PDF cifrado con una contraseña y cómo generar resultados en formato Markdown. Esta característica es extremadamente útil cuando se procesan palabras con documentos PDF seguros.


