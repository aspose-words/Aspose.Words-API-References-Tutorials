---
title: Ställ in typsnittsmappar som standardinstans
linktitle: Ställ in typsnittsmappar som standardinstans
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att ställa in standardfontmappen när du renderar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/set-fonts-folders-default-instance/
---

den här handledningen går vi igenom steg-för-steg-processen för att ställa in standardfontmappen när du renderar ett dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du ställer in standardfontmappen som ska användas när du renderar dina dokument med Aspose.Words för .NET.

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där du vill spara ditt redigerade renderade dokument. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ställ in standardfontmapp
 Sedan kan du ställa in standardfontmappen med hjälp av`FontSettings.DefaultInstance` klass och`SetFontsFolder()` metod. Ange sökvägen till den typsnittsmapp du vill använda som standardmapp.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Steg 3: Ladda dokumentet för att rendera
 Nu kan du ladda dokumentet för att rendera med hjälp av`Document` klass. Var noga med att ange rätt dokumentsökväg.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Steg 4: Spara det renderade dokumentet
 Slutligen kan du spara det renderade dokumentet till en fil med hjälp av`Save()` metod för`Document` klass. Var noga med att ange rätt sökväg och filnamn.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Exempel på källkod för Set Fonts Folders Default Instance med Aspose.Words för .NET 

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Slutsats
den här handledningen lärde vi oss hur du ställer in standardfontmappen när du renderar ett dokument med Aspose.Words för .NET. Genom att följa den här steg-för-steg-guiden kan du enkelt ange vilken mapp med teckensnitt som ska användas som standardmapp när du renderar dina dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att arbeta med typsnitt i dina dokument. Med denna kunskap kan du styra och anpassa teckensnittskällorna som används när du renderar dina dokument efter dina specifika behov.