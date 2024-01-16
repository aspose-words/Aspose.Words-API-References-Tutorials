---
title: Pagina Terugbellen opslaan
linktitle: Pagina Terugbellen opslaan
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u het opslaan van documentpagina's naar afbeeldingen kunt aanpassen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-imagesaveoptions/page-saving-callback/
---

In deze zelfstudie verkennen we de C#-broncode voor het gebruik van de callback voor het opslaan van pagina's met Aspose.Words-opties voor het opslaan van afbeeldingen voor .NET. Met deze functie kunt u aangepaste acties uitvoeren wanneer u elke pagina van een document als afbeelding opslaat.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 In deze stap configureren we de opties voor het opslaan van afbeeldingen door een nieuw bestand te maken`ImageSaveOptions` voorwerp. We specificeren het gewenste back-upformaat, hier "Png" voor het PNG-formaat. We gebruiken`PageSet` om het paginabereik op te geven dat moet worden opgeslagen, hier vanaf de eerste pagina tot de laatste pagina van het document (`doc.PageCount - 1`). Wij hebben ook gezeten`PageSavingCallback` naar een exemplaar van`HandlePageSavingCallback`, wat een aangepaste klasse is om de callback voor het opslaan van pagina's af te handelen.

## Stap 4: Implementatie van de Save Page Callback

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Implementeer hier uw aangepaste acties
         // U kunt pagina-informatie openen via de eigenschap "args.PageIndex".
         // U kunt de opslagopties ook voor elke pagina afzonderlijk wijzigen
     }
}
```

 In deze stap implementeren we de`HandlePageSavingCallback` klasse die de`IPageSavingCallback` koppel. U kunt deze klasse aanpassen door uw specifieke acties toe te voegen in de`PageSaving` methode. U kunt pagina-informatie openen via de`args.PageIndex` eigendom van de`PageSavingArgs` object doorgegeven als argument.

## Stap 5: Pagina's opslaan als afbeeldingen

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 In deze laatste stap slaan we elke pagina van het document op als afbeelding met behulp van de`Save` methode en geef het pad door naar het uitvoerbestand met de`.png` extensie, samen met de opgegeven opslagopties.

Nu kunt u de broncode uitvoeren om aangepaste acties uit te voeren wanneer u elke pagina van het document als afbeelding opslaat. Het resulterende bestand wordt opgeslagen in de opgegeven map met de naam "WorkingWithImageSaveOptions.PageSavingCallback.png".

### Voorbeeldbroncode voor terugbellen van pagina's met Aspose.Words voor .NET


```csharp 
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Conclusie

In deze zelfstudie hebben we de callback-functionaliteit voor het opslaan van pagina's onderzocht met Aspose.Words-opties voor het opslaan van afbeeldingen voor .NET. We hebben geleerd hoe u aangepaste acties kunt uitvoeren wanneer u elke pagina van een document als afbeelding opslaat.

Deze functie is handig als u specifieke bewerkingen op elke pagina wilt uitvoeren bij het converteren naar afbeeldingen. U hebt toegang tot pagina-informatie en kunt deze gebruiken om back-upopties aan te passen of andere paginaspecifieke verwerkingen uit te voeren.

Aspose.Words voor .NET biedt een uitgebreid scala aan geavanceerde functies voor documentmanipulatie en -generatie. De herinnering voor het opslaan van pagina's is een van de vele krachtige hulpmiddelen waarmee u het proces van het opslaan van pagina's in afbeeldingen kunt aanpassen.