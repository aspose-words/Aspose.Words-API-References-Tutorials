---
title: Converteren tussen meeteenheden
linktitle: Converteren tussen meeteenheden
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het converteren tussen maateenheden in een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-properties/convert-between-measurement-units/
---

In deze zelfstudie leiden we u door de C#-broncode voor het converteren tussen maateenheden met Aspose.Words voor .NET. Met deze functie kunt u marges, kop- en voettekstafstanden enz. in verschillende maateenheden opgeven.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document en de constructor maken

In deze stap maken we een nieuw document en initialiseren we de constructor. Gebruik de volgende code:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Configureer maateenheden

Nu gaan we de waarden voor marges, kop- en voettekstafstanden, etc. omzetten in verschillende maateenheden. Gebruik de volgende code om waarden in specifieke meeteenheden op te geven:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Deze code maakt gebruik van de`ConvertUtil` klasse van Aspose.Words om de opgegeven waarden naar inches te converteren (`InchToPoint`). U kunt ook andere conversiemethoden gebruiken die beschikbaar zijn in de`ConvertUtil` klasse om waarden naar andere meeteenheden om te zetten.

### Voorbeeldbroncode voor converteren tussen meeteenheden met Aspose.Words voor .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

U hebt nu geleerd hoe u tussen maateenheden kunt converteren bij het opgeven van marges, kop- en voettekstafstanden, enz. in een document met behulp van Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze tutorial te volgen, kunt u eenvoudig de waarden in de gewenste maateenheden in uw eigen documenten opgeven.