---
title: Lägg till textvattenstämpel med specifika alternativ
linktitle: Lägg till textvattenstämpel med specifika alternativ
second_title: Aspose.Words Document Processing API
description: Lär dig hur du lägger till en textvattenstämpel med specifika alternativ med Aspose.Words för .NET. Steg-för-steg guide.
type: docs
weight: 10
url: /sv/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

I den här handledningen kommer vi att gå igenom hur du lägger till en textvattenstämpel med specifika alternativ med Aspose.Words för .NET. En textvattenstämpel är text som läggs ovanpå ett dokument för att indikera att det är ett utkast, konfidentiellt osv.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda dokumentet

Vi kommer att ladda ett befintligt dokument med hjälp av dokumentsökvägen.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Steg 3: Lägg till textvattenstämpel med specifika alternativ

 Vi kommer att skapa en instans av`TextWatermarkOptions`klass och ställ in önskade alternativ för textens vattenstämpel.

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

## Steg 4: Spara dokumentet

Slutligen kan vi spara dokumentet med den tillagda textvattenstämpeln.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Exempel på källkod för att lägga till textvattenstämpel med specifika alternativ med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
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

Grattis! Du har nu lärt dig hur du lägger till textvattenstämpel med specifika alternativ med Aspose.Words för .NET.

