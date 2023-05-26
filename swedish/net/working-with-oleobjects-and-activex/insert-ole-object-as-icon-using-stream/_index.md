---
title: Infoga Ole-objekt som ikon med hjälp av Stream
linktitle: Infoga Ole-objekt som ikon med hjälp av Stream
second_title: Aspose.Words för .NET API Referens
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