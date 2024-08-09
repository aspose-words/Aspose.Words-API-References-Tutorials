---
title: Converti Docx in Mhtml e invia e-mail
linktitle: Converti Docx in Mhtml e invia e-mail
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come convertire DOCX in MHTML e inviare e-mail utilizzando Aspose.Words per .NET in questa guida passo passo. Aumenta la tua produttività con una semplice automazione.
type: docs
weight: 10
url: /it/net/basic-conversions/docx-to-mhtml-and-sending-email/
---
## Introduzione

Nell'era digitale di oggi, convertire documenti da un formato all'altro e inviarli via e-mail è un compito comune. Questo articolo ti guiderà attraverso il processo di conversione di un file DOCX in formato MHTML e quindi di invio come e-mail utilizzando Aspose.Words per .NET. Analizzeremo ogni passaggio in una guida dettagliata e facile da seguire, assicurandoti di comprendere il processo dall'inizio alla fine. Immergiamoci!

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1. Aspose.Words per .NET: scarica e installa la libreria Aspose.Words per .NET dal[Pagina delle versioni di Aspose](https://releases.aspose.com/words/net/).
2.  Aspose.Email per .NET: scarica e installa la libreria Aspose.Email per .NET da[Pagina delle versioni di Aspose](https://releases.aspose.com/email/net/).
3. .NET Framework: assicurati di avere .NET Framework installato sul tuo computer.
4. Server SMTP: è necessario accedere a un server SMTP per inviare e-mail.

## Importa spazi dei nomi

Per utilizzare Aspose.Words e Aspose.Email nel tuo progetto, devi importare gli spazi dei nomi necessari. Aggiungi le seguenti direttive using nella parte superiore del file C#:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Clients.Smtp;
```

Suddividiamo il processo in più passaggi per assicurarci di comprendere chiaramente ogni parte.

## Passaggio 1: caricare il documento DOCX

 Innanzitutto, devi caricare il documento DOCX che desideri convertire. Usa il`Document` classe da Aspose.Words per caricare il file DOCX.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Passaggio 2: salva il documento come MHTML

 Successivamente, salva il documento caricato come file MHTML. Questo viene fatto utilizzando il`Save` metodo del`Document` classe.

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);

// Riavvolgere il flusso all'inizio in modo che Aspose.Email possa leggerlo.
stream.Position = 0;
```

## Passaggio 3: crea un messaggio e-mail

Ora crea un messaggio di posta elettronica dal flusso MHTML utilizzando Aspose.Email. Utilizzerai il`MailMessage` classe a questo scopo.

```csharp
// Creare un messaggio di posta elettronica MIME Aspose.Email dal flusso.
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

## Passaggio 4: invia l'e-mail

 Infine, invia l'e-mail utilizzando un client SMTP. Configura il client SMTP con i dettagli del tuo server SMTP e utilizza il file`Send` metodo per inviare il messaggio.

```csharp
// Invia il messaggio utilizzando Aspose.Email.
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

## Conclusione

Congratulazioni! Hai convertito con successo un documento DOCX in MHTML e lo hai inviato via e-mail utilizzando Aspose.Words per .NET. Questo processo prevede il caricamento del documento, la sua conversione in MHTML, la creazione di un messaggio di posta elettronica e l'invio tramite un client SMTP. Con questi passaggi puoi automatizzare facilmente la conversione e l'invio tramite posta elettronica dei documenti nelle tue applicazioni.

## Domande frequenti

### Posso utilizzare questo metodo per convertire altri formati di documento?
Sì, Aspose.Words supporta vari formati e puoi convertire documenti come DOC, DOCX, RTF e altri in MHTML.

### Come posso aggiungere allegati all'e-mail?
 Puoi usare il`Attachments` proprietà del`MailMessage`lezione per aggiungere allegati alla tua email.

### Aspose.Words è compatibile con .NET Core?
Sì, Aspose.Words è compatibile con .NET Core. È possibile usarlo anche nelle applicazioni .NET Core.

### Ho bisogno di una licenza per Aspose.Words e Aspose.Email?
 Sì, entrambe le biblioteche richiedono licenze. Puoi ottenere una licenza temporanea da[Aspose la pagina di acquisto](https://purchase.aspose.com/temporary-license/) a fini di valutazione.

### Dove posso trovare ulteriore documentazione?
 È possibile trovare la documentazione dettagliata per Aspose.Words[Qui](https://reference.aspose.com/words/net/) e per Aspose.Email[Qui](https://reference.aspose.com/email/net/).
