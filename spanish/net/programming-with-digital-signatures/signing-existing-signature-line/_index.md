---
title: Firma de la línea de firma existente
linktitle: Firma de la línea de firma existente
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a firmar una línea de firma existente en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/signing-existing-signature-line/
---

En este tutorial, lo guiaremos a través de los pasos para usar la función de firma de una línea de firma existente con Aspose.Words para .NET. Esta característica le permite firmar digitalmente una línea de firma ya presente en un documento de Word. Siga los pasos a continuación:

## Paso 1: Cargar el documento y acceder a la línea de firma

Comience cargando el documento que contiene la línea de firma existente:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Paso 2: Configuración de las opciones de firma

Cree una instancia de la clase SignOptions y configure las opciones de firma, incluido el ID de la línea de firma y la imagen de la línea de firma:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Asegúrese de especificar la ruta correcta a la imagen de la línea de la firma.

## Paso 3: Cargar el certificado

Comience cargando el certificado de firma usando la clase CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Asegúrese de especificar la ruta correcta a su certificado y la contraseña asociada.

## Paso 4: Firmar la línea de firma existente

Use la clase DigitalSignatureUtil para firmar la línea de firma existente:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Asegúrese de especificar las rutas correctas para el documento de origen, el documento firmado y el certificado.

### Ejemplo de código fuente para firmar una línea de firma existente usando Aspose.Words para .NET

Aquí está el código fuente completo para firmar una línea de firma existente con Aspose.Words para .NET:


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Siguiendo estos pasos, puede firmar fácilmente una línea de firma existente en un documento de Word con Aspose.Words para .NET.

