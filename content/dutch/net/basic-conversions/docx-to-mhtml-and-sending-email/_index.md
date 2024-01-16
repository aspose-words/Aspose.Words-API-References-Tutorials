---
title: Converteer Docx naar Mhtml en verzend e-mail
linktitle: Converteer Docx naar Mhtml en verzend e-mail
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Word-documenten converteert van Docx naar MHTML en deze als e-mails verzendt met Aspose.Words en Aspose.Email. Stapsgewijze zelfstudie.
type: docs
weight: 10
url: /nl/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

In deze stapsgewijze zelfstudie laten we u zien hoe u Aspose.Words voor .NET kunt gebruiken om een Word-document in Docx-indeling naar MHTML te converteren en als e-mail te verzenden met Aspose.Email. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze in uw eigen projecten kunt implementeren.

 Om aan de slag te gaan, moet u ervoor zorgen dat u zowel de Aspose.Words voor .NET- als de Aspose.Email-bibliotheken in uw ontwikkelomgeving hebt geïnstalleerd en ingesteld. Als u dit nog niet hebt gedaan, downloadt en installeert u de bibliotheken van[Aspose.Releases](https://releases.aspose.com/words/net/).

## Stap 1: Het documentobject initialiseren

 Initialiseer eerst de`Document`object met het pad naar uw brondocument in Docx-indeling:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Stap 2: Het document opslaan in MHTML-indeling

 Sla het document vervolgens op in een`Stream` object in MHTML-indeling:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Stap 3: De stream terugspoelen

Omdat Aspose.Email de stream vanaf het begin moet lezen, spoelt u de stream terug naar het begin:

```csharp
stream.Position = 0;
```

## Stap 4: Een Aspose.Email MIME-bericht maken

 Maak een`MailMessage` object uit de stream gebruikt`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

U kunt de berichteigenschappen, zoals de afzender, de ontvanger en het onderwerp, gerust aanpassen.

## Stap 5: De e-mail verzenden

 Gebruik Aspose.Email's`SmtpClient` om de e-mail te verzenden:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Zorg ervoor dat u het juiste SMTP-serverhostadres opgeeft.

Dat is het! U hebt met succes een Word-document in Docx-indeling naar MHTML geconverteerd en als e-mail verzonden met Aspose.Words voor .NET en Aspose.Email.

### Voorbeeldbroncode voor Docx naar Mhtml en het verzenden van e-mail met Aspose.Words voor .NET

```csharp

	// Documentdoc = nieuw document (Mijn map + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//Spoel de stream terug naar het begin, zodat Aspose.Email deze kan lezen.
	stream.Position = 0;

	// Maak een Aspose.Email MIME-e-mailbericht vanuit de stream.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Verzend het bericht met Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

U kunt deze code gerust in uw eigen projecten gebruiken en aanpassen aan uw specifieke vereisten.

### Veelgestelde vragen

#### Hoe converteer je een DOCX-bestand naar MHTML?

Om een DOCX-bestand naar MHTML te converteren, kunt u softwaretools of bibliotheken gebruiken die deze functionaliteit bieden. Aspose.Words voor .NET is een betrouwbare optie voor deze conversie. U kunt de bibliotheek-API gebruiken om het DOCX-bestand te laden en op te slaan in MHTML-indeling.

#### Hoe verzend ik een e-mail met een MHTML-bestandsbijlage?

Als u een e-mail wilt verzenden met een MHTML-bestand als bijlage, kunt u bibliotheken of hulpprogramma's gebruiken die specifiek zijn voor het verzenden van e-mail, zoals System.Net.Mail in .NET. U moet een e-mailbericht maken, de ontvanger, het onderwerp en de inhoud opgeven en vervolgens het MHTML-bestand als bijlage aan het bericht toevoegen voordat u het verzendt.

#### Wat zijn de beperkingen van het e-mailconversie- en verzendproces?

De beperkingen van het e-mailconversie- en verzendproces zijn afhankelijk van de specifieke tools die u gebruikt. Voor sommige tools kunnen beperkingen gelden met betrekking tot de bestandsgrootte, beveiligingsinstellingen of ondersteunde e-mailprotocollen. Het is belangrijk om tools te kiezen die bij uw behoeften passen en bij de implementatie rekening te houden met deze beperkingen.

#### Is Aspose een betrouwbaar hulpmiddel voor DOCX naar MHTML-conversie en het verzenden van e-mail?

Ja, Aspose.Words voor .NET is een betrouwbaar hulpmiddel voor DOCX naar MHTML-conversie en het verzenden van e-mail. Het wordt veel gebruikt door ontwikkelaars en professionals vanwege de prestaties en kwaliteit. De tool biedt uitgebreide documentatie, geavanceerde functies en toegewijde technische ondersteuning, waardoor het een aanbevolen keuze is voor deze taken.