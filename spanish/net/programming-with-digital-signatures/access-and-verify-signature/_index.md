---
title: Acceda y verifique la firma en un documento de Word
linktitle: Acceda y verifique la firma en un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
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
	Console.WriteLine("* Signature Found *");
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
		Console.WriteLine("* Signature Found *");
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

## Conclusión

En este tutorial, exploramos la característica de acceder y verificar firmas digitales en un documento de Word usando Aspose.Words para .NET. Siguiendo los pasos proporcionados, puede cargar fácilmente un documento, acceder a sus firmas digitales y verificar su validez. La capacidad de acceder y verificar firmas digitales proporciona una forma de garantizar la integridad y autenticidad de sus documentos de Word. Aspose.Words for .NET ofrece una potente API para el procesamiento de textos con firmas digitales, lo que le permite automatizar el proceso de verificación y mejorar la seguridad de sus documentos.

### Preguntas frecuentes

#### P: ¿Qué son las firmas digitales en un documento de Word?

R: Las firmas digitales en un documento de Word son firmas electrónicas que proporcionan una forma de autenticar la integridad y el origen del documento. Se crean mediante certificados digitales y algoritmos criptográficos, lo que permite a los destinatarios verificar que el documento no ha sido alterado y que proviene de una fuente confiable.

#### P: ¿Cómo puedo acceder a las firmas digitales en un documento de Word usando Aspose.Words para .NET?

R: Para acceder a las firmas digitales en un documento de Word utilizando Aspose.Words para .NET, puede seguir estos pasos:
1.  Cargue el documento utilizando el`Document` class y especifique la ruta al archivo del documento.
2.  Utilice un bucle para iterar a través de la`DigitalSignatures` colección del documento. Cada iteración representa una firma digital.

#### P: ¿A qué información puedo acceder desde una firma digital en un documento de Word?

R: A partir de una firma digital en un documento de Word, se puede acceder a diversa información, como por ejemplo:
- Vigencia: Comprobar si la firma es válida.
- Comentarios: obtenga el motivo de la firma especificado por el firmante.
- Hora de Firma: Obtiene la hora en que se firmó el documento.
- Nombre del sujeto: recupere el nombre del firmante o sujeto del certificado.
- Nombre del emisor: Obtenga el nombre del emisor del certificado.

#### P: ¿Puedo verificar la validez de una firma digital en un documento de Word utilizando Aspose.Words para .NET?

 R: Sí, puede verificar la validez de una firma digital en un documento de Word usando Aspose.Words para .NET. Al acceder a la`IsValid` propiedad de la`DigitalSignature` objeto, puede determinar si la firma es válida o no.

#### P: ¿Cómo puedo verificar la validez de las firmas digitales en un documento de Word usando Aspose.Words para .NET?

R: Para verificar la validez de las firmas digitales en un documento de Word utilizando Aspose.Words para .NET, puede seguir estos pasos:
1.  Acceder al`DigitalSignatures` colección del documento.
2.  Iterar a través de cada`DigitalSignature` objeto en la colección.
3.  Utilizar el`IsValid` propiedad de la`DigitalSignature` objeto para comprobar si la firma es válida.

#### P: ¿Puedo recuperar los comentarios del firmante o el motivo para firmar desde una firma digital en un documento de Word?

R: Sí, puede recuperar los comentarios del firmante o el motivo de la firma a partir de una firma digital en un documento de Word. El`Comments` propiedad de la`DigitalSignature` El objeto proporciona acceso a los comentarios especificados por el firmante durante el proceso de firma.

#### P: ¿Qué tipo de documentos admite la función de verificación de firma en Aspose.Words para .NET?

R: La función de verificación de firmas en Aspose.Words para .NET admite la verificación de firmas digitales en documentos de Word con el formato de archivo DOCX. Puede usar esta función para verificar firmas en archivos DOCX.

#### P: ¿Cómo puedo acceder a los detalles del certificado de una firma digital en un documento de Word usando Aspose.Words para .NET?

 R: Para acceder a los detalles del certificado de una firma digital en un documento de Word utilizando Aspose.Words para .NET, puede acceder a la`CertificateHolder` propiedad de la`DigitalSignature` objeto. Desde el`CertificateHolder` objeto, puede recuperar varios detalles del certificado, como el nombre del sujeto y el nombre del emisor.

#### P: ¿Puedo personalizar la visualización o el procesamiento de firmas digitales en un documento de Word usando Aspose.Words para .NET?

 R: Sí, puede personalizar la visualización o el procesamiento de firmas digitales en un documento de Word utilizando Aspose.Words para .NET. Accediendo a las propiedades y métodos del`DigitalSignature` objeto, puede extraer la información deseada, realizar validaciones adicionales o integrar el proceso de verificación de firma en el flujo de trabajo de su aplicación.

#### P: ¿Es posible verificar varias firmas digitales en un documento de Word usando Aspose.Words para .NET?

 R: Sí, es posible verificar múltiples firmas digitales en un documento de Word utilizando Aspose.Words para .NET. Al iterar a través de la`DigitalSignatures` colección del documento, puede acceder y verificar cada firma digital individualmente.

