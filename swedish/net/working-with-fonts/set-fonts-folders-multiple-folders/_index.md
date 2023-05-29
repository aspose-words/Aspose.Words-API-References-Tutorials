---
title: Ställ in teckensnittsmappar Flera mappar
linktitle: Ställ in teckensnittsmappar Flera mappar
second_title: Aspose.Words för .NET API Referens
description: Steg för steg guide för att ställa in flera teckensnittsmappar när du renderar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

den här handledningen går vi igenom steg-för-steg-processen för att ställa in flera teckensnittsmappar när du renderar ett dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du anger flera teckensnittsmappar som ska användas när du renderar dina dokument med Aspose.Words för .NET.

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där du vill spara ditt redigerade renderade dokument. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet för att rendera
 Sedan kan du ladda dokumentet för att rendera med hjälp av`Document` klass. Var noga med att ange rätt dokumentsökväg.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Steg 3: Ställ in teckensnittsmappar
 Nu kan du ställa in flera teckensnittsmappar med hjälp av`FontSettings` klass och`SetFontsFolders()` metod. Du kan ange sökvägarna till teckensnittsmappar som du vill använda i en array. I det här exemplet har vi specificerat två teckensnittsmappar: "C:\MyFonts\" och "D:\Misc\Fonts\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Steg 4: Använd teckensnittsinställningar
 Därefter måste du tillämpa teckensnittsinställningarna på ditt dokument med hjälp av`FontSettings` egendom av`Document` klass.

```csharp
doc.FontSettings = fontSettings;
```

## Steg 5: Spara det renderade dokumentet
 Slutligen kan du spara det renderade dokumentet till en fil med hjälp av`Save()` metod för`Document` klass. Var noga med att ange rätt sökväg och filnamn.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Exempel på källkod för Set Fonts Folders Flera mappar med Aspose.Words för .NET 

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Observera att den här inställningen åsidosätter alla standardfontkällor som söks efter som standard. Nu kommer endast dessa mappar att sökas efter
// teckensnitt när du renderar eller bäddar in teckensnitt. För att lägga till en extra teckensnittskälla samtidigt som systemets teckensnittskällor behålls, använd sedan både FontSettings.GetFontSources och
// FontSettings.SetFontSources istället.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Slutsats
I den här handledningen lärde vi oss hur du ställer in flera teckensnittsmappar när du renderar ett dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide kan du enkelt ange flera teckensnittsmappar som ska användas när du renderar dina dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att arbeta med typsnitt i dina dokument. Med denna kunskap kan du styra och anpassa teckensnittskällorna som används när du renderar dina dokument efter dina specifika behov.