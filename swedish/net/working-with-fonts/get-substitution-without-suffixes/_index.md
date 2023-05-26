---
title: Få substitution utan suffix
linktitle: Få substitution utan suffix
second_title: Aspose.Words för .NET API Referens
description: I den här självstudien lär du dig hur du får åsidosättningar utan suffix i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/get-substitution-without-suffixes/
---

I den här handledningen kommer vi att visa dig hur du får åsidosättningar utan suffix i ett Word-dokument med hjälp av Aspose.Words-biblioteket för .NET. Substitutioner utan suffix används för att lösa teckensnittsersättningsproblem vid visning eller utskrift av dokument. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt

## Steg 1: Definiera dokumentkatalogen
 Först måste du ställa in katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet och konfigurera ersättningar utan suffix
 Därefter laddar vi dokumentet med hjälp av`Document` klass och konfigurera ersättningar utan suffix med hjälp av`DocumentSubstitutionWarnings` klass. Vi kommer också att lägga till en teckensnittskälla genom att ange en mapp som innehåller teckensnitten.

```csharp
//Ladda dokumentet och konfigurera ersättningar utan suffix
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Steg 3: Spara dokumentet
Slutligen kommer vi att spara dokumentet med åsidosättningar utan suffix tillämpade.

```csharp
// Spara dokumentet
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Exempel på källkod för Get Substitution Without Suffixes med Aspose.Words för .NET 
```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Slutsats
I den här handledningen såg vi hur man får åsidosättningarna utan suffix i ett Word-dokument med Aspose.Words för .NET. Substitutioner utan suffix är användbara för att lösa problem med teckensnittsersättning. Använd gärna den här funktionen för att förbättra visningen och utskriften av dina dokument.
