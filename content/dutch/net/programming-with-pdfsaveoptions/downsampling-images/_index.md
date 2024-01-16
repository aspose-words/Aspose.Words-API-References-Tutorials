---
title: Verklein de PDF-documentgrootte door afbeeldingen te downsamplen
linktitle: Verklein de PDF-documentgrootte door afbeeldingen te downsamplen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de PDF-documentgrootte kunt verkleinen door afbeeldingen te downsamplen bij het converteren naar PDF met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/downsampling-images/
---

In deze zelfstudie leiden we u door de stappen om de PDF-documentgrootte te verkleinen door afbeeldingen te downsamplen bij het converteren naar PDF met Aspose.Words voor .NET. Hierdoor wordt de grootte van het gegenereerde PDF-bestand kleiner. Volg onderstaande stappen:

## Stap 1: Het document laden

Begin met het uploaden van het document dat u naar PDF wilt converteren:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Zorg ervoor dat u het juiste pad naar uw document opgeeft.

## Stap 2: Configureer de PDF-opslagopties

Maak een exemplaar van de klasse PdfSaveOptions en stel de opties voor het verkleinen van afbeeldingen in:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 De`Resolution` eigenschap specificeert de doelresolutie van de afbeeldingen en de`ResolutionThreshold`eigenschap specificeert de minimale resolutie waaronder de afbeeldingen niet worden verkleind.

## Stap 3: Converteer document naar PDF

 Gebruik de`Save` methode om het document naar PDF te converteren, waarbij de opslagopties worden gespecificeerd:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Zorg ervoor dat u het juiste pad opgeeft om de geconverteerde PDF op te slaan.

### Voorbeeldbroncode voor het downsamplen van afbeeldingen met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// We kunnen een minimumdrempel instellen voor downsampling.
	// Deze waarde voorkomt dat de tweede afbeelding in het invoerdocument wordt gedownsampled.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Door deze stappen te volgen, kunt u de afbeeldingsresolutie eenvoudig verlagen bij het converteren naar PDF met Aspose.Words voor .NET.

## Conclusie

In deze zelfstudie hebben we uitgelegd hoe u de grootte van een PDF-document kunt verkleinen met beeldbemonstering bij het converteren naar PDF met Aspose.Words voor .NET. Door de beschreven stappen te volgen, kunt u eenvoudig de resolutie van afbeeldingen en de grootte van het gegenereerde PDF-bestand verkleinen. Zorg ervoor dat u het juiste pad naar uw document opgeeft en configureer indien nodig de opties voor beeldbemonstering. Door de PDF-bestandsgrootte te verkleinen, wordt het gemakkelijker om het bestand op verschillende platforms te delen, op te slaan en snel te laden. Profiteer van de voordelen van het verkleinen van de PDF-documentgrootte met beeldbemonstering met Aspose.Words voor .NET.

### Veel Gestelde Vragen

#### Vraag: Wat verkleint de grootte van het PDF-document met beeldbemonstering?
A: Het verkleinen van de PDF-documentgrootte met Image Sampling is het verkleinen van de grootte van het gegenereerde PDF-bestand door de resolutie van de afbeeldingen te verlagen bij het converteren naar PDF. Dit optimaliseert het gebruik van opslagruimte en maakt het gemakkelijker om het PDF-bestand te delen en over te dragen.

#### Vraag: Hoe kan ik de PDF-documentgrootte verkleinen met beeldbemonstering met Aspose.Words voor .NET?
A: Volg deze stappen om de PDF-documentgrootte te verkleinen met beeldbemonstering met Aspose.Words voor .NET:

 Stel het mappad in waar uw documenten zich bevinden door te vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van uw documentenmap.

 Laad het document dat u naar PDF wilt converteren met behulp van de`Document` class en specificeer het pad naar het document in de opgegeven documentenmap.

 Configureer de opties voor opslaan als PDF door een exemplaar te maken van het`PdfSaveOptions` klasse en het instellen van de opties voor beeldbemonstering met behulp van de`DownsampleOptions` eigendom. U kunt de doelresolutie van afbeeldingen opgeven met behulp van de`Resolution` en stel een minimale resolutiedrempel in waarboven afbeeldingen niet worden verkleind met behulp van de`ResolutionThreshold` eigendom.

 Sla het document op in PDF-formaat met behulp van de`Save` werkwijze van de`Document` klasse die het pad specificeert en opties voor opslaan.

#### Vraag: Wat zijn de voordelen van het verkleinen van de PDF-documentgrootte met beeldbemonstering?
A: De voordelen van het verkleinen van de PDF-documentgrootte met beeldbemonstering zijn:

Verkleinde PDF-bestandsgrootte: Beeldbemonstering vermindert de resolutie van afbeeldingen in het PDF-document, wat resulteert in een aanzienlijke afname van de PDF-bestandsgrootte. Dit maakt het gemakkelijk om het bestand te delen en over te dragen, vooral via e-mail of online.

Optimalisatie van opslagruimte: Het verkleinen van de grootte van het PDF-bestand helpt het gebruik van de opslagruimte te optimaliseren, vooral als u veel PDF-bestanden heeft die afbeeldingen met een hoge resolutie bevatten.

Prestatieverbeteringen: Kleinere PDF-bestanden worden sneller geladen en kunnen sneller op verschillende apparaten worden geopend en bekeken.