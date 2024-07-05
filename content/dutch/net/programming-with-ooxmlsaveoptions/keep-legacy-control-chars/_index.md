---
title: Bewaar oude controletekens
linktitle: Bewaar oude controletekens
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u oudere stuurtekens kunt behouden bij het opslaan van een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

In deze zelfstudie verkennen we de meegeleverde C#-broncode om oudere stuurtekens te behouden bij het opslaan van een document met Aspose.Words voor .NET. Met deze functie kunt u speciale controletekens behouden bij het converteren of opslaan van een document.

## Stap 1: De omgeving instellen

Zorg ervoor dat u, voordat u begint, uw ontwikkelomgeving hebt ingesteld met Aspose.Words voor .NET. Zorg ervoor dat u de benodigde referenties hebt toegevoegd en de juiste naamruimten hebt geïmporteerd.

## Stap 2: Het document laden

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 In deze stap laden we het document met behulp van de`Document` methode en geef het pad door naar het bestand dat de overgenomen controletekens bevat.

## Stap 3: OOXML-back-upopties configureren

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

 In deze stap configureren we de OOXML-opslagopties door een nieuw`OoxmlSaveOptions` voorwerp. We specificeren het gewenste opslagformaat (hier`FlatOpc` ) en schakel de in`KeepLegacyControlChars` optie om oudere stuurtekens te behouden.

## Stap 4: Het document opslaan met oudere stuurtekens

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 In deze laatste stap slaan we het document op met behulp van de`Save` methode en geef het pad door naar het uitvoerbestand met de`.docx` extensie, samen met de opgegeven opslagopties.

Nu kunt u de broncode uitvoeren om oudere stuurtekens te behouden bij het opslaan van een document. Het resulterende bestand wordt opgeslagen in de opgegeven map met de naam "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Voorbeeldbroncode voor Keep Legacy Control Chars met Aspose.Words voor .NET 
```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Conclusie

In deze zelfstudie hebben we de functionaliteit onderzocht van het behouden van oudere stuurtekens bij het opslaan van een document met Aspose.Words voor .NET. We hebben geleerd hoe we de speciale tekens kunnen behouden die belangrijk kunnen zijn voor de juiste documentopmaak of weergave.

 Het behouden van oudere stuurtekens is vooral handig bij het verwerken van woorden met documenten die oudere of specifieke functies gebruiken, zoals speciale stuurtekens. Door het inschakelen van de`KeepLegacyControlChars` optie bij het opslaan van het document zorgt u ervoor dat deze tekens behouden blijven.

Aspose.Words voor .NET biedt een reeks flexibele en krachtige back-upopties om aan uw behoeften op het gebied van documentmanipulatie te voldoen. Door de juiste opties te gebruiken, kunt u het back-upproces aanpassen om de specifieke kenmerken van uw documenten te behouden.

Voel je vrij om deze functionaliteit op te nemen in je Aspose.Words voor .NET-projecten om de integriteit en het behoud van oudere stuurtekens in je documenten te garanderen.