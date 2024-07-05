---
title: Firmar documento de Word
linktitle: Firmar documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a firmar digitalmente un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/sign-document/
---
En este tutorial, lo guiaremos a través de los pasos para usar la función de firma de documentos con Aspose.Words para .NET. Esta función le permite firmar digitalmente un documento de Word mediante un certificado. Siga los pasos a continuación:

## Paso 1: cargar el certificado

Comience cargando el certificado de firma usando la clase CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Asegúrese de especificar la ruta correcta a su certificado y contraseña asociada.

## Paso 2: Firmar el documento

Utilice la clase DigitalSignatureUtil para firmar el documento:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Asegúrese de especificar las rutas correctas para el documento fuente y el documento firmado.

### Código fuente de ejemplo para firmar documento usando Aspose.Words para .NET

Aquí está el código fuente completo para firmar un documento con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Siguiendo estos pasos, podrá firmar fácilmente un documento de Word con Aspose.Words para .NET.

## Conclusión

 En este tutorial, exploramos la función de firma de documentos en Aspose.Words para .NET. Al cargar un certificado de firma y utilizar el`DigitalSignatureUtil.Sign` Con este método podremos firmar digitalmente un documento de Word. La firma de documentos proporciona autenticación y garantiza la integridad del contenido del documento, lo que la convierte en una característica valiosa para una gestión de documentos segura y confiable.

### Preguntas frecuentes sobre documentos de Word de signos

#### P: ¿Qué es la firma de documentos en Aspose.Words para .NET?

R: La firma de documentos en Aspose.Words para .NET se refiere al proceso de firmar digitalmente un documento de Word mediante un certificado. Esta característica agrega una firma digital al documento, proporcionando autenticidad, integridad y no repudio del contenido del documento.

#### P: ¿Cómo puedo cargar el certificado de firma en Aspose.Words para .NET?

 R: Para cargar el certificado de firma en Aspose.Words para .NET, puede utilizar el`CertificateHolder` clase. Crear una instancia de`CertificateHolder` proporcionando la ruta al archivo del certificado y la contraseña asociada. He aquí un ejemplo:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Asegúrese de proporcionar la ruta correcta a su certificado y la contraseña asociada.

#### P: ¿Cómo firmo un documento de Word usando Aspose.Words para .NET?

 R: Para firmar un documento de Word usando Aspose.Words para .NET, puede usar el`DigitalSignatureUtil` clase. Llama a`Sign` método, proporcionando la ruta al documento fuente, la ruta al documento firmado (salida) y el`CertificateHolder` objeto. He aquí un ejemplo:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Asegúrese de proporcionar las rutas correctas para el documento fuente y el documento firmado (salida).

#### P: ¿Cuál es el propósito de la firma de documentos?

R: La firma de documentos sirve como método para garantizar la autenticidad e integridad de un documento. Al firmar digitalmente un documento, puede proporcionar pruebas de su origen, verificar que su contenido no haya sido alterado y establecer el no repudio. La firma de documentos se utiliza comúnmente para documentos legales, financieros y confidenciales.

#### P: ¿Puedo utilizar cualquier certificado para firmar documentos en Aspose.Words para .NET?

R: Para firmar documentos en Aspose.Words para .NET, debe utilizar un certificado X.509 válido. Este certificado se puede obtener de una autoridad certificadora (CA) de confianza o se puede utilizar un certificado autofirmado con fines de prueba.

#### P: ¿Qué formato de archivo admite Aspose.Words para .NET para la firma de documentos?

 R: Aspose.Words para .NET admite la firma de documentos de Word en formato de archivo DOCX. Puede firmar archivos DOCX usando el`DigitalSignatureUtil` clase y el certificado correspondiente.

#### P: ¿Puedo firmar varios documentos de Word con el mismo certificado?

R: Sí, puedes firmar varios documentos de Word con el mismo certificado. Una vez que haya cargado el certificado usando el`CertificateHolder` clase, puede reutilizarla para firmar varios documentos llamando al`DigitalSignatureUtil.Sign` método con diferentes rutas de documentos fuente y firmados.

#### P: ¿La firma del documento modifica el documento original?

R: La firma de documentos con Aspose.Words para .NET no modifica el documento original. En su lugar, crea una copia firmada digitalmente del documento, dejando intacto el documento original. La copia firmada digitalmente contiene la firma digital agregada, lo que garantiza la integridad del contenido del documento.

#### P: ¿Puedo verificar la firma digital de un documento firmado usando Aspose.Words para .NET?

 R: Sí, Aspose.Words para .NET proporciona funcionalidad para verificar la firma digital de un documento firmado. Puedes usar el`DigitalSignatureUtil.Verify` Método para comprobar la validez y autenticidad de la firma digital.