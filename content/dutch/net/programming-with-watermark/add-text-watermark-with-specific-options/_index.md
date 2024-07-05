---
title: Voeg tekstwatermerk toe met specifieke opties
linktitle: Voeg tekstwatermerk toe met specifieke opties
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tekstwatermerk met specifieke opties kunt toevoegen met Aspose.Words voor .NET. Stap-voor-stap handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

In deze zelfstudie laten we u zien hoe u een tekstwatermerk met specifieke opties kunt toevoegen met Aspose.Words voor .NET. Een tekstwatermerk is tekst die over een document heen wordt geplaatst om aan te geven dat het een concept, een vertrouwelijk document, enz. is.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Het document laden

We laden een bestaand document via het documentpad.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Stap 3: Voeg een tekstwatermerk toe met specifieke opties

 We zullen een exemplaar maken van de`TextWatermarkOptions`klasse en stel de gewenste opties voor het tekstwatermerk in.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Stap 4: Sla het document op

Ten slotte kunnen we het document opslaan met het toegevoegde tekstwatermerk.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Voorbeeldbroncode voor het toevoegen van tekstwatermerk met specifieke opties met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Gefeliciteerd! U hebt nu geleerd hoe u een tekstwatermerk met specifieke opties kunt toevoegen met Aspose.Words voor .NET.

