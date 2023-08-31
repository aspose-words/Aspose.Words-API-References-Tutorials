---
title: Convertir Docx a Mhtml y enviar correo electrónico
linktitle: Convertir Docx a Mhtml y enviar correo electrónico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo convertir documentos de Word de Docx a MHTML y enviarlos como correos electrónicos usando Aspose.Words y Aspose.Email. Tutorial paso a paso.
type: docs
weight: 10
url: /es/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para convertir un documento de Word en formato Docx a MHTML y enviarlo como correo electrónico usando Aspose.Email. Explicaremos el código fuente C# proporcionado y le mostraremos cómo implementarlo en sus propios proyectos.

 Para comenzar, asegúrese de tener instaladas y configuradas las bibliotecas Aspose.Words para .NET y Aspose.Email en su entorno de desarrollo. Si no lo ha hecho, descargue e instale las bibliotecas desde[Lanzamientos.Aspose](https://releases.aspose.com/words/net/).

## Paso 1: Inicializar el objeto del documento

 Primero, inicialice el`Document`objeto con la ruta a su documento fuente en formato Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Paso 2: guardar el documento en formato MHTML

 A continuación, guarde el documento en un`Stream` objeto en formato MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Paso 3: rebobinar la transmisión

Dado que Aspose.Email necesita leer la transmisión desde el principio, rebobine la transmisión hasta el principio:

```csharp
stream.Position = 0;
```

## Paso 4: Crear un mensaje MIME de Aspose.Email

 Crear un`MailMessage` objeto de la secuencia usando`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

No dude en personalizar las propiedades del mensaje, como el remitente, el destinatario y el asunto.

## Paso 5: enviar el correo electrónico

 Utilice Aspose.Email`SmtpClient` para enviar el correo electrónico:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Asegúrese de proporcionar la dirección de host del servidor SMTP correcta.

¡Eso es todo! Ha convertido con éxito un documento de Word en formato Docx a MHTML y lo ha enviado como correo electrónico utilizando Aspose.Words para .NET y Aspose.Email.

### Código fuente de ejemplo para Docx a Mhtml y envío de correo electrónico utilizando Aspose.Words para .NET

```csharp

	// Documento doc = nuevo documento (MyDir + "Documento.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//Rebobina la transmisión hasta el principio para que Aspose.Email pueda leerla.
	stream.Position = 0;

	// Cree un mensaje de correo electrónico Aspose.Email MIME desde la secuencia.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Envíe el mensaje utilizando Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

No dude en utilizar este código en sus propios proyectos y modificarlo según sus requisitos específicos.

### Preguntas frecuentes

#### ¿Cómo convertir un archivo DOCX a MHTML?

Para convertir un archivo DOCX a MHTML, puede utilizar herramientas de software o bibliotecas que proporcionen esta funcionalidad. Aspose.Words para .NET es una opción confiable para esta conversión. Puede utilizar la API de la biblioteca para cargar el archivo DOCX y guardarlo en formato MHTML.

#### ¿Cómo envío un correo electrónico con un archivo adjunto MHTML?

Para enviar un correo electrónico con un archivo MHTML como archivo adjunto, puede utilizar bibliotecas o herramientas específicas para el envío de correo electrónico, como System.Net.Mail en .NET. Debe crear un mensaje de correo electrónico, especificar el destinatario, el asunto y el contenido y luego agregar el archivo MHTML como archivo adjunto al mensaje antes de enviarlo.

#### ¿Cuáles son las limitaciones del proceso de conversión y envío de correo electrónico?

Las limitaciones del proceso de conversión y envío de correo electrónico dependen de las herramientas específicas que esté utilizando. Algunas herramientas pueden tener restricciones relacionadas con el tamaño del archivo, la configuración de seguridad o los protocolos de correo electrónico compatibles. Es importante elegir herramientas que se adapten a sus necesidades y considerar estas limitaciones al implementarlas.

#### ¿Es Aspose una herramienta confiable para la conversión de DOCX a MHTML y el envío de correo electrónico?

Sí, Aspose.Words para .NET es una herramienta confiable para la conversión de DOCX a MHTML y el envío de correo electrónico. Es muy utilizado por desarrolladores y profesionales por su rendimiento y calidad. La herramienta ofrece documentación completa, funciones avanzadas y soporte técnico dedicado, lo que la convierte en una opción recomendada para estas tareas.