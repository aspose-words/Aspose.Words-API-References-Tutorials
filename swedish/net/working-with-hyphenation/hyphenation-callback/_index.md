---
title: Återuppringning med avstavning
linktitle: Återuppringning med avstavning
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder återuppringning av avstavning i Aspose.Words för .NET för att hantera ordavstavning.
type: docs
weight: 10
url: /sv/net/working-with-hyphenation/hyphenation-callback/
---

I denna steg-för-steg handledning kommer vi att visa dig hur du använder avstavningsåteruppringningsfunktionen i Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte redan har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Spara avstavningspåminnelse

 Först registrerar vi avstavningsåteruppringningen med en anpassad`CustomHyphenationCallback` klass. Detta gör att vi kan hantera ordavstavning enligt våra egna regler:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Se till att du har implementerat`CustomHyphenationCallback`klass efter dina specifika behov.

## Steg 2: Ladda dokumentet och tillämpa avstavning

Ladda sedan ditt dokument från den angivna katalogen och avstava orden med Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Steg 3: Hantera saknade ordboksfel

Om en avstavningsordbok saknas kommer vi att fånga motsvarande undantag och visa ett felmeddelande:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Steg 4: Rensa och inaktivera avstavningspåminnelse

Slutligen, för renlighet och för att stänga av avstavningspåminnelsen, utför följande steg:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Detta rensar upp och inaktiverar avstavningspåminnelsen efter avslutad bearbetning.

Så ! Du har framgångsrikt använt avstavningsuppringning i Aspose.Words för .NET.

### Exempel på källkod för återuppringning av avstavning med Aspose.Words för .NET

```csharp
try
{
	 // Registrera avstavningsuppringning.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Använd gärna den här koden i dina egna projekt och modifiera den för att passa dina specifika behov.