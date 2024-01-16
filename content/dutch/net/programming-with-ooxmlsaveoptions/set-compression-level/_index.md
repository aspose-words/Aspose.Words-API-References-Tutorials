---
title: Compressieniveau instellen
linktitle: Compressieniveau instellen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u het compressieniveau instelt wanneer u een document opslaat met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
In deze zelfstudie verkennen we de meegeleverde C#-broncode om het compressieniveau in te stellen bij het opslaan van een document met Aspose.Words voor .NET. Met deze functie kunt u het compressieniveau van het gegenereerde document regelen.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 In deze stap configureren we de OOXML-opslagopties met behulp van de`OoxmlSaveOptions` klas. We hebben het compressieniveau ingesteld op`SuperFast` om een snellere compressie te verkrijgen.

## Stap 4: Sla het document op met het opgegeven compressieniveau

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 In deze laatste stap slaan we het document op met behulp van de`Save` methode en geef het pad door naar het uitvoerbestand met de`.docx` extensie, samen met de opgegeven opslagopties.

Nu kunt u de broncode uitvoeren om het compressieniveau in te stellen bij het opslaan van een document. Het resulterende bestand wordt opgeslagen in de opgegeven map met de naam "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### Voorbeeldbroncode voor Compressieniveau instellen met Aspose.Words voor .NET 

```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Conclusie

In deze zelfstudie hebben we de functionaliteit onderzocht van het instellen van het compressieniveau bij het opslaan van een document met Aspose.Words voor .NET. Door het juiste compressieniveau op te geven, kunt u de documentgrootte en aanmaaksnelheid optimaliseren.

 De`OoxmlSaveOptions` class biedt flexibiliteit om het compressieniveau te regelen door de`CompressionLevel` eigendom tot een passende waarde, zoals`SuperFast`. Hierdoor kunt u de juiste balans vinden tussen bestandsgrootte en back-upsnelheid op basis van uw specifieke behoeften.

Het gebruik van compressie kan nuttig zijn als u de grootte van gegenereerde bestanden wilt verkleinen, vooral bij grote documenten. Dit kan het gemakkelijker maken om documenten op te slaan, te delen en te verzenden.

Aspose.Words voor .NET biedt een reeks krachtige opties en functies voor documentmanipulatie. Door de juiste back-upopties te gebruiken, kunt u het proces voor het genereren van documenten aanpassen en de prestaties van uw toepassing optimaliseren.

Ontdek gerust meer functies van Aspose.Words voor .NET om uw workflow voor het genereren van documenten te verbeteren.
