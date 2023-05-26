---
title: Detectar firmas de documentos
linktitle: Detectar firmas de documentos
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para detectar firmas digitales en un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-fileformat/detect-document-signatures/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función de detección de firmas de documentos con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo detectar firmas digitales en un documento.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Detectar firmas digitales

 A continuación, usamos el`DetectFileFormat` metodo de la`FileFormatUtil` clase para detectar la información de formato de archivo. En este ejemplo, asumimos que el documento se llama "Firmado digitalmente.docx" y se encuentra en el directorio de documentos especificado.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## Paso 3: Buscar firmas digitales

 Verificamos si el documento contiene firmas digitales usando el`HasDigitalSignature` propiedad de la`FileFormatInfo` objeto. Si se detectan firmas digitales, mostramos un mensaje que indica que las firmas se perderán si el documento se abre/guarda con Aspose.Words.

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

Eso es todo ! Ha detectado con éxito firmas digitales en un documento utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para detectar firmas de documentos con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");

	if (info.HasDigitalSignature)
	{
		Console.WriteLine(
			$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
			"they will be lost if you open/save this document with Aspose.Words.");
	}
	
        
```
