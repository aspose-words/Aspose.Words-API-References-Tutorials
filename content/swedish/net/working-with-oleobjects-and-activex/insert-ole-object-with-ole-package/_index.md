---
title: Infoga Ole-objekt i Word med Ole-paketet
linktitle: Infoga Ole-objekt i Word med Ole-paketet
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar ett OLE-objekt med ett OLE-paket i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som illustrerar hur man infogar ett OLE-objekt i word med ett OLE-paket med Aspose.Words för .NET.

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
 Använd dokumentgeneratorns`InsertOleObject`metod för att infoga ett OLE-objekt med ett OLE-paket i dokumentet. Ange dataström, objekttyp, visningsalternativ och andra nödvändiga inställningar.

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

## Slutsats

Avslutningsvis har vi gått igenom en steg-för-steg-guide för att infoga ett OLE-objekt i ett Word-dokument med ett OLE-paket med hjälp av Aspose.Words för .NET.

Genom att följa dessa steg kommer du att framgångsrikt kunna infoga OLE-objekt med OLE-paket i dina Word-dokument med Aspose.Words för .NET. Se till att importera nödvändiga referenser och följ instruktionerna noggrant för att få önskat resultat.

### Vanliga frågor för att infoga ole-objekt i word med ole-paket

#### F: Vilka referenser behöver jag importera för att använda Aspose.Words för .NET?

S: För att använda Aspose.Words för .NET måste du importera följande referenser:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### F: Hur skapar man ett nytt dokument och en dokumentgenerator?

 S: Du kan skapa ett nytt dokument med hjälp av`Document` klass och en dokumentbyggare med hjälp av`DocumentBuilder` klass, som visas nedan:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### F: Hur infogar man ett OLE-objekt med ett OLE-paket i dokumentet?

 A: Använd`InsertOleObject` metod för dokumentbyggaren (`DocumentBuilder`) för att infoga ett OLE-objekt med ett OLE-paket i dokumentet. Ange dataström, objekttyp, visningsalternativ och andra nödvändiga inställningar. Här är ett exempel :

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### F: Hur sparar jag dokumentet?

 S: Använd dokumentet`Save`metod för att spara dokumentet till en fil. Här är ett exempel :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### F: Kan du ge ett komplett exempel på att infoga ett OLE-objekt med ett OLE-paket med Aspose.Words för .NET?

S: Här är en komplett exempelkod för att infoga ett OLE-objekt med ett OLE-paket med Aspose.Words för .NET. Se till att importera nödvändiga referenser och följ stegen som beskrivits tidigare för att integrera den här koden i ditt projekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Detta avslutar vår handledning om att infoga ett OLE-objekt med ett OLE-paket i ett Word-dokument med Aspose.Words för .NET. Importera gärna de nödvändiga referenserna och följ stegen som beskrivs för att integrera denna kod i ditt projekt. Om du har ytterligare frågor, tveka inte att kontakta oss.