---
title: Infoga Ole-objekt i Word-dokument som ikon
linktitle: Infoga Ole-objekt i Word-dokument som ikon
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar ett OLE-objekt i Word-dokument som ikon med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som illustrerar hur man infogar ett OLE-objekt i Word-dokument som ikon med Aspose.Words för .NET.

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

## Steg 3: Infoga ett OLE-objekt som en ikon
 Använd dokumentbyggarens`InsertOleObjectAsIcon` metod för att infoga ett OLE-objekt som en ikon i dokumentet. Ange OLE-filsökväg, visningsflagga, ikonsökväg och namn på det inbäddade objektet.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Steg 4: Spara dokumentet
 Använd dokumentets`Save` metod för att spara dokumentet till en fil.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Exempel på källkod för att infoga ett OLE-objekt som en ikon med Aspose.Words för .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Detta är ett komplett kodexempel för att infoga ett OLE-objekt som en ikon med Aspose.Words för .NET. Var noga med att importera nödvändiga referenser och följ stegen som beskrivits tidigare för att integrera denna kod i ditt projekt.

## Slutsats

Avslutningsvis utforskade vi en steg-för-steg-guide för att infoga ett OLE-objekt som en ikon i ett Word-dokument med Aspose.Words för .NET.

Genom att följa dessa steg kommer du att framgångsrikt kunna infoga ett OLE-objekt som en ikon i dina Word-dokument med Aspose.Words för .NET. Se till att importera nödvändiga referenser och följ instruktionerna noggrant för att få önskat resultat.

### Vanliga frågor för att infoga ole-objekt i word-dokument som ikon

#### F. Vilka referenser behövs för att infoga ett OLE-objekt som en ikon i ett Word-dokument med Aspose.Words för .NET?

S: Du måste importera följande referenser till ditt projekt för att kunna använda Aspose.Words för .NET:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### F. Hur skapar man en ny dokument- och dokumentgenerator i Aspose.Words för .NET?

 S: Du kan skapa ett nytt dokument med hjälp av`Document` klass och en dokumentbyggare med hjälp av`DocumentBuilder`klass. Här är ett exempel :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### F. Hur infogar man ett OLE-objekt som en ikon i dokumentet?

 S: Använd dokumentbyggarens`InsertOleObjectAsIcon` metod för att infoga ett OLE-objekt som en ikon. Ange OLE-filsökväg, visningsflagga, ikonsökväg och namn på det inbäddade objektet. Här är ett exempel :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### F. Hur sparar man dokumentet med OLE-objektet infogat som en ikon?

 S: Använd dokumentet`Save`metod för att spara dokumentet till en fil. Här är ett exempel :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```