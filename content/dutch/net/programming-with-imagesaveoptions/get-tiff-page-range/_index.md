---
title: TIFF-paginabereik ophalen
linktitle: TIFF-paginabereik ophalen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een reeks TIFF-pagina's kunt extraheren met Aspose.Words voor .NET. Volledige tutorial voor aangepaste TIFF-bestanden.
type: docs
weight: 10
url: /nl/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

In deze zelfstudie verkennen we de meegeleverde C#-broncode om een reeks TIFF-pagina's te krijgen met Aspose.Words voor .NET. Met deze functie kunt u een specifiek bereik aan pagina's uit een document extraheren en deze opslaan als een TIFF-bestand.

## Stap 1: De omgeving instellen

Zorg ervoor dat u, voordat u begint, uw ontwikkelomgeving hebt ingesteld met Aspose.Words voor .NET. Zorg ervoor dat u de benodigde referenties hebt toegevoegd en de juiste naamruimten hebt geïmporteerd.

## Stap 2: Het document laden

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 In deze stap laden we het document met behulp van de`Document` methode en geef het pad door naar het DOCX-bestand dat moet worden geladen.

## Stap 3: Het volledige document opslaan in TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

In deze stap slaan we het volledige document op in TIFF-formaat met behulp van de`Save` methode en specificeert het pad naar het uitvoerbestand met de extensie`.tiff`.

## Stap 4: Configureer back-upopties voor het paginabereik

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 In deze stap configureren we back-upopties voor het specifieke paginabereik. Wij creëren een nieuwe`ImageSaveOptions` object dat het gewenste opslagformaat specificeert, hier "Tiff" voor het TIFF-formaat. We gebruiken`PageSet` om het paginabereik te specificeren dat we willen extraheren, hier van pagina 0 tot pagina 1 (inclusief). We hebben ook de TIFF-compressie ingesteld op`Ccitt4` en de resolutie tot 160 dpi.

## Stap 5: Het paginabereik opslaan in TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 In deze laatste stap slaan we het opgegeven paginabereik op in TIFF-formaat met behulp van de`Save` methode en geef het pad door naar het uitvoerbestand met`.tiff` extensie, samen met de opgegeven opslagopties .

Nu kunt u de broncode uitvoeren om een specifiek paginabereik uit uw document te halen en deze op te slaan als een TIFF-bestand. De resulterende bestanden worden opgeslagen in de opgegeven map met de namen "WorkingWithImageSaveOptions.MultipageTiff.tiff" voor het volledige document en "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" voor het opgegeven paginabereik.

### Voorbeeldbroncode van Get Tiff Page Range met Aspose.Words voor .NET

```csharp 

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Conclusie

In deze zelfstudie hebben we de functionaliteit onderzocht van het verkrijgen van een reeks TIFF-pagina's met Aspose.Words voor .NET. We hebben geleerd hoe we een specifiek bereik aan pagina's uit een document kunnen extraheren en deze kunnen opslaan als een TIFF-bestand.

Deze functie is handig als u alleen bepaalde pagina's uit een document wilt extraheren en deze wilt opslaan in een standaard afbeeldingsformaat zoals TIFF. U kunt ook de compressie- en resolutie-opties aanpassen om TIFF-bestanden van de beste kwaliteit te krijgen.

Aspose.Words voor .NET biedt een uitgebreid scala aan geavanceerde functies voor documentmanipulatie en -generatie. Het verkrijgen van een TIFF-paginabereik is een van de vele krachtige hulpmiddelen die u ter beschikking krijgt.

Voel je vrij om deze functionaliteit te integreren in je Aspose.Words voor .NET-projecten om specifieke paginabereiken uit je documenten te extraheren en op te slaan in TIFF-formaat.