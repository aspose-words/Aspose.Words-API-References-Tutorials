---
title: Använd varningskälla
linktitle: Använd varningskälla
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder varningskälla med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/use-warning-source/
---

I det här exemplet kommer vi att visa dig hur du använder varningskälla med Aspose.Words för .NET. Varningskällan anger varningens ursprung när du använder återuppringningsfunktionen.

## Steg 1: Ladda dokumentet

 Vi kommer att ladda ett befintligt dokument som innehåller varningar med hjälp av`Load` metod för`Document` klass.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Steg 3: Använda varningskällan

 Vi använder varningskällan genom att ställa in dokumentets`WarningCallback` egendom till en samling av`WarningInfo` föremål.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Steg 4: Spara dokumentet

Slutligen kan vi spara dokumentet i önskat format.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Exempel på källkod för användning av varningskälla med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Grattis! Du har nu lärt dig hur du använder varningskällan med Aspose.Words för .NET.

### FAQ's

#### F: Kan vi anpassa utseendet på "Varning"-taggen?

 S: Formateringen av "Warning"-taggen beror på vilken Markdown-renderare som används. I de flesta fall kan du anpassa utseendet genom att använda CSS för att rikta in dig på`blockquote` taggen i ditt dokument.

#### F: Är det möjligt att lägga till ikoner i "Varning"-taggen?

S: Ja, det är möjligt att lägga till ikoner till "Varning"-taggen med HTML-kod i ditt Markdown-dokument. Du kan infoga en`span` tagga med lämplig klass för att visa en ikon bredvid varningstexten.

#### F: Är "Warning"-taggen kompatibel med alla Markdown-läsare?

 S: Kompatibiliteten för "Warning"-taggen beror på vilken Markdown-rendering som används. De flesta Markdown-läsare kommer att stödja`blockquote` taggen för att visa markerad text, men det exakta utseendet kan variera.