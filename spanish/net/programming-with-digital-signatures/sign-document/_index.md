---
title: Firmar documento
linktitle: Firmar documento
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a firmar digitalmente un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/sign-document/
---

En este tutorial, lo guiaremos a través de los pasos para usar la función de firma de documentos con Aspose.Words para .NET. Esta característica le permite firmar digitalmente un documento de Word usando un certificado. Siga los pasos a continuación:

## Paso 1: Cargar el certificado

Comience cargando el certificado de firma usando la clase CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Asegúrese de especificar la ruta correcta a su certificado y la contraseña asociada.

## Paso 2: Firma del documento

Utilice la clase DigitalSignatureUtil para firmar el documento:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Asegúrese de especificar las rutas correctas para el documento de origen y el documento firmado.

### Código fuente de ejemplo para firmar documento usando Aspose.Words para .NET

Aquí está el código fuente completo para firmar un documento con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Siguiendo estos pasos, puede firmar fácilmente un documento de Word con Aspose.Words para .NET.



