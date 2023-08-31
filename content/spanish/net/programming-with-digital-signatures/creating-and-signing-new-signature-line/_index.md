---
title: Crear y firmar una nueva línea de firma
linktitle: Crear y firmar una nueva línea de firma
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a crear y firmar una nueva línea de firma en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
En este tutorial, lo guiaremos a través de los pasos para usar la función Crear y firmar una nueva línea de firma con Aspose.Words para .NET. Esta función le permite insertar una línea de firma en un documento de Word, establecer opciones personalizadas y firmar el documento. Siga los pasos a continuación:

## Paso 1: Crear el Documento y el Generador

Comience creando una instancia de la clase Document y un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Inserción de la línea de firma

Utilice el método InsertSignatureLine() del objeto DocumentBuilder para insertar una nueva línea de firma en el documento:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Paso 3: Guarde el documento

Guarde el documento modificado:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento.

## Paso 4: Firma del documento

Para firmar el documento, debe configurar las opciones de firma y usar la clase DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Asegúrese de especificar las rutas correctas para el documento, la imagen de la línea de firma y el documento firmado.

### Ejemplo de código fuente para crear y firmar una nueva línea de firma usando Aspose.Words para .NET

Aquí está el código fuente completo para crear y firmar una nueva línea de firma con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Siguiendo estos pasos, podrá crear y firmar fácilmente una nueva línea de firma en su documento de Word con Aspose.Words para .NET.

## Conclusión

En este tutorial, aprendimos cómo crear y firmar una nueva línea de firma en un documento de Word usando Aspose.Words para .NET. Siguiendo los pasos proporcionados, puede insertar fácilmente una línea de firma en su documento, personalizar sus opciones y firmar el documento con un certificado digital. Agregar líneas de firma y firmas digitales a sus documentos mejora su autenticidad e integridad, haciéndolos más seguros y confiables. Aspose.Words for .NET proporciona una potente API para el procesamiento de textos con firmas y certificados digitales en documentos de Word, lo que le permite automatizar el proceso de firma y garantizar la validez de sus documentos.

### Preguntas frecuentes

#### P: ¿Qué es una línea de firma en un documento de Word?

R: Una línea de firma en un documento de Word es un marcador de posición que indica dónde se debe colocar una firma. Por lo general, incluye el nombre, el título y la fecha, y proporciona espacio para una firma manuscrita o digital.

#### P: ¿Cómo puedo crear una línea de firma en un documento de Word usando Aspose.Words para .NET?

R: Para crear una línea de firma en un documento de Word usando Aspose.Words para .NET, puede seguir estos pasos:
1.  Crear una instancia de la`Document` clase y un`DocumentBuilder` objeto.
2.  Utilizar el`InsertSignatureLine` metodo de la`DocumentBuilder` objeto para insertar una nueva línea de firma en el documento.
3. Guarde el documento modificado.

#### P: ¿Puedo personalizar las opciones de la línea de firma, como el nombre, el cargo y la fecha?

 R: Sí, puede personalizar las opciones de la línea de firma. El`SignatureLineOptions` class proporciona propiedades para establecer las opciones deseadas, como`Signer`, `SignerTitle`, `ShowDate`, etc. Puede modificar estas propiedades antes de insertar la línea de firma.

#### P: ¿Cómo puedo firmar el documento después de crear una línea de firma?

 R: Para firmar el documento después de crear una línea de firma, debe configurar las opciones de firma y usar el`DigitalSignatureUtil` clase. Aquí están los pasos:
1.  Selecciona el`SignatureLineId` propiedad en el`SignOptions` oponerse al ID de la línea de firma.
2.  Selecciona el`SignatureLineImage` propiedad en el`SignOptions` oponerse a la imagen de la firma que desea utilizar.
3.  Cargue el certificado de firma usando el`CertificateHolder` clase.
4.  Utilizar el`DigitalSignatureUtil.Sign` método para firmar el documento, proporcionando los parámetros necesarios.

#### P: ¿Puedo usar una imagen de firma digital para firmar el documento?

 R: Sí, puede usar una imagen de firma digital para firmar el documento. Para hacer esto, debe proporcionar el archivo de imagen en el`SignOptions` objeto usando el`SignatureLineImage`propiedad. La imagen puede estar en cualquier formato de imagen compatible, como JPEG, PNG o EMF.

#### P: ¿Cuál es el propósito de crear y firmar una nueva línea de firma en un documento de Word?

R: Crear y firmar una nueva línea de firma en un documento de Word usando Aspose.Words para .NET le permite agregar un marcador de posición para una firma y luego firmar el documento usando un certificado digital. Este proceso asegura la autenticidad e integridad del documento, proporcionando evidencia de aprobación o acuerdo.

#### P: ¿Puedo crear y firmar varias líneas de firma en un documento de Word usando Aspose.Words para .NET?

R: Sí, puede crear y firmar varias líneas de firma en un documento de Word utilizando Aspose.Words para .NET. Cada línea de firma puede tener su propia ID y opciones únicas. Puede repetir los pasos para crear y firmar líneas de firma adicionales en el documento.

#### P: ¿Puedo modificar la línea de la firma o agregar información adicional después de haberla firmado?

R: Una vez que se ha firmado una línea de firma, se convierte en parte del contenido del documento y no se puede modificar por separado. Sin embargo, puede agregar información o contenido adicional después de la línea de firma firmada.

#### P: ¿Puedo verificar la firma digital de un documento que contiene una línea de firma?

 R: Sí, Aspose.Words para .NET brinda funcionalidad para verificar la firma digital de un documento que contiene una línea de firma. Puedes usar el`DigitalSignatureUtil.Verify` método para comprobar la validez y autenticidad de la firma digital.

#### P: ¿Qué formato de archivo admite Aspose.Words para .NET para crear y firmar líneas de firma?

R: Aspose.Words para .NET admite la creación y firma de líneas de firma en el formato de archivo DOCX. Puede crear y firmar líneas de firma en archivos DOCX utilizando los métodos y clases proporcionados.