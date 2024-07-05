---
title: Convertir Docx a Mhtml y enviar correo electrónico
linktitle: Convertir Docx a Mhtml y enviar correo electrónico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo convertir DOCX a MHTML y enviar correos electrónicos usando Aspose.Words para .NET en esta guía paso a paso. Aumente su productividad con una sencilla automatización.
type: docs
weight: 10
url: /es/net/basic-conversions/docx-to-mhtml-and-sending-email/
---
## Introducción

En la era digital actual, convertir documentos de un formato a otro y enviarlos por correo electrónico es una tarea común. Este artículo lo guiará a través del proceso de convertir un archivo DOCX al formato MHTML y luego enviarlo como correo electrónico usando Aspose.Words para .NET. Desglosaremos cada paso en una guía detallada y fácil de seguir, asegurándonos de que comprenda el proceso de principio a fin. ¡Vamos a sumergirnos!

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

1. Aspose.Words para .NET: descargue e instale la biblioteca Aspose.Words para .NET desde[Página de lanzamientos de Aspose](https://releases.aspose.com/words/net/).
2.  Aspose.Email para .NET: descargue e instale la biblioteca Aspose.Email para .NET desde[Página de lanzamientos de Aspose](https://releases.aspose.com/email/net/).
3. .NET Framework: asegúrese de tener .NET Framework instalado en su máquina.
4. Servidor SMTP: necesita acceso a un servidor SMTP para enviar correos electrónicos.

## Importar espacios de nombres

Para utilizar Aspose.Words y Aspose.Email en su proyecto, necesita importar los espacios de nombres necesarios. Agregue las siguientes directivas de uso en la parte superior de su archivo C#:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Clients.Smtp;
```

Dividamos el proceso en varios pasos para asegurarnos de que comprenda cada parte con claridad.

## Paso 1: cargue el documento DOCX

 Primero, debes cargar el documento DOCX que deseas convertir. Utilizar el`Document` clase de Aspose.Words para cargar su archivo DOCX.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Paso 2: guarde el documento como MHTML

 A continuación, guarde el documento cargado como un archivo MHTML. Esto se hace usando el`Save` método de la`Document` clase.

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);

// Rebobina la transmisión hasta el principio para que Aspose.Email pueda leerla.
stream.Position = 0;
```

## Paso 3: cree un mensaje de correo electrónico

Ahora, cree un mensaje de correo electrónico desde la secuencia MHTML usando Aspose.Email. Usarás el`MailMessage` clase para este propósito.

```csharp
// Cree un mensaje de correo electrónico Aspose.Email MIME desde la secuencia.
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

## Paso 4: envíe el correo electrónico

 Finalmente, envíe el correo electrónico utilizando un cliente SMTP. Configure el cliente SMTP con los detalles de su servidor SMTP y use el`Send` Método para enviar el mensaje.

```csharp
// Envíe el mensaje utilizando Aspose.Email.
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

## Conclusión

¡Felicidades! Convirtió con éxito un documento DOCX a MHTML y lo envió por correo electrónico utilizando Aspose.Words para .NET. Este proceso implica cargar el documento, convertirlo a MHTML, crear un mensaje de correo electrónico y enviarlo mediante un cliente SMTP. Con estos pasos, puede automatizar fácilmente la conversión y el envío por correo electrónico de documentos en sus aplicaciones.

## Preguntas frecuentes

### ¿Puedo utilizar este método para convertir otros formatos de documentos?
Sí, Aspose.Words admite varios formatos y puede convertir documentos como DOC, DOCX, RTF y más a MHTML.

### ¿Cómo puedo agregar archivos adjuntos al correo electrónico?
 Puedes usar el`Attachments` propiedad de la`MailMessage`class para agregar archivos adjuntos a su correo electrónico.

### ¿Aspose.Words es compatible con .NET Core?
Sí, Aspose.Words es compatible con .NET Core. También puede usarlo en aplicaciones .NET Core.

### ¿Necesito una licencia para Aspose.Words y Aspose.Email?
 Sí, ambas bibliotecas requieren licencias. Puede obtener una licencia temporal del[Aspose página de compra](https://purchase.aspose.com/temporary-license/) para fines de evaluación.

### ¿Dónde puedo encontrar más documentación?
 Puede encontrar documentación detallada para Aspose.Words[aquí](https://reference.aspose.com/words/net/) y para Aspose.Email[aquí](https://reference.aspose.com/email/net/).
