---
title: Firma de documentos de Word cifrados
linktitle: Firma de documentos de Word cifrados
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a firmar digitalmente un documento de Word encriptado con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/signing-encrypted-document/
---
En este tutorial, lo guiaremos a través de los pasos para usar la función de firmar un documento de Word encriptado con Aspose.Words para .NET. Esta característica le permite firmar digitalmente un documento de Word que está encriptado usando una contraseña de descifrado. Siga los pasos a continuación:

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

## Conclusión

En este tutorial, exploramos el proceso de firmar un documento de Word encriptado usando Aspose.Words para .NET. Al proporcionar la contraseña de descifrado y el certificado de firma, podemos agregar una firma digital a un documento encriptado. La firma de documentos cifrados garantiza su autenticidad e integridad, lo que proporciona una capa adicional de seguridad. Aspose.Words para .NET le permite firmar documentos encriptados y mantener la seguridad y confiabilidad de sus archivos de Word.

### Preguntas frecuentes

#### P: ¿Qué es la firma de documentos en Aspose.Words para .NET?

R: La firma de documentos en Aspose.Words para .NET se refiere al proceso de firma digital de un documento de Word para garantizar su autenticidad, integridad y no repudio. Se trata de añadir una firma digital al documento mediante un certificado.

#### P: ¿Qué es un documento de Word encriptado?

R: Un documento de Word encriptado es un documento que ha sido encriptado usando una contraseña. El cifrado es una medida de seguridad que protege el contenido del documento codificándolo y haciéndolo ilegible sin la contraseña de descifrado correcta.

#### P: ¿Cómo puedo firmar un documento de Word encriptado usando Aspose.Words para .NET?

R: Para firmar un documento de Word cifrado con Aspose.Words para .NET, debe proporcionar la contraseña de descifrado junto con el certificado de firma. Sigue estos pasos:
1.  Establezca la contraseña de descifrado en el`SignOptions` objeto.
2.  Cargue el certificado de firma usando el`CertificateHolder` clase.
3.  Utilizar el`DigitalSignatureUtil.Sign` método para firmar el documento cifrado, proporcionando los parámetros necesarios.

#### P: ¿Cuál es el propósito de firmar un documento encriptado?

R: Firmar un documento encriptado con Aspose.Words para .NET le permite agregar una firma digital al documento incluso cuando está encriptado. Esto proporciona una capa adicional de seguridad y garantiza la autenticidad e integridad del contenido cifrado. Permite a los destinatarios verificar el origen del documento y detectar cualquier manipulación.

#### P: ¿Puedo firmar un documento cifrado sin proporcionar la contraseña de descifrado?

R: No, para firmar un documento cifrado, debe proporcionar la contraseña de descifrado correcta. La contraseña de descifrado es necesaria para acceder y modificar el contenido cifrado del documento antes de aplicar la firma digital.

#### P: ¿Puedo firmar un documento de Word cifrado con cualquier certificado?

R: Para firmar un documento de Word cifrado con Aspose.Words para .NET, necesita un certificado X.509 válido. El certificado se puede obtener de una entidad emisora de certificados (CA) de confianza o se puede utilizar un certificado autofirmado con fines de prueba.

#### P: ¿Puedo firmar varios documentos de Word cifrados con el mismo certificado?

 R: Sí, puede firmar varios documentos de Word cifrados con el mismo certificado. Una vez que haya cargado el certificado usando el`CertificateHolder` class, puede reutilizarlo para firmar varios documentos cifrados.

#### P: ¿Puedo verificar la firma digital de un documento cifrado firmado?

 R: Sí, Aspose.Words para .NET brinda funcionalidad para verificar la firma digital de un documento cifrado firmado. Puedes usar el`DigitalSignatureUtil.Verify` método para comprobar la validez y autenticidad de la firma digital.

#### P: ¿Qué formato de archivo admite Aspose.Words para .NET para firmar documentos cifrados?

 R: Aspose.Words para .NET admite la firma de documentos de Word cifrados en formato de archivo DOCX. Puede firmar archivos DOCX encriptados usando el`DigitalSignatureUtil.Sign` método junto con la contraseña de descifrado y el certificado necesarios.

#### P: ¿Cómo afecta la firma de un documento cifrado al cifrado?

R: Firmar un documento encriptado con Aspose.Words para .NET no afecta el encriptado del documento. El cifrado permanece intacto y la firma digital se agrega al contenido cifrado. La firma digital proporciona seguridad y verificación adicionales sin comprometer el cifrado aplicado al documento.