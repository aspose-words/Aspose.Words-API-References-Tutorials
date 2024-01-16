---
title: Ole objektum beszúrása a Wordbe Ole csomaggal
linktitle: Ole objektum beszúrása a Wordbe Ole csomaggal
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szúrhat be egy OLE-objektumot OLE-csomaggal egy dokumentumba az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Az alábbiakban egy lépésről lépésre bemutatjuk a C# forráskódot, amely bemutatja, hogyan lehet OLE-objektumot beszúrni a Wordbe egy OLE-csomaggal az Aspose.Words for .NET használatával.

## 1. lépés: Importálja a szükséges referenciákat
Mielőtt elkezdené, győződjön meg arról, hogy importálta az Aspose.Words for .NET használatához szükséges hivatkozásokat a projektbe. Ez magában foglalja az Aspose.Words könyvtár importálását és a szükséges névterek hozzáadását a forrásfájlhoz.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## 2. lépés: Hozzon létre egy új dokumentumot és dokumentumgenerátort
 Ebben a lépésben egy új dokumentumot hozunk létre a`Document` osztályt és egy dokumentumkészítőt a`DocumentBuilder` osztály.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Szúrjon be egy OLE-objektumot egy OLE-csomaggal
 Használja a Dokumentumgenerátort`InsertOleObject` módszer egy OLE-csomaggal rendelkező OLE objektum dokumentumba való beillesztésére. Adja meg az adatfolyamot, az objektum típusát, a megjelenítési beállításokat és az egyéb szükséges beállításokat.

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

## 4. lépés: Mentse el a dokumentumot
 Használja a dokumentumot`Save` módszerrel mentheti a dokumentumot fájlba.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Minta forráskód egy OLE-objektum beszúrásához OLE-csomaggal az Aspose.Words for .NET-hez

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

Ez egy teljes kódminta egy OLE objektum beszúrásához az Aspose.Words for .NET OLE csomaggal. Ügyeljen arra, hogy importálja a szükséges hivatkozásokat, és kövesse a korábban leírt lépéseket a kód projektbe való integrálásához.

## Következtetés

Végezetül, végignéztünk egy lépésről-lépésre szóló útmutatót, amellyel az Aspose.Words for .NET segítségével OLE-objektumot illeszthetünk be egy OLE-csomaggal rendelkező Word dokumentumba.

Ha követi ezeket a lépéseket, az Aspose.Words for .NET segítségével sikeresen beillesztheti az OLE-csomagokat tartalmazó OLE-objektumokat Word-dokumentumaiba. Ügyeljen arra, hogy importálja a szükséges referenciákat, és gondosan kövesse az utasításokat a kívánt eredmény elérése érdekében.

### GYIK az ole objektum beszúrásához a Wordbe az ole csomaggal

#### K: Milyen hitelesítő adatokat kell importálnom az Aspose.Words for .NET használatához?

V: Az Aspose.Words for .NET használatához importálnia kell a következő hivatkozásokat:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### K: Hogyan lehet új dokumentumot és dokumentumgenerátort létrehozni?

 V: Új dokumentumot hozhat létre a`Document` osztályt és egy dokumentumkészítőt a`DocumentBuilder` osztály, az alábbiak szerint:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### K: Hogyan lehet beszúrni egy OLE-objektumot OLE-csomaggal a dokumentumba?

 V: Használja a`InsertOleObject` dokumentumkészítő módszere (`DocumentBuilder`) egy OLE-csomaggal rendelkező OLE objektum beszúrásához a dokumentumba. Adja meg az adatfolyamot, az objektum típusát, a megjelenítési beállításokat és az egyéb szükséges beállításokat. Íme egy példa:

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

#### K: Hogyan lehet menteni a dokumentumot?

 V: Használja a dokumentumot`Save` módszerrel mentheti a dokumentumot fájlba. Íme egy példa:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### K: Tudna mutatni egy teljes példát egy OLE objektum beszúrására az Aspose.Words for .NET OLE csomaggal?

V: Íme egy teljes mintakód egy OLE-objektum beszúrásához egy OLE-csomaggal az Aspose.Words for .NET használatával. Ügyeljen arra, hogy importálja a szükséges hivatkozásokat, és kövesse a korábban leírt lépéseket a kód projektbe való integrálásához:

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

Ezzel az oktatóanyagunk egy OLE-csomaggal rendelkező OLE-objektum Word-dokumentumba történő beszúrásáról szóló oktatóanyagunk befejeződik az Aspose.Words for .NET használatával. Nyugodtan importálja a szükséges hivatkozásokat, és kövesse a leírt lépéseket a kód projektbe való integrálásához. Ha további kérdése van, forduljon hozzánk bizalommal.