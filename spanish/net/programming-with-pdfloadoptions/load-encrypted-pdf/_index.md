---
title: Cargar PDF encriptado
linktitle: Cargar PDF encriptado
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para cargar un PDF encriptado usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

Cuando trabaje con documentos PDF en su aplicación .NET, puede ser necesario cargar archivos PDF protegidos con contraseña. Aspose.Words para .NET es una poderosa biblioteca que brinda funcionalidad para cargar documentos PDF encriptados. En este artículo, lo guiaremos paso a paso para comprender y usar esta función.

## Descripción de la función Cargar PDF cifrado

La función Cargar PDF cifrado de Aspose.Words para .NET le permite cargar archivos PDF protegidos con contraseña. Puede especificar la contraseña al cargar el documento para poder acceder a su contenido y manipularlo según sea necesario.

## Paso 1: cargar el documento PDF cifrado

El primer paso es cargar el documento PDF cifrado en su aplicación. Aquí está cómo hacerlo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 Asegúrese de especificar la ruta correcta al archivo PDF cifrado en el`dataDir` variable.

## Paso 2: Cifrado del documento PDF

 Si también desea cifrar su documento PDF, puede hacerlo utilizando el`PdfSaveOptions` clase y especificando los detalles de encriptación:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

Esto creará una versión cifrada del documento PDF en el directorio especificado.

## Paso 3: guardar el documento PDF cifrado

Después de cargar y, opcionalmente, cifrar el documento PDF, puede guardarlo en otro formato o procesarlo según sus necesidades específicas.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Paso 5: Cargar el documento PDF cifrado con contraseña

Mantenimiento

 Sin embargo, si desea cargar el documento PDF encriptado con una contraseña, debe usar el`PdfLoadOptions` clase y especifique la contraseña al cargar el documento:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 Asegúrese de proporcionar la contraseña correcta en el`Password` variable.

### Ejemplo de código fuente para cargar PDF cifrado con Aspose.Words para .NET

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

En este artículo, exploramos cómo usar la función Cargar PDF cifrado de Aspose.Words para .NET. Aprendió cómo cargar archivos PDF encriptados, cómo encriptar un documento PDF, cómo cargar un PDF encriptado con una contraseña y cómo generar resultados en formato Markdown. Esta característica es extremadamente útil cuando se trabaja con documentos PDF seguros.


