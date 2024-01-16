---
title: Afbeeldingsopsommingsteken niet opslaan
linktitle: Afbeeldingsopsommingsteken niet opslaan
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u het opslaan van opsommingstekens in Word-documenten kunt uitschakelen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Afbeeldingsopsommingstekens zijn een veelgebruikte functie in Word-documenten om aangepaste opsommingstekens toe te voegen. In sommige gevallen kan het echter nodig zijn om de registratie van opsommingstekens uit te schakelen bij het manipuleren van documenten met behulp van de Aspose.Words-bibliotheek voor .NET. In deze stapsgewijze handleiding leggen we uit hoe u de Aspose.Words C#-broncode voor .NET kunt gebruiken om het opslaan van afbeeldingen opsommingstekens uit te schakelen met behulp van de DocSaveOptions-opslagopties.

## Inzicht in de Aspose.Words-bibliotheek

Voordat u in de code duikt, is het belangrijk dat u de Aspose.Words-bibliotheek voor .NET begrijpt. Aspose.Words is een krachtige bibliotheek voor het maken, bewerken, converteren en beschermen van Word-documenten op verschillende platforms, waaronder .NET. Het biedt veel functies voor het manipuleren van documenten, zoals het invoegen van tekst, het wijzigen van de opmaak, het toevoegen van secties en nog veel meer.

## Stap 1: De documentenmap instellen

De eerste stap is het definiëren van de map waarin uw documenten zich bevinden. U moet het volledige mappad opgeven. Bijvoorbeeld :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 2: Het document met opsommingstekens laden

Vervolgens moet u het document met afbeeldingsopsommingstekens laden. Gebruik de klasse Document om het document uit een bestand te laden. Bijvoorbeeld :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

In dit voorbeeld laden we het document uit het bestand "Afbeelding opsommingstekens.docx"

  bevindt zich in de documentenmap.

## Stap 3: Configureer opnameopties

Laten we nu de opslagopties voor ons document configureren. Gebruik de klasse DocSaveOptions om opslaginstellingen op te geven. Bijvoorbeeld :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

In dit voorbeeld maken we een nieuw DocSaveOptions-object en stellen we de eigenschap SavePictureBullet in op false om het opslaan van afbeeldingsopsommingstekens uit te schakelen.

## Stap 4: Schakel de functie "Afbeeldingbulletin niet opslaan" in

Om de functie "Afbeeldingbullet niet opslaan" in te schakelen, hebben we de opslagopties al geconfigureerd met SavePictureBullet ingesteld op false. Dit zorgt ervoor dat afbeeldingsopsommingstekens niet worden opgeslagen in het uiteindelijke document.

## Stap 5: Sla het document op

Ten slotte kunt u het document opslaan met de Save-methode van de Document-klasse. Geef het volledige pad naar het bestand en de gewenste bestandsnaam op. Bijvoorbeeld :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Zorg ervoor dat u "dataDir" vervangt door het mappad naar uw documenten.

## Voorbeeldbroncode voor DocSaveOptions-opslagopties met de functionaliteit "Picture Bullet niet opslaan" met behulp van Aspose.Words voor .NET

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document met afbeeldingsopsommingstekens
Document doc = new Document(dataDir + "Image bullet points.docx");

// Configureer de opslagopties met de functie "Picture Bullet niet opslaan".
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Sla het document op met de opgegeven opties
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Conclusie

In deze handleiding hebben we besproken hoe u het opslaan van afbeeldingsopsommingstekens in een document kunt uitschakelen met behulp van de Aspose.Words-bibliotheek voor .NET. Door de meegeleverde stappen te volgen en de meegeleverde C#-broncode te gebruiken, kunt u deze functionaliteit eenvoudig toepassen in uw C#-applicatie. Het uitschakelen van het opslaan van opsommingstekens kan in sommige situaties nuttig zijn om de documentstructuur en opmaak te behouden zonder opsommingstekens op te slaan.