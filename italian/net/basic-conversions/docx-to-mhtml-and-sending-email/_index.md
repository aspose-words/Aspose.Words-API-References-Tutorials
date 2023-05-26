---
title: Docx a Mhtml e invio di e-mail
linktitle: Docx a Mhtml e invio di e-mail
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come convertire i documenti di Word da Docx a MHTML e inviarli come e-mail utilizzando Aspose.Words e Aspose.Email. Tutorial passo dopo passo.
type: docs
weight: 10
url: /it/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

In questo tutorial passo-passo, ti guideremo su come utilizzare Aspose.Words per .NET per convertire un documento Word in formato Docx in MHTML e inviarlo come e-mail utilizzando Aspose.Email. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere entrambe le librerie Aspose.Words per .NET e Aspose.Email installate e configurate nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa le librerie dai loro siti Web ufficiali.

## Passaggio 1: inizializzazione dell'oggetto documento

 Per prima cosa, inizializza il file`Document` oggetto con il percorso del documento di origine in formato Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Passaggio 2: salvare il documento in formato MHTML

 Successivamente, salva il documento in a`Stream` oggetto in formato MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Passaggio 3: riavvolgimento dello stream

Poiché Aspose.Email deve leggere il flusso dall'inizio, riavvolgi il flusso all'inizio:

```csharp
stream.Position = 0;
```

## Passaggio 4: Creazione di un messaggio MIME Aspose.Email

 Creare un`MailMessage` oggetto dal flusso utilizzando`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Sentiti libero di personalizzare le proprietà del messaggio come mittente, destinatario e oggetto.

## Passaggio 5: invio dell'e-mail

 Usa Aspose.Email`SmtpClient` per inviare la mail:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Assicurati di fornire l'indirizzo host del server SMTP corretto.

Questo è tutto! Hai convertito con successo un documento Word in formato Docx in MHTML e lo hai inviato come e-mail utilizzando Aspose.Words per .NET e Aspose.Email.

### Codice sorgente di esempio per Docx To Mhtml e invio di e-mail utilizzando Aspose.Words per .NET

```csharp

	// Documento doc = new Document(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	// Riavvolgi il flusso all'inizio in modo che Aspose.Email possa leggerlo.
	stream.Position = 0;

	// Crea un messaggio e-mail MIME Aspose.Email dallo stream.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Invia il messaggio utilizzando Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.