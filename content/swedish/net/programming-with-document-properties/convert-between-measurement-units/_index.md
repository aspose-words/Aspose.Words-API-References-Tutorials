---
title: Konvertera mellan måttenheter
linktitle: Konvertera mellan måttenheter
second_title: Aspose.Words Document Processing API
description: Steg-för-steg guide för att konvertera mellan måttenheter i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-properties/convert-between-measurement-units/
---

den här handledningen går vi igenom C#-källkoden för att konvertera mellan måttenheter med Aspose.Words för .NET. Denna funktion låter dig specificera marginaler, sidhuvuden och sidfotsavstånd etc. i olika måttenheter.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Skapa dokumentet och konstruktören

I det här steget kommer vi att skapa ett nytt dokument och initiera konstruktorn. Använd följande kod:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Konfigurera måttenheter

Nu ska vi konvertera värdena för marginaler, sidhuvuds- och sidfotsavstånd etc. i olika måttenheter. Använd följande kod för att ange värden i specifika måttenheter:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Denna kod använder`ConvertUtil` klass av Aspose.Words för att konvertera de angivna värdena till tum (`InchToPoint` ). Du kan också använda andra konverteringsmetoder som är tillgängliga i`ConvertUtil` klass för att konvertera värden till andra måttenheter.

### Exempel på källkod för Convert Between Measurement Units med Aspose.Words för .NET

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

Du har nu lärt dig hur du konverterar mellan måttenheter när du anger marginaler, sidhuvud och sidfotsavstånd etc. i ett dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt ange värdena i de önskade måttenheterna i dina egna dokument.