---
title: Infoga Ole-objekt med Ole-paket
linktitle: Infoga Ole-objekt med Ole-paket
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar ett OLE-objekt med ett OLE-paket i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som illustrerar hur man infogar ett OLE-objekt med ett OLE-paket med Aspose.Words för .NET.

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

## Steg 3: Infoga ett OLE-objekt med ett OLE-paket
 Använd dokumentgeneratorns`InsertOleObject` metod för att infoga ett OLE-objekt med ett OLE-paket i dokumentet. Ange dataström, objekttyp, visningsalternativ och andra nödvändiga inställningar.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Steg 4: Spara dokumentet
 Använd dokumentets`Save` metod för att spara dokumentet till en fil.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Exempel på källkod för att infoga ett OLE-objekt med ett OLE-paket med Aspose.Words för .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Detta är ett komplett kodexempel för att infoga ett OLE-objekt med ett OLE-paket med Aspose.Words för .NET. Var noga med att importera nödvändiga referenser och följ stegen som beskrivits tidigare för att integrera denna kod i ditt projekt.