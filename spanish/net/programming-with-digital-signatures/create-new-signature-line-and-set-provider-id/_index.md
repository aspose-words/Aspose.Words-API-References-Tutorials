---
title: Crear nueva línea de firma y establecer la identificación del proveedor
linktitle: Crear nueva línea de firma y establecer la identificación del proveedor
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a crear una nueva línea de firma y establecer la ID del proveedor en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---

En este tutorial, lo guiaremos a través de los pasos para usar la función Crear nueva línea de firma y Establecer ID de proveedor con Aspose.Words para .NET. Esta función le permite insertar una línea de firma en un documento de Word, establecer opciones personalizadas y firmar el documento. Siga los pasos a continuación:

## Paso 1: Crear el Documento y el Generador

Comience creando una instancia de la clase Document y un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Configuración de las opciones de la línea de firma

Cree una instancia de la clase SignatureLineOptions y establezca las opciones deseadas:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Paso 3: Inserción de la línea de firma

Utilice el método InsertSignatureLine() del objeto DocumentBuilder para insertar la línea de firma en el documento:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Paso 4: Establecer ID de proveedor

Establezca la ID del proveedor para la línea de firma usando la propiedad ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Asegúrese de especificar el ID de proveedor correcto para su caso de uso.

## Paso 5: Guarde el documento

Guarde el documento modificado:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento.

## Paso 6: Firma del documento

Para firmar el documento, debe configurar las opciones de firma y usar la clase DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Asegúrese de especificar las rutas correctas para el documento, el certificado y el documento firmado.

### Código fuente de ejemplo para crear una nueva línea de firma y establecer la identificación del proveedor usando Aspose.Words para .NET

Aquí está el código fuente completo para crear una nueva línea de firma y establecer la ID del proveedor con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Siguiendo estos pasos, puede crear fácilmente una nueva línea de firma y establecer la ID del proveedor en su documento de Word con Aspose.Words para .NET.

