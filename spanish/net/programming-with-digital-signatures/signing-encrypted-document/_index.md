---
title: Firma de documento cifrado
linktitle: Firma de documento cifrado
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a firmar digitalmente un documento cifrado con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/signing-encrypted-document/
---

En este tutorial, lo guiaremos a través de los pasos para usar la función de firmar un documento encriptado con Aspose.Words para .NET. Esta característica le permite firmar digitalmente un documento de Word que está encriptado usando una contraseña de descifrado. Siga los pasos a continuación:

## Paso 1: Configuración de las opciones de firma

Cree una instancia de la clase SignOptions y establezca la contraseña de descifrado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Asegúrese de especificar la contraseña de descifrado correcta para su documento cifrado.

## Paso 2: Cargar el certificado

Comience cargando el certificado de firma usando la clase CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Asegúrese de especificar la ruta correcta a su certificado y la contraseña asociada.

## Paso 3: Firma del documento encriptado

Utilice la clase DigitalSignatureUtil para firmar el documento cifrado:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Asegúrese de especificar las rutas correctas para el documento cifrado, el documento firmado y el certificado.

### Ejemplo de código fuente para firmar documentos cifrados con Aspose.Words para .NET

Aquí está el código fuente completo para firmar un documento encriptado con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Siguiendo estos pasos, puede firmar fácilmente un documento de Word encriptado con Aspose.Words para .NET.

