---
title: Docx To Mhtml And Sending Email
linktitle: Docx To Mhtml And Sending Email
second_title: Aspose.Words for .NET API Reference
description: Learn how to convert Word documents from Docx to MHTML and send them as emails using Aspose.Words and Aspose.Email. Step-by-step tutorial.
type: docs
weight: 10
url: /net/basic-conversions/docx-to-mhtml-and-sending-email/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to convert a Word document in Docx format to MHTML and send it as an email using Aspose.Email. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, ensure that you have both Aspose.Words for .NET and Aspose.Email libraries installed and set up in your development environment. If you haven't done so, download and install the libraries from their official websites.

## Step 1: Initializing the Document Object

First, initialize the `Document` object with the path to your source document in Docx format:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Step 2: Saving the Document in MHTML Format

Next, save the document to a `Stream` object in MHTML format:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Step 3: Rewinding the Stream

Since Aspose.Email needs to read the stream from the beginning, rewind the stream to the beginning:

```csharp
stream.Position = 0;
```

## Step 4: Creating an Aspose.Email MIME Message

Create a `MailMessage` object from the stream using `MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Feel free to customize the message properties such as the sender, recipient, and subject.

## Step 5: Sending the Email

Use Aspose.Email's `SmtpClient` to send the email:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Ensure that you provide the correct SMTP server host address.

That's it! You have successfully converted a Word document in Docx format to MHTML and sent it as an email using Aspose.Words for .NET and Aspose.Email.

### Example source code for Docx To Mhtml And Sending Email using Aspose.Words for .NET

```csharp

	// Document doc = new Document(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	// Rewind the stream to the beginning so Aspose.Email can read it.
	stream.Position = 0;

	// Create an Aspose.Email MIME email message from the stream.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Send the message using Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Feel free to use this code in your own projects and modify it according to your specific requirements.
