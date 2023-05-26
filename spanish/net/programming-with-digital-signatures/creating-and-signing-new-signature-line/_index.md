---
title: Crear y firmar una nueva línea de firma
linktitle: Crear y firmar una nueva línea de firma
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a crear y firmar una nueva línea de firma en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---

En este tutorial, lo guiaremos a través de los pasos para usar la función Crear y firmar una nueva línea de firma con Aspose.Words para .NET. Esta función le permite insertar una línea de firma en un documento de Word, establecer opciones personalizadas y firmar el documento. Siga los pasos a continuación:

## Paso 1: Crear el Documento y el Generador

Comience creando una instancia de la clase Document y un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Inserción de la línea de firma

Utilice el método InsertSignatureLine() del objeto DocumentBuilder para insertar una nueva línea de firma en el documento:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Paso 3: Guarde el documento

Guarde el documento modificado:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento.

## Paso 4: Firma del documento

Para firmar el documento, debe configurar las opciones de firma y usar la clase DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Asegúrese de especificar las rutas correctas para el documento, la imagen de la línea de firma y el documento firmado.

### Ejemplo de código fuente para crear y firmar una nueva línea de firma usando Aspose.Words para .NET

Aquí está el código fuente completo para crear y firmar una nueva línea de firma con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Siguiendo estos pasos, podrá crear y firmar fácilmente una nueva línea de firma en su documento de Word con Aspose.Words para .NET.

