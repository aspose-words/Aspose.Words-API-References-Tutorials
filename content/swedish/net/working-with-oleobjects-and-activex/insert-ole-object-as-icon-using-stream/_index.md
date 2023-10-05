---
title: Infoga Ole-objekt som ikon med hjälp av Stream
linktitle: Infoga Ole-objekt som ikon med hjälp av Stream
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar ett OLE-objekt som en ikon med hjälp av en ström med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som illustrerar hur man infogar ett OLE-objekt som en ikon med hjälp av en stream med Aspose.Words för .NET.

## Steg 1: Importera nödvändiga referenser
Innan du börjar, se till att du har importerat de nödvändiga referenserna för att använda Aspose.Words för .NET i ditt projekt. Detta inkluderar att importera Aspose.Words-biblioteket och lägga till de nödvändiga namnområdena till din källfil.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Steg 2: Skapa ett nytt dokument och dokumentgenerator
 I det här steget kommer vi att skapa ett nytt dokument med hjälp av`Document` klass och en dokumentbyggare med hjälp av`DocumentBuilder` klass.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Infoga ett OLE-objekt som en ikon från en ström
 Använd dokumentbyggarens`InsertOleObjectAsIcon` metod för att infoga ett OLE-objekt som en ikon från en ström i dokumentet. Ange dataström, objekttyp, ikonsökväg och namn på det inbäddade objektet.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Steg 4: Spara dokumentet
 Använd dokumentets`Save` metod för att spara dokumentet till en fil.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Exempel på källkod för att infoga ett OLE-objekt som en ikon med en ström med Aspose.Words för .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Detta är ett komplett kodexempel för att infoga ett OLE-objekt som en ikon med hjälp av en ström med Aspose.Words för .NET. Var noga med att importera nödvändiga referenser och följ stegen som beskrivits tidigare för att integrera denna kod i ditt projekt.

## Slutsats

Steg-för-steg-guiden ovan förklarar hur man infogar ett OLE-objekt som en ikon i ett Word-dokument med hjälp av ett flöde med Aspose.Words för .NET. Genom att följa de beskrivna stegen kommer du att kunna integrera denna funktionalitet i ditt projekt. Se till att importera nödvändiga referenser, skapa ett nytt dokument och dokumentgenerator, infoga OLE-objektet som en ikon från strömmen och spara sedan dokumentet. Använd exempelkoden som tillhandahålls som utgångspunkt och anpassa den efter dina behov.

### FAQ's

#### F. Hur importerar man nödvändiga referenser för att använda Aspose.Words för .NET?

A. För att importera nödvändiga referenser måste du följa dessa steg:

 Lägg till följande`using` uttalanden överst i din källfil:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Se till att du har lagt till Aspose.Words-biblioteket i ditt projekt.

#### F. Hur skapar man ett nytt dokument- och dokumentbyggare med Aspose.Words för .NET?

A. För att skapa ett nytt dokument och dokumentgenerator kan du följa dessa steg:

 Använd`Document` klass för att skapa ett nytt dokument:

```csharp
Document doc = new Document();
```
 Använd`DocumentBuilder`klass för att skapa en dokumentbyggare kopplad till det tidigare skapade dokumentet:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### F. Hur infogar man ett OLE-objekt som en ikon från en ström med Aspose.Words för .NET?

A. För att infoga ett OLE-objekt som en ikon från en ström kan du följa dessa steg:

 Använd`InsertOleObjectAsIcon` metod för dokumentgeneratorn för att infoga OLE-objektet:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### F. Hur sparar man dokumentet i en fil?

A.  För att spara dokumentet till en fil kan du använda`Save` metod för dokumentet som anger destinationssökvägen:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### F. Hur bäddar jag in koden för att infoga ett OLE-objekt som en ikon från en ström i mitt projekt?

A. För att bädda in koden för att infoga ett OLE-objekt som en ikon från en ström i ditt projekt, följ dessa steg:
-  Importera nödvändiga referenser genom att lägga till lämpliga`using` uttalanden.
-  Skapa ett nytt dokument och en dokumentbyggare med hjälp av`Document` och`DocumentBuilder` klasser.
- Använd koden för att infoga OLE-objektet som en ikon från en ström.
-  Spara dokumentet med hjälp av`Save` metod med lämplig destinationssökväg.

Genom att följa dessa steg kommer du att framgångsrikt kunna infoga ett OLE-objekt som en ikon från en ström med Aspose.Words för .NET. Se till att följa instruktionerna och importera nödvändiga referenser för att få önskat resultat.