---
title: Converti Docx in Mhtml e invia e-mail
linktitle: Converti Docx in Mhtml e invia e-mail
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come convertire documenti Word da Docx a MHTML e inviarli come e-mail utilizzando Aspose.Words e Aspose.Email. Tutorial passo dopo passo.
type: docs
weight: 10
url: /it/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

In questo tutorial passo passo, ti guideremo su come utilizzare Aspose.Words per .NET per convertire un documento Word in formato Docx in MHTML e inviarlo come e-mail utilizzando Aspose.Email. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

 Per iniziare, assicurati di avere entrambe le librerie Aspose.Words per .NET e Aspose.Email installate e configurate nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa le librerie da[Aspose.Releases](https://releases.aspose.com/words/net/).

## Passaggio 1: inizializzazione dell'oggetto documento

 Innanzitutto, inizializza il file`Document`oggetto con il percorso del documento di origine in formato Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Passaggio 2: salvataggio del documento in formato MHTML

 Quindi, salva il documento in un file`Stream` oggetto in formato MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Passaggio 3: riavvolgimento dello streaming

Poiché Aspose.Email deve leggere il flusso dall'inizio, riavvolgi il flusso all'inizio:

```csharp
stream.Position = 0;
```

## Passaggio 4: creazione di un messaggio MIME Aspose.Email

 Creare un`MailMessage` oggetto dallo stream utilizzando`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Sentiti libero di personalizzare le proprietà del messaggio come mittente, destinatario e oggetto.

## Passaggio 5: invio dell'e-mail

 Utilizzare Aspose.Email`SmtpClient` per inviare l'e-mail:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Assicurati di fornire l'indirizzo host del server SMTP corretto.

Questo è tutto! Hai convertito con successo un documento Word in formato Docx in MHTML e lo hai inviato come email utilizzando Aspose.Words per .NET e Aspose.Email.

### Codice sorgente di esempio per Docx To Mhtml e invio di e-mail utilizzando Aspose.Words per .NET

```csharp

	// Documento doc = nuovo Documento(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//Riavvolgere il flusso all'inizio in modo che Aspose.Email possa leggerlo.
	stream.Position = 0;

	// Creare un messaggio di posta elettronica MIME Aspose.Email dal flusso.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Invia il messaggio utilizzando Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e modificarlo in base alle tue esigenze specifiche.

### Domande frequenti

#### Come convertire un file DOCX in MHTML?

Per convertire un file DOCX in MHTML, puoi utilizzare strumenti software o librerie che forniscono questa funzionalità. Aspose.Words per .NET è un'opzione affidabile per questa conversione. Puoi utilizzare l'API della libreria per caricare il file DOCX e salvarlo in formato MHTML.

#### Come posso inviare un'e-mail con un file MHTML allegato?

Per inviare un'e-mail con un file MHTML come allegato, è possibile utilizzare librerie o strumenti specifici per l'invio di e-mail, come System.Net.Mail in .NET. È necessario creare un messaggio e-mail, specificare il destinatario, l'oggetto e il contenuto, quindi aggiungere il file MHTML come allegato al messaggio prima di inviarlo.

#### Quali sono i limiti del processo di conversione e invio delle email?

Le limitazioni del processo di conversione e invio delle email dipendono dagli strumenti specifici che stai utilizzando. Alcuni strumenti potrebbero avere restrizioni relative alla dimensione del file, alle impostazioni di sicurezza o ai protocolli di posta elettronica supportati. È importante scegliere gli strumenti adatti alle proprie esigenze e considerare queste limitazioni durante l'implementazione.

#### Aspose è uno strumento affidabile per la conversione da DOCX a MHTML e l'invio di e-mail?

Sì, Aspose.Words per .NET è uno strumento affidabile per la conversione da DOCX a MHTML e l'invio di e-mail. È ampiamente utilizzato da sviluppatori e professionisti per le sue prestazioni e qualità. Lo strumento offre documentazione completa, funzionalità avanzate e supporto tecnico dedicato, rendendolo una scelta consigliata per queste attività.