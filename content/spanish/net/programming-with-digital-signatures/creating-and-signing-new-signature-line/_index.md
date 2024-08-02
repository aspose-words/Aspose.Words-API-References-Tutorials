---
title: Crear y firmar una nueva línea de firma
linktitle: Crear y firmar una nueva línea de firma
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear y firmar digitalmente una línea de firma en un documento de Word usando Aspose.Words para .NET con este tutorial paso a paso. Perfecto para la automatización de documentos.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
## Introducción

¡Hola! Entonces, tienes un documento de Word y necesitas agregar una línea de firma y luego firmarlo digitalmente. ¿Suena complicado? ¡De nada! Gracias a Aspose.Words para .NET, puedes lograr esto sin problemas con solo unas pocas líneas de código. En este tutorial, lo guiaremos a través de todo el proceso, desde configurar su entorno hasta guardar su documento con una firma nueva y brillante. ¿Listo? ¡Vamos a sumergirnos!

## Requisitos previos

Antes de pasar al código, asegurémonos de que tiene todo lo que necesita:
1.  Aspose.Words para .NET: puede[descarguelo aqui](https://releases.aspose.com/words/net/).
2. Se recomienda encarecidamente un entorno de desarrollo .NET: Visual Studio.
3. Un documento para firmar: cree un documento de Word sencillo o utilice uno existente.
4.  Un archivo de certificado: es necesario para las firmas digitales. Puedes usar un`.pfx` archivo.
5. Imágenes para Línea de Firma: opcionalmente, un archivo de imagen para la firma.

## Importar espacios de nombres

Primero, necesitamos importar los espacios de nombres necesarios. Este paso es crucial ya que configura el entorno para utilizar las funcionalidades de Aspose.Words.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Paso 1: configurar el directorio de documentos

Todo proyecto necesita un buen comienzo. Configuremos la ruta a su directorio de documentos. Aquí es donde se guardarán y recuperarán sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: crear un nuevo documento

Ahora, creemos un nuevo documento de Word usando Aspose.Words. Este será nuestro lienzo donde agregaremos la línea de firma.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Insertar la línea de firma

 Aquí es donde ocurre la magia. Insertamos una línea de firma en nuestro documento usando el`DocumentBuilder` clase.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Paso 4: Guardar el documento con la línea de firma

Una vez que la línea de firma esté en su lugar, debemos guardar el documento. Este es un paso intermedio antes de proceder a firmarlo.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Paso 5: configurar las opciones de registro

Ahora, configuremos las opciones para firmar el documento. Esto incluye especificar el ID de la línea de firma y la imagen que se utilizará.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf")
};
```

## Paso 6: cargar el certificado

Las firmas digitales requieren un certificado. Aquí cargamos el archivo de certificado que se utilizará para firmar el documento.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Paso 7: Firmar el documento

 Este es el paso final. Usamos el`DigitalSignatureUtil`clase para firmar el documento. El documento firmado se guarda con un nuevo nombre.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

## Conclusión

¡Y ahí lo tienes! Con estos pasos, creó exitosamente un nuevo documento de Word, agregó una línea de firma y lo firmó digitalmente usando Aspose.Words para .NET. Es una herramienta poderosa que facilita la automatización de documentos. Ya sea que se trate de contratos, acuerdos o cualquier documento formal, este método garantiza que estén firmados y autenticados de forma segura.

## Preguntas frecuentes

### ¿Puedo utilizar otros formatos de imagen para la línea de firma?
Sí, puedes utilizar varios formatos de imagen como PNG, JPG, BMP, etc.

###  ¿Es necesario utilizar un`.pfx` file for the certificate?
 Sí un`.pfx` El archivo es un formato común para almacenar información criptográfica, incluidos certificados y claves privadas.

### ¿Puedo agregar varias líneas de firma en un solo documento?
¡Absolutamente! Puede insertar varias líneas de firma repitiendo el paso de inserción para cada firma.

### ¿Qué pasa si no tengo un certificado digital?
Deberá obtener un certificado digital de una autoridad certificadora confiable o generar uno usando herramientas como OpenSSL.

### ¿Cómo verifico la firma digital en el documento?
Puede abrir el documento firmado en Word e ir a los detalles de la firma para verificar la autenticidad e integridad de la firma.