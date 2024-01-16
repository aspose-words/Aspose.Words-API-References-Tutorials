---
title: Update laatst opgeslagen tijdeigenschap
linktitle: Update laatst opgeslagen tijdeigenschap
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de eigenschap Laatst opgeslagen tijd automatisch bijwerkt wanneer u een document opslaat met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
In deze zelfstudie verkennen we de meegeleverde C#-broncode om de laatste tijdseigenschap bij te werken bij het opslaan van een document met Aspose.Words voor .NET. Met deze functie kunt u automatisch de laatste opslagtijdeigenschap van het gegenereerde document bijwerken.

## Stap 1: De omgeving instellen

Zorg ervoor dat u, voordat u begint, uw ontwikkelomgeving hebt ingesteld met Aspose.Words voor .NET. Zorg ervoor dat u de benodigde referenties hebt toegevoegd en de juiste naamruimten hebt geïmporteerd.

## Stap 2: Het document laden

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 In deze stap laden we het document met behulp van de`Document` methode en geef het pad door naar het DOCX-bestand dat moet worden geladen.

## Stap 3: OOXML-back-upopties configureren

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 In deze stap configureren we de OOXML-opslagopties met behulp van de`OoxmlSaveOptions` klas. We maken het automatisch bijwerken van de laatste opgeslagen tijd-eigenschap mogelijk door in te stellen`UpdateLastSavedTimeProperty` naar`true`.

## Stap 4: Document opslaan met bijgewerkte eigenschap

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 In deze laatste stap slaan we het document op met behulp van de`Save` methode en geef het pad door naar het uitvoerbestand met de`.docx` extensie, samen met de opgegeven opslagopties.

Nu kunt u de broncode uitvoeren om automatisch de laatste opslagtijdeigenschap bij te werken bij het opslaan van een document. Het resulterende bestand wordt opgeslagen in de opgegeven map met de naam "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### Voorbeeldbroncode voor Update Last Saved Time Property met Aspose.Words voor .NET 

```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Conclusie

In deze zelfstudie hebben we de functie onderzocht van het automatisch bijwerken van de laatste opslagtijdeigenschap bij het opslaan van een document met Aspose.Words voor .NET. Door deze functie in te schakelen met OOXML-opslagopties, kunt u ervoor zorgen dat de laatste opslagtijdeigenschap automatisch wordt bijgewerkt in het gegenereerde document.

Het bijwerken van de laatste opslagtijdeigenschap kan handig zijn voor het bijhouden van wijzigingen en versies van een document. Het houdt ook bij wanneer het document voor het laatst is opgeslagen, wat handig kan zijn in verschillende scenario's.

Aspose.Words voor .NET maakt het eenvoudig om de eigenschap Laatste back-uptijd automatisch bij te werken door flexibele en krachtige back-upopties te bieden. U kunt deze functie in uw projecten integreren om ervoor te zorgen dat gegenereerde documenten nauwkeurige back-upinformatie hebben.