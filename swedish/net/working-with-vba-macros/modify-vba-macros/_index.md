---
title: Ändra Vba-makron
linktitle: Ändra Vba-makron
second_title: Aspose.Words för .NET API Referens
description: I den här handledningen lär du dig hur du redigerar VBA-makron i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-vba-macros/modify-vba-macros/
---
I den här handledningen kommer vi att förklara hur man ändrar VBA-makron i ett Word-dokument med hjälp av Aspose.Words-biblioteket för .NET. Genom att redigera VBA-makron kan du uppdatera befintlig VBA-kod i ditt Word-dokument. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt
- Ett Word-dokument som innehåller VBA-makron som du vill ändra

## Steg 1: Definiera dokumentkatalogen
 Först måste du ställa in katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet som innehåller VBA-makron
Därefter kommer vi att ladda Word-dokumentet som innehåller VBA-makron som vi vill ändra.

```csharp
// Ladda dokumentet som innehåller VBA-makron
Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
```

## Steg 3: Ändra makrokällkoden
 Vi ska nu modifiera källkoden för det första makrot i VBA-projektet. Ersätt`newSourceCode` variabel med den nya källkoden du vill använda.

```csharp
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
```

## Steg 4: Spara det ändrade dokumentet
Slutligen kommer vi att spara det modifierade dokumentet med de uppdaterade VBA-makron till en fil.

```csharp
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");
```

### Exempel på källkod för Ändra Vba-makron med Aspose.Words för .NET
 
```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");

```

## Slutsats
I den här handledningen såg vi hur man redigerar VBA-makron i ett Word-dokument med Aspose.Words för .NET. Genom att redigera VBA-makron kan du uppdatera befintlig VBA-kod i ditt dokument för att göra ändringar eller förbättringar. Använd gärna den här funktionen för att ytterligare anpassa och automatisera dina Word-dokument.