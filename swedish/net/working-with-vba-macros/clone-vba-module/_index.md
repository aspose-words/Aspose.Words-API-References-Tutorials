---
title: Klon Vba-modul
linktitle: Klon Vba-modul
second_title: Aspose.Words för .NET API Referens
description: den här handledningen lär du dig hur du klona en VBA-modul från ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-vba-macros/clone-vba-module/
---

I den här handledningen kommer vi att berätta för dig hur du klona en VBA-modul från ett Word-dokument med makron med hjälp av Aspose.Words-biblioteket för .NET. Genom att klona en VBA-modul kan du återanvända eller kopiera VBA-kod från ett källdokument till ett annat dokument. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt
- Ett Word-dokument som innehåller ett VBA-projekt med modulen du vill klona

## Steg 1: Definiera dokumentkatalogen
 Först måste du ställa in katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda källdokument
Därefter laddar vi källdokumentet i Word, som innehåller VBA-projektet och modulen vi vill klona.

```csharp
// Ladda källdokumentet
Document doc = new Document(dataDir + "VBA project.docm");
```

## Steg 3: Skapa ett nytt dokument med VBA-projektet och klona modulen
Vi kommer att skapa ett nytt dokument med ett tomt VBA-projekt och klona den angivna modulen från källdokumentet.

```csharp
// Skapa ett nytt dokument med ett tomt VBA-projekt
Document destDoc = new Document { VbaProject = new VbaProject() };

// Klona modulen
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## Steg 4: Spara måldokumentet
Slutligen kommer vi att spara måldokumentet med den klonade VBA-modulen till en fil.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Exempel på källkod för Clone Vba Module med Aspose.Words för .NET 
```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Slutsats
I den här handledningen såg vi hur man klona en VBA-modul från ett Word-dokument med makron med Aspose.Words för .NET. Genom att klona VBA-moduler kan du enkelt återanvända VBA-kod från ett källdokument i ett annat dokument. Använd gärna den här funktionen för att organisera och hantera dina makron i olika dokument.
