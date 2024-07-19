---
title: Jpeg-paginabereik ophalen
linktitle: Jpeg-paginabereik ophalen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een reeks JPEG-pagina's kunt verkrijgen met Aspose.Words voor .NET. Volledige tutorial voor het extraheren van aangepaste afbeeldingen.
type: docs
weight: 10
url: /nl/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

In deze zelfstudie verkennen we de C#-broncode voor de functie "Bereik bereik van JPEG-pagina's ophalen" met Aspose.Words voor .NET. Met deze functie kunt u een specifiek paginabereik van een document converteren naar afbeeldingen in JPEG-indeling.

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
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 In deze stap configureren we back-upopties voor afbeeldingen. Wij creëren een nieuwe`ImageSaveOptions` object dat het gewenste opslagformaat specificeert, hier "Jpeg" voor het JPEG-formaat. We stellen ook het bereik van de pagina's in die moeten worden geconverteerd met behulp van de`PageSet`voorwerp. Ten slotte passen we de helderheid en het contrast van de afbeelding aan met behulp van de`ImageBrightness`En`ImageContrast` eigenschappen, respectievelijk. We veranderen ook de horizontale resolutie met behulp van de`HorizontalResolution` eigendom.

## Stap 4: Een back-up maken van afbeeldingen

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 In deze laatste stap slaan we de afbeeldingen van het opgegeven paginabereik op in het JPEG-formaat met behulp van de`Save` methode en geef het pad door naar het uitvoerbestand, samen met de opgegeven opslagopties.

Nu kunt u de broncode uitvoeren om een specifiek paginabereik in uw document naar JPEG-afbeeldingen te converteren. Het resulterende bestand wordt opgeslagen in de opgegeven map met de naam "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg".

### Voorbeeldbroncode voor Get Jpeg Page Range met Aspose.Words For .NET

```csharp 
 // Pad naar uw documentmap
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Stel de "PageSet" in op "0" om alleen de eerste pagina van een document te converteren.
options.PageSet = new PageSet(0);

// Wijzig de helderheid en het contrast van de afbeelding.
// Beide bevinden zich op een schaal van 0-1 en staan standaard op 0,5.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Wijzig de horizontale resolutie.
// De standaardwaarde voor deze eigenschappen is 96,0, voor een resolutie van 96 dpi.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Conclusie

In deze zelfstudie hebben we de functionaliteit onderzocht van het verkrijgen van een JPEG-paginabereik met Aspose.Words voor .NET. We hebben geleerd hoe we een specifiek bereik aan pagina's van een document kunnen converteren naar afbeeldingen in JPEG-indeling, terwijl we de opslagopties aanpassen.

Deze functie is handig als u specifieke pagina's uit een document wilt extraheren en deze als JPEG-afbeeldingen wilt opslaan. U kunt ook de helderheid, het contrast en de horizontale resolutie van afbeeldingen aanpassen om gepersonaliseerde resultaten te bereiken.

Aspose.Words voor .NET biedt een uitgebreid scala aan geavanceerde functies voor documentmanipulatie en -generatie. Het verkrijgen van een JPEG-paginabereik is een van de vele krachtige tools die u tot uw beschikking heeft.

Voel je vrij om deze functie te integreren in je Aspose.Words voor .NET-projecten om JPEG-afbeeldingen van hoge kwaliteit uit je documenten te halen.