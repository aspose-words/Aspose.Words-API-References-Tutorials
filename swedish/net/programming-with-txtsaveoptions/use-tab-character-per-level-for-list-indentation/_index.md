---
title: Använd fliktecken per nivå för listindrag
linktitle: Använd fliktecken per nivå för listindrag
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder funktionen för indragslistor med tabbtecken i Aspose.Words för .NET. Spara tid och förbättra ditt arbetsflöde med denna kraftfulla funktion.
type: docs
weight: 10
url: /sv/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

den här handledningen kommer vi att utforska C#-källkoden som tillhandahålls för funktionen "Använd ett tabbtecken per nivå för listindrag" med Aspose.Words för .NET. Den här funktionen låter dig använda tabbtecken för indragningslistor på varje nivå, vilket ger större flexibilitet och kontroll över utseendet på dina dokument.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har ställt in din utvecklingsmiljö med Aspose.Words för .NET. Se till att du har lagt till nödvändiga referenser och importerat lämpliga namnområden.

## Steg 2: Skapa dokumentet och generatorn

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 I det här steget skapar vi en ny`Document` objekt och en tillhörande`DocumentBuilder` objekt. Dessa objekt kommer att tillåta oss att manipulera och generera vårt dokument.

## Steg 3: Skapa en lista med tre nivåer av indrag

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

 I det här steget tillämpar vi standardformatet för listnummer med hjälp av`ApplyNumberDefault()` metod för listformateraren. Därefter lägger vi till tre objekt till vår lista med hjälp av dokumentbyggarens`Writeln()` och`Write()` metoder. Vi använder`ListIndent()` metod för att öka indraget på varje nivå.

## Steg 4: Konfigurera inspelningsalternativ

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

 I det här steget konfigurerar vi alternativen för att spara dokumentet. Vi skapar en ny`TxtSaveOptions` objekt och ställ in`ListIndentation.Count`egenskapen till 1 för att ange antalet tabbtecken per indragsnivå. Vi ställer också in`ListIndentation.Character` egenskapen till '\t' för att ange att vi vill använda tabbtecken.

## Steg 5: Spara dokumentet

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

 I detta sista steg sparar vi dokumentet med de angivna sparalternativen. Vi använder`Save()` metod för att dokumentet skickar hela sökvägen till utdatafilen och alternativen för att spara.


Nu kan du köra källkoden för att generera ett dokument med listindrag med tabbtecken. Utdatafilen kommer att sparas i den angivna katalogen med namnet "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt".

### Exempel på kodkälla för funktionen Använd ett tabbtecken per nivå för listindrag med Aspose.Words för .NET:

```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa en lista med tre nivåer av indrag
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");

TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);

```

Nu när du har skapat ditt dokument med listindrag med tabbtecken kan du använda Markdown för att formatera ditt artikelinnehåll. Se till att använda lämpliga formateringstaggar för att markera titlar, undertexter och medföljande källkod.