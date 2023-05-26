---
title: Establecer ID de proveedor de firma
linktitle: Establecer ID de proveedor de firma
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a configurar la ID del proveedor de firmas en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/set-signature-provider-id/
---

En este tutorial, lo guiaremos a través de los pasos para usar la función Establecer ID de proveedor de firma con Aspose.Words para .NET. Esta función le permite especificar el ID del proveedor de firmas para una línea de firma en un documento de Word. Siga los pasos a continuación:

## Paso 1: Cargar el documento y acceder a la línea de firma

Comience cargando el documento que contiene la línea de firma:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Paso 2: Configuración de las opciones de firma

Cree una instancia de la clase SignOptions y configure las opciones de firma, incluido el ID del proveedor:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Paso 3: Firma del documento

Para firmar el documento, debe usar la clase DigitalSignatureUtil y especificar el certificado de firma:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Asegúrese de especificar las rutas correctas para el documento, el certificado y el documento firmado.

### Ejemplo de código fuente para establecer la identificación del proveedor de firmas usando Aspose.Words para .NET

Aquí está el código fuente completo para establecer la ID del proveedor de firmas con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Finalice el ID del proveedor de firmas en su documento de Word con Aspose.Words para .NET.

