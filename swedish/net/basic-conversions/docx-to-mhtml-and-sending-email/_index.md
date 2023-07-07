---
title: Konvertera Docx till Mhtml och skicka e-post
linktitle: Konvertera Docx till Mhtml och skicka e-post
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du konverterar Word-dokument från Docx till MHTML och skickar dem som e-post med Aspose.Words och Aspose.Email. Steg-för-steg handledning.
type: docs
weight: 10
url: /sv/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att konvertera ett Word-dokument i Docx-format till MHTML och skicka det som ett e-postmeddelande med Aspose.Email. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har både Aspose.Words for .NET och Aspose.Email-biblioteken installerade och inställda i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteken från deras officiella webbplatser.

## Steg 1: Initiera dokumentobjektet

 Initiera först`Document` objekt med sökvägen till ditt källdokument i Docx-format:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Steg 2: Spara dokumentet i MHTML-format

 Spara sedan dokumentet till en`Stream` objekt i MHTML-format:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Steg 3: Spola tillbaka strömmen

Eftersom Aspose.Email behöver läsa strömmen från början, spola tillbaka strömmen till början:

```csharp
stream.Position = 0;
```

## Steg 4: Skapa ett Aspose.Email MIME-meddelande

 Skapa en`MailMessage` objekt från strömmen med hjälp av`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Anpassa gärna meddelandeegenskaperna som avsändare, mottagare och ämne.

## Steg 5: Skicka e-postmeddelandet

 Använd Aspose.Email's`SmtpClient` för att skicka e-postmeddelandet:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Se till att du anger rätt SMTP-servervärdadress.

Det är allt! Du har framgångsrikt konverterat ett Word-dokument i Docx-format till MHTML och skickat det som ett e-postmeddelande med Aspose.Words för .NET och Aspose.Email.

### Exempel på källkod för Docx till Mhtml och skicka e-post med Aspose.Words för .NET

```csharp

	// Document doc = new Document(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	// Spola tillbaka strömmen till början så att Aspose.Email kan läsa den.
	stream.Position = 0;

	// Skapa ett Aspose.Email MIME-e-postmeddelande från strömmen.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Skicka meddelandet med Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.

### Vanliga frågor

#### Hur konverterar man en DOCX-fil till MHTML?

För att konvertera en DOCX-fil till MHTML kan du använda programvaruverktyg eller bibliotek som tillhandahåller denna funktionalitet. Aspose.Words för .NET är ett tillförlitligt alternativ för denna konvertering. Du kan använda bibliotekets API för att ladda DOCX-filen och spara den i MHTML-format.

#### Hur skickar jag ett e-postmeddelande med en MHTML-filbilaga?

För att skicka ett e-postmeddelande med en MHTML-fil som en bilaga kan du använda bibliotek eller verktyg som är specifika för e-postsändning, som System.Net.Mail i .NET. Du måste skapa ett e-postmeddelande, ange mottagare, ämne och innehåll och sedan lägga till MHTML-filen som en bilaga till meddelandet innan du skickar det.

#### Vilka är begränsningarna för e-postkonvertering och sändningsprocessen?

Begränsningarna för e-postkonvertering och sändningsprocessen beror på de specifika verktyg du använder. Vissa verktyg kan ha begränsningar relaterade till filstorlek, säkerhetsinställningar eller e-postprotokoll som stöds. Det är viktigt att välja verktyg som passar dina behov och överväga dessa begränsningar vid implementering.

#### Är Aspose ett pålitligt verktyg för DOCX till MHTML-konvertering och e-postsändning?

Ja, Aspose.Words för .NET är ett tillförlitligt verktyg för DOCX till MHTML-konvertering och e-postsändning. Det används ofta av utvecklare och proffs för dess prestanda och kvalitet. Verktyget erbjuder omfattande dokumentation, avancerade funktioner och dedikerad teknisk support, vilket gör det till ett rekommenderat val för dessa uppgifter.