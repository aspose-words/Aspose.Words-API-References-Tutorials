---
title: Cree una nueva línea de firma y establezca la identificación del proveedor
linktitle: Cree una nueva línea de firma y establezca la identificación del proveedor
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear una nueva línea de firma y configurar el ID del proveedor en documentos de Word usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
## Introducción

¡Hola, entusiastas de la tecnología! ¿Alguna vez se preguntó cómo agregar una línea de firma en sus documentos de Word mediante programación? Bueno, hoy nos sumergiremos en eso usando Aspose.Words para .NET. Esta guía lo guiará a través de cada paso, haciendo que sea muy fácil crear una nueva línea de firma y establecer la identificación del proveedor en sus documentos de Word. Ya sea que esté automatizando el procesamiento de documentos o simplemente esté buscando optimizar su flujo de trabajo, este tutorial lo tiene cubierto.

## Requisitos previos

Antes de ensuciarnos las manos, asegurémonos de tener todo lo que necesitamos:

1.  Aspose.Words para .NET: si aún no lo has hecho, descárgalo[aquí](https://releases.aspose.com/words/net/).
2. Entorno de desarrollo: Visual Studio o cualquier otro entorno de desarrollo C#.
3. .NET Framework: asegúrese de tener .NET Framework instalado.
4. Certificado PFX: para firmar documentos, necesitará un certificado PFX. Puede obtener uno de una autoridad certificadora confiable.

## Importar espacios de nombres

Primero lo primero, importemos los espacios de nombres necesarios en su proyecto C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Muy bien, vayamos al meollo de la cuestión. Aquí hay un desglose detallado de cada paso para crear una nueva línea de firma y configurar la identificación del proveedor.

## Paso 1: crear un nuevo documento

Para empezar, necesitamos crear un nuevo documento de Word. Este será el lienzo de nuestra línea distintiva.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 En este fragmento, estamos inicializando un nuevo`Document` y un`DocumentBuilder` . El`DocumentBuilder` nos ayuda a agregar elementos a nuestro documento.

## Paso 2: Definir las opciones de la línea de firma

A continuación, definimos las opciones para nuestra línea de firma. Esto incluye el nombre, cargo, correo electrónico y otros detalles del firmante.

```csharp
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
```

Estas opciones personalizan la línea de firma, haciéndola clara y profesional.

## Paso 3: inserte la línea de firma

Con nuestras opciones configuradas, ahora podemos insertar la línea de firma en el documento.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

 Aquí el`InsertSignatureLine` El método agrega la línea de firma y le asignamos una identificación de proveedor única.

## Paso 4: guarde el documento

Después de insertar la línea de firma, guardemos el documento.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Esto guarda su documento con la línea de firma recién agregada.

## Paso 5: configurar las opciones de firma

Ahora necesitamos configurar las opciones para firmar el documento. Esto incluye el ID de la línea de firma, el ID del proveedor, los comentarios y la hora de la firma.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Estas opciones garantizan que el documento esté firmado con los detalles correctos.

## Paso 6: crear titular del certificado

Para firmar el documento, usaremos un certificado PFX. Creemos un titular de certificado para ello.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 Asegúrate de reemplazar`"morzal.pfx"` con su archivo de certificado real y`"aw"` con la contraseña de su certificado.

## Paso 7: firme el documento

Finalmente firmamos el documento mediante la utilidad de firma digital.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Esto firma el documento y lo guarda como un archivo nuevo.

## Conclusión

¡Y ahí lo tienes! Ha creado con éxito una nueva línea de firma y ha configurado el ID del proveedor en un documento de Word utilizando Aspose.Words para .NET. Esta poderosa biblioteca hace que sea increíblemente fácil administrar y automatizar las tareas de procesamiento de documentos. Pruébelo y vea cómo puede optimizar su flujo de trabajo.

## Preguntas frecuentes

### ¿Puedo personalizar la apariencia de la línea de firma?
¡Absolutamente! Puede modificar varias opciones en el`SignatureLineOptions` para satisfacer sus necesidades.

### ¿Qué pasa si no tengo un certificado PFX?
Deberá obtener uno de una autoridad certificadora confiable. Es esencial para firmar documentos digitalmente.

### ¿Puedo agregar varias líneas de firma a un documento?
Sí, puedes agregar tantas líneas de firma como necesites repitiendo el proceso de inserción con diferentes opciones.

### ¿Aspose.Words para .NET es compatible con .NET Core?
Sí, Aspose.Words para .NET es compatible con .NET Core, lo que lo hace versátil para diferentes entornos de desarrollo.

### ¿Qué tan seguras son las firmas digitales?
Las firmas digitales creadas con Aspose.Words son altamente seguras, siempre que utilice un certificado válido y confiable.