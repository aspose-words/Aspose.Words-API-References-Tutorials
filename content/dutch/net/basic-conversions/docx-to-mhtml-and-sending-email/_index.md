---
title: Converteer Docx naar Mhtml en verstuur e-mail
linktitle: Converteer Docx naar Mhtml en verstuur e-mail
second_title: Aspose.Words API voor documentverwerking
description: Leer hoe u DOCX naar MHTML converteert en e-mails verstuurt met Aspose.Words voor .NET in deze stapsgewijze handleiding. Verhoog uw productiviteit met eenvoudige automatisering.
type: docs
weight: 10
url: /nl/net/basic-conversions/docx-to-mhtml-and-sending-email/
---
## Invoering

In het digitale tijdperk van vandaag is het converteren van documenten van het ene formaat naar het andere en het verzenden ervan via e-mail een veelvoorkomende taak. Dit artikel leidt u door het proces van het converteren van een DOCX-bestand naar het MHTML-formaat en het vervolgens verzenden als een e-mail met Aspose.Words voor .NET. We zullen elke stap in een gedetailleerde, eenvoudig te volgen handleiding uiteenzetten, zodat u het proces van begin tot eind begrijpt. Laten we erin duiken!

## Vereisten

Voordat we beginnen, moet u ervoor zorgen dat aan de volgende voorwaarden is voldaan:

1.  Aspose.Words voor .NET: Download en installeer de Aspose.Words voor .NET-bibliotheek van de[Aspose releases pagina](https://releases.aspose.com/words/net/).
2.  Aspose.Email voor .NET: Download en installeer de Aspose.Email voor .NET-bibliotheek van de[Aspose releases pagina](https://releases.aspose.com/email/net/).
3. .NET Framework: Zorg ervoor dat .NET Framework op uw computer is geïnstalleerd.
4. SMTP-server: Om e-mails te kunnen versturen, hebt u toegang tot een SMTP-server nodig.

## Naamruimten importeren

Om Aspose.Words en Aspose.Email in uw project te gebruiken, moet u de benodigde naamruimten importeren. Voeg het volgende toe met behulp van richtlijnen boven aan uw C#-bestand:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Clients.Smtp;
```

Laten we het proces opsplitsen in meerdere stappen, zodat u zeker weet dat u elk onderdeel goed begrijpt.

## Stap 1: Laad het DOCX-document

 Eerst moet u het DOCX-document laden dat u wilt converteren. Gebruik de`Document` klasse van Aspose.Words om uw DOCX-bestand te laden.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Stap 2: Sla het document op als MHTML

 Sla vervolgens het geladen document op als een MHTML-bestand. Dit doet u met behulp van de`Save` methode van de`Document` klas.

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);

// Spoel de stream terug naar het begin, zodat Aspose.Email deze kan lezen.
stream.Position = 0;
```

## Stap 3: Maak een e-mailbericht

 Maak nu een e-mailbericht van de MHTML-stream met Aspose.Email. U gebruikt de`MailMessage` klasse voor dit doel.

```csharp
// Maak een Aspose.Email MIME e-mailbericht van de stream.
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

## Stap 4: Verstuur de e-mail

Verstuur ten slotte de e-mail met een SMTP-client. Configureer de SMTP-client met uw SMTP-servergegevens en gebruik de`Send` Methode om het bericht te versturen.

```csharp
// Verstuur het bericht met Aspose.Email.
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

## Conclusie

Gefeliciteerd! U hebt een DOCX-document succesvol geconverteerd naar MHTML en via e-mail verzonden met Aspose.Words voor .NET. Dit proces omvat het laden van het document, het converteren naar MHTML, het maken van een e-mailbericht en het verzenden ervan via een SMTP-client. Met deze stappen kunt u de conversie en het e-mailen van documenten in uw toepassingen eenvoudig automatiseren.

## Veelgestelde vragen

### Kan ik deze methode gebruiken om andere documentformaten te converteren?
Ja, Aspose.Words ondersteunt verschillende formaten en u kunt documenten zoals DOC, DOCX, RTF en meer converteren naar MHTML.

### Hoe kan ik bijlagen aan de e-mail toevoegen?
 U kunt de`Attachments` eigendom van de`MailMessage` klasse om bijlagen aan uw e-mail toe te voegen.

### Is Aspose.Words compatibel met .NET Core?
Ja, Aspose.Words is compatibel met .NET Core. U kunt het ook gebruiken in .NET Core-applicaties.

### Heb ik een licentie nodig voor Aspose.Words en Aspose.Email?
Ja, beide bibliotheken vereisen licenties. U kunt een tijdelijke licentie krijgen van de[Aspose aankooppagina](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.

### Waar kan ik meer documentatie vinden?
 Gedetailleerde documentatie voor Aspose.Words vindt u hier[hier](https://reference.aspose.com/words/net/) en voor Aspose.E-mail[hier](https://reference.aspose.com/email/net/).
