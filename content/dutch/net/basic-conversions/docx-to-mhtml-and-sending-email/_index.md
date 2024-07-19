---
title: Converteer Docx naar Mhtml en verzend e-mail
linktitle: Converteer Docx naar Mhtml en verzend e-mail
second_title: Aspose.Words-API voor documentverwerking
description: Leer in deze stapsgewijze handleiding hoe u DOCX naar MHTML converteert en e-mails verzendt met Aspose.Words voor .NET. Verhoog uw productiviteit met eenvoudige automatisering.
type: docs
weight: 10
url: /nl/net/basic-conversions/docx-to-mhtml-and-sending-email/
---
## Invoering

In het huidige digitale tijdperk is het converteren van documenten van het ene formaat naar het andere en het verzenden ervan via e-mail een veel voorkomende taak. Dit artikel leidt u door het proces van het converteren van een DOCX-bestand naar het MHTML-formaat en het vervolgens als e-mail verzenden met Aspose.Words voor .NET. We zetten elke stap uiteen in een gedetailleerde, eenvoudig te volgen handleiding, zodat u het proces van begin tot eind begrijpt. Laten we erin duiken!

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

1. Aspose.Words voor .NET: Download en installeer de Aspose.Words voor .NET-bibliotheek van de[Aspose-releasespagina](https://releases.aspose.com/words/net/).
2.  Aspose.Email voor .NET: Download en installeer de Aspose.Email voor .NET-bibliotheek van de[Aspose-releasespagina](https://releases.aspose.com/email/net/).
3. .NET Framework: Zorg ervoor dat .NET Framework op uw computer is geïnstalleerd.
4. SMTP-server: U hebt toegang tot een SMTP-server nodig om e-mails te verzenden.

## Naamruimten importeren

Om Aspose.Words en Aspose.Email in uw project te gebruiken, moet u de benodigde naamruimten importeren. Voeg het volgende toe met behulp van richtlijnen bovenaan uw C#-bestand:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Clients.Smtp;
```

Laten we het proces in meerdere stappen opsplitsen, zodat u elk onderdeel duidelijk begrijpt.

## Stap 1: Laad het DOCX-document

 Eerst moet u het DOCX-document laden dat u wilt converteren. Gebruik de`Document` class uit Aspose.Words om uw DOCX-bestand te laden.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Stap 2: Sla het document op als MHTML

 Sla vervolgens het geladen document op als een MHTML-bestand. Dit gebeurt met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);

// Spoel de stream terug naar het begin, zodat Aspose.Email deze kan lezen.
stream.Position = 0;
```

## Stap 3: Maak een e-mailbericht

Maak nu een e-mailbericht vanuit de MHTML-stream met behulp van Aspose.Email. Je gebruikt de`MailMessage` klasse voor dit doel.

```csharp
// Maak een Aspose.Email MIME-e-mailbericht vanuit de stream.
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

## Stap 4: Verzend de e-mail

 Verstuur de e-mail ten slotte via een SMTP-client. Configureer de SMTP-client met uw SMTP-servergegevens en gebruik de`Send` methode om het bericht te verzenden.

```csharp
// Verzend het bericht met Aspose.Email.
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

## Conclusie

Gefeliciteerd! U hebt met succes een DOCX-document naar MHTML geconverteerd en via e-mail verzonden met Aspose.Words voor .NET. Dit proces omvat het laden van het document, het converteren naar MHTML, het maken van een e-mailbericht en het verzenden ervan met behulp van een SMTP-client. Met deze stappen kunt u eenvoudig de conversie en e-mailing van documenten in uw applicaties automatiseren.

## Veelgestelde vragen

### Kan ik deze methode gebruiken om andere documentformaten te converteren?
Ja, Aspose.Words ondersteunt verschillende indelingen en u kunt documenten zoals DOC, DOCX, RTF en meer naar MHTML converteren.

### Hoe kan ik bijlagen toevoegen aan de e-mail?
 U kunt gebruik maken van de`Attachments` eigendom van de`MailMessage`class om bijlagen aan uw e-mail toe te voegen.

### Is Aspose.Words compatibel met .NET Core?
Ja, Aspose.Words is compatibel met .NET Core. U kunt het ook gebruiken in .NET Core-toepassingen.

### Heb ik een licentie nodig voor Aspose.Words en Aspose.Email?
 Ja, voor beide bibliotheken zijn licenties vereist. U kunt een tijdelijke licentie aanvragen bij de[Aspose aankooppagina](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.

### Waar kan ik meer documentatie vinden?
 U kunt gedetailleerde documentatie voor Aspose.Words vinden[hier](https://reference.aspose.com/words/net/) en voor Aspose.Email[hier](https://reference.aspose.com/email/net/).
