---
title: Firmar la línea de firma existente en un documento de Word
linktitle: Firmar la línea de firma existente en un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
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

## Conclusión

En este tutorial, aprendimos a firmar una línea de firma existente en un documento de Word usando Aspose.Words para .NET. Siguiendo los pasos proporcionados, puede cargar fácilmente el documento, acceder a la línea de firma existente, configurar las opciones de firma y firmar el documento. La capacidad de firmar una línea de firma existente proporciona una manera conveniente de agregar firmas digitales a áreas predefinidas en sus documentos de Word, asegurando la integridad y autenticación del documento. Aspose.Words para .NET ofrece una potente API para el procesamiento de textos con firmas digitales, lo que le permite personalizar el proceso de firma y mejorar la seguridad de sus documentos de Word.

### Preguntas frecuentes

#### P: ¿Qué es una línea de firma existente en un documento de Word?

R: Una línea de firma existente en un documento de Word es un área predefinida donde se puede colocar una firma. Por lo general, está representado por una forma u objeto en el documento y sirve como un espacio designado para que el firmante agregue su firma digital.

#### P: ¿Cómo puedo firmar una línea de firma existente en un documento de Word usando Aspose.Words para .NET?

R: Para firmar una línea de firma existente en un documento de Word usando Aspose.Words para .NET, puede seguir estos pasos:
1.  Cargue el documento utilizando el`Document` class y especifique la ruta al archivo del documento.
2.  Acceda a la línea de firma existente mediante el método o la propiedad adecuados. Por ejemplo, puedes usar`GetChild` para recuperar la forma de la línea de la firma.
3.  Crear una instancia de la`SignOptions`clase y establecer el`SignatureLineId` propiedad al ID de la línea de firma existente.
4.  Selecciona el`SignatureLineImage` propiedad de la`SignOptions` clase a la imagen que representa la firma digital.
5.  Cargue el certificado de firma usando el`CertificateHolder` clase y proporcione el certificado y la contraseña necesarios.
6.  Utilizar el`DigitalSignatureUtil.Sign` método para firmar el documento, proporcionando los parámetros necesarios, incluido el`SignOptions` objeto.

#### P: ¿Cómo accedo a la línea de firma existente en un documento de Word usando Aspose.Words para .NET?

 R: Para acceder a la línea de firma existente en un documento de Word usando Aspose.Words para .NET, puede usar el método o la propiedad adecuados para recuperar la forma de la línea de firma de la estructura del documento. Por ejemplo, puede utilizar el`GetChild` método con los parámetros apropiados para obtener la forma de línea de firma deseada.

#### P: ¿Puedo personalizar la apariencia de la firma digital en una línea de firma existente?

R: Sí, puede personalizar la apariencia de la firma digital en una línea de firma existente proporcionando un archivo de imagen que represente la firma. La imagen puede ser un logotipo, una firma manuscrita o cualquier otra representación gráfica de la firma. Puede configurar el`SignatureLineImage` propiedad de la`SignOptions` clase a los bytes del archivo de imagen.

#### P: ¿Puedo firmar varias líneas de firma existentes en un documento de Word?
 R: Sí, puede firmar varias líneas de firma existentes en un documento de Word. Debe seguir los pasos para cada línea de firma individualmente, configurando el`SignatureLineId` y`SignatureLineImage` valores en el`SignOptions` objeto para cada línea de firma.

#### P: ¿Qué formato debe tener el archivo de imagen para la firma digital en una línea de firma existente?

 R: El archivo de imagen de la firma digital en una línea de firma existente puede estar en varios formatos, como PNG, JPEG, BMP o GIF. Puede especificar la ruta del archivo o leer los bytes del archivo de imagen y asignarlo al`SignatureLineImage` propiedad de la`SignOptions` clase.
