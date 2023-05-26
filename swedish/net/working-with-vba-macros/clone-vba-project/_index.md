---
title: Clone Vba-projekt
linktitle: Clone Vba-projekt
second_title: Aspose.Words för .NET API Referens
description: I den här handledningen lär du dig hur du klona ett VBA-projekt från ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-vba-macros/clone-vba-project/
---

I den här handledningen kommer vi att berätta för dig hur du klona ett VBA-projekt från ett Word-dokument med makron med hjälp av Aspose.Words-biblioteket för .NET. Genom att klona ett VBA-projekt kan du kopiera all VBA-kod från ett källdokument till ett annat dokument. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt
- Ett Word-dokument som innehåller ett VBA-projekt som du vill klona

## Steg 1: Definiera dokumentkatalogen
 Först måste du ställa in katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda källdokument
Därefter laddar vi källdokumentet i Word, som innehåller VBA-projektet vi vill klona.

```csharp
// Ladda källdokumentet
Document doc = new Document(dataDir + "VBA project.docm");
```

## Steg 3: Skapa ett nytt dokument med det klonade VBA-projektet
Vi kommer att skapa ett nytt dokument med ett tomt VBA-projekt och klona VBA-projektet från källdokumentet.

```csharp
// Skapa ett nytt dokument med ett tomt VBA-projekt
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };
```

## Steg 4: Spara måldokumentet
Slutligen kommer vi att spara måldokumentet tillsammans med det klonade VBA-projektet till en fil.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");
```

### Exempel på källkod för Clone Vba Project med Aspose.Words för .NET 
```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");

```

## Slutsats
I den här handledningen såg vi hur man klona ett VBA-projekt från ett Word-dokument med makron med Aspose.Words för .NET. Genom att klona VBA-projekt kan du kopiera all VBA-kod från ett källdokument till ett annat dokument. Använd gärna den här funktionen för att organisera och hantera dina makron i olika dokument.
