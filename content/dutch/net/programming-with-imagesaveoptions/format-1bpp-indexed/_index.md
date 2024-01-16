---
title: Formaat 1Bpp geïndexeerd
linktitle: Formaat 1Bpp geïndexeerd
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u afbeeldingen kunt opmaken in 1 bpp, geïndexeerd met Aspose.Words voor .NET. Volledige tutorial voor afbeeldingen met een lage kleurdiepte.
type: docs
weight: 10
url: /nl/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
In deze zelfstudie verkennen we de C#-broncode voor de functionaliteit "Format 1Bpp Indexed" met Aspose.Words voor .NET. Met deze functie kunt u afbeeldingen in een document opmaken in PNG-indeling met een kleurdiepte van 1 bit per pixel (1 bpp) en een geïndexeerde kleurmodus.

## Stap 1: De omgeving instellen

Zorg ervoor dat u, voordat u begint, uw ontwikkelomgeving hebt ingesteld met Aspose.Words voor .NET. Zorg ervoor dat u de benodigde referenties hebt toegevoegd en de juiste naamruimten hebt geïmporteerd.

## Stap 2: Het document laden

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 In deze stap laden we het document met behulp van de`Document` methode en geef het pad door naar het DOCX-bestand dat moet worden geladen.

## Stap 3: Configureer de back-upopties voor afbeeldingen

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 In deze stap configureren we back-upopties voor afbeeldingen. Wij creëren een nieuwe`ImageSaveOptions`object dat het gewenste opslagformaat specificeert, hier "Png" voor het PNG-formaat. We definiëren ook de pagina die in de afbeelding moet worden opgenomen, de zwart-witte kleurmodus en het geïndexeerde pixelformaat van 1 bpp.

## Stap 4: Een back-up maken van afbeeldingen

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 In deze laatste stap slaan we de documentafbeeldingen op in het PNG-formaat met behulp van de`Save` methode en geef het pad door naar het uitvoerbestand, samen met de opgegeven opslagopties.

Nu kunt u de broncode uitvoeren om de documentafbeeldingen op te maken in het PNG-formaat met een geïndexeerde kleurdiepte van 1 bpp. Het resulterende bestand wordt opgeslagen in de opgegeven map met de naam "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### Voorbeeldbroncode voor indeling 1Bpp Geïndexeerd met Aspose.Words voor .NET

```csharp 
 
			 // Pad naar uw documentmap
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Conclusie

In deze zelfstudie hebben we de 1Bpp Indexed-indelingsfunctie onderzocht met Aspose.Words voor .NET. We hebben geleerd hoe we afbeeldingen in een document kunnen opmaken in PNG-indeling met een kleurdiepte van 1 bit per pixel (1 bpp) en een geïndexeerde kleurmodus.

Deze functie is handig als u afbeeldingen wilt maken met een lage kleurdiepte en een kleine bestandsgrootte. Met het 1Bpp Indexed-formaat kunnen afbeeldingen worden weergegeven met behulp van een geïndexeerd kleurenpalet, wat nuttig kan zijn voor bepaalde specifieke toepassingen.

Aspose.Words voor .NET biedt een breed scala aan geavanceerde functies voor documentmanipulatie en -generatie. Het 1Bpp Indexed-formaat is een van de vele krachtige tools die het tot uw beschikking stelt.