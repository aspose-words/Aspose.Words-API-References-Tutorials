---
title: Infoga Ole-objekt i Word-dokument
linktitle: Infoga Ole-objekt i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar ett OLE-objekt i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som illustrerar hur man infogar ett OLE-objekt i Word-dokument med Aspose.Words för .NET.

## Steg 1: Importera nödvändiga referenser
Innan du börjar, se till att du har importerat de nödvändiga referenserna för att använda Aspose.Words för .NET i ditt projekt. Detta inkluderar att importera Aspose.Words-biblioteket och lägga till de nödvändiga namnområdena till din källfil.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Steg 2: Skapa ett nytt dokument och dokumentgenerator
 I det här steget kommer vi att skapa ett nytt dokument med hjälp av`Document` klass och en dokumentbyggare med hjälp av`DocumentBuilder` klass.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Infoga ett OLE-objekt
 Använd dokumentbyggarens`InsertOleObject` metod för att infoga ett OLE-objekt i dokumentet. Ange OLE-objektets URL, objekttyp, visningsalternativ och andra nödvändiga inställningar.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

## Steg 4: Spara dokumentet
 Använd dokumentets`Save` metod för att spara dokumentet till en fil.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Exempel på källkod för att infoga ett OLE-objekt med Aspose.Words för .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Detta är ett komplett kodexempel för att infoga ett OLE-objekt med Aspose.Words för .NET. Var noga med att importera nödvändiga referenser och följ stegen som beskrivits tidigare för att integrera denna kod i ditt projekt.

## Slutsats

Sammanfattningsvis är att infoga OLE-objekt i ett Word-dokument en kraftfull funktion som erbjuds av Aspose.Words för .NET. Med det här biblioteket kan du enkelt bädda in OLE-objekt som HTML-filer, Excel-kalkylblad, PowerPoint-presentationer etc. i dina Word-dokument.

I den här artikeln har vi gått igenom en steg-för-steg-guide för att förklara källkoden i C# som illustrerar hur man infogar ett OLE-objekt i ett Word-dokument. Vi täckte de nödvändiga referenserna, skapade ett nytt dokument och en dokumentgenerator, och stegen för att infoga ett OLE-objekt och spara dokumentet.

### Vanliga frågor för att infoga ett OLE-objekt i ett Word-dokument

#### F: Vilka referenser behöver jag importera för att använda Aspose.Words för .NET?

S: För att använda Aspose.Words för .NET måste du importera följande referenser:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### F: Hur skapar man ett nytt dokument och en dokumentgenerator?

 S: Du kan skapa ett nytt dokument med hjälp av`Document` klass och en dokumentbyggare med hjälp av`DocumentBuilder` klass, som visas nedan:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### F: Hur infogar man ett OLE-objekt i dokumentet?

 A: Använd`InsertOleObject`metod för dokumentbyggaren (`DocumentBuilder`) för att infoga ett OLE-objekt i dokumentet. Ange OLE-objektets URL, objekttyp, visningsalternativ och andra nödvändiga inställningar. Här är ett exempel :

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

#### F: Hur sparar jag dokumentet?

 S: Använd dokumentet`Save` metod för att spara dokumentet till en fil. Här är ett exempel :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### F: Kan du ge ett komplett exempel på att infoga ett OLE-objekt med Aspose.Words för .NET?

S: Här är en komplett exempelkod för att infoga ett OLE-objekt med Aspose.Words för .NET. Se till att importera nödvändiga referenser och följ stegen som beskrivits tidigare för att integrera den här koden i ditt projekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
