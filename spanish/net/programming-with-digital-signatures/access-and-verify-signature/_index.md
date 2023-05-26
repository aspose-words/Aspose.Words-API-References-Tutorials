---
title: Acceder y verificar la firma
linktitle: Acceder y verificar la firma
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a acceder y verificar firmas digitales en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/access-and-verify-signature/
---
En este tutorial, lo guiaremos a través de los pasos para usar la función de verificación de acceso y firma de Aspose.Words para .NET. Esta característica le permite acceder a las firmas digitales en un documento de Word y verificar su validez. Siga los pasos a continuación:

## Paso 1: Cargar el documento y acceder a las firmas

Comience cargando el documento que contiene las firmas digitales:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Paso 2: busque firmas digitales

Utilice un bucle para recorrer todas las firmas digitales del documento:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Acceder a la información de la firma
	Console.WriteLine("*** Signature Found ***");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Esta propiedad solo está disponible en documentos de MS Word.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Asegúrese de personalizar los mensajes de la pantalla según sus necesidades.

### Código fuente de ejemplo para Acceder y verificar la firma usando Aspose.Words para .NET

Aquí está el código fuente completo para la verificación de acceso y firma usando Aspose.Words para .NET:

```csharp
	
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("*** Signature Found ***");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Esta propiedad solo está disponible en documentos de MS Word.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Siguiendo estos pasos, podrá acceder y verificar fácilmente las firmas digitales en su documento de Word con Aspose.Words para .NET.


