---
title: Läs Vba-makron
linktitle: Läs Vba-makron
second_title: Aspose.Words för .NET API Referens
description: I den här handledningen lär du dig hur du läser VBA-makron från ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-vba-macros/read-vba-macros/
---
den här handledningen kommer vi att förklara hur man läser VBA-makron från ett Word-dokument med hjälp av Aspose.Words-biblioteket för .NET. Genom att läsa VBA-makron kan du komma åt befintlig VBA-kod i ditt Word-dokument. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt
- Ett Word-dokument som innehåller VBA-makron

## Steg 1: Definiera dokumentkatalogen
 Först måste du ställa in katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet och läs VBA-makron
Därefter kommer vi att ladda Word-dokumentet och kontrollera om det innehåller ett VBA-projekt. Om dokumentet har ett VBA-projekt kommer vi att gå igenom alla moduler i projektet och visa källkoden för varje modul.

```csharp
//Ladda dokumentet
Document doc = new Document(dataDir + "VBA project.docm");
if (doc.VbaProject!= null)
{
foreach(VbaModule module in doc.VbaProject.Modules)
{
Console.WriteLine(module.SourceCode);
}
}
```

### Exempel på källkod för Läs Vba-makron med Aspose.Words för .NET 

```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
if (doc.VbaProject != null)
{
	foreach (VbaModule module in doc.VbaProject.Modules)
	{
		Console.WriteLine(module.SourceCode);
	}
}

```

## Slutsats
I den här handledningen såg vi hur man läser VBA-makron från ett Word-dokument med Aspose.Words för .NET. Genom att läsa VBA-makron kan du komma åt befintlig VBA-kod i ditt dokument och utföra operationer enligt dina behov. Använd gärna den här funktionen för att granska och analysera VBA-makron i dina Word-dokument.


