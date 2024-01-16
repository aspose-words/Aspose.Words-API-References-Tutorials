---
title: Illessze be az Ole objektumot ikonként a Stream segítségével
linktitle: Illessze be az Ole objektumot ikonként a Stream segítségével
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be egy OLE-objektumot ikonként egy adatfolyam segítségével az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Az alábbiakban egy lépésről lépésre bemutatjuk a C# forráskódot, amely bemutatja, hogyan lehet OLE-objektumot ikonként beszúrni az Aspose.Words for .NET-hez tartozó adatfolyam segítségével.

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

## 3. lépés: Szúrjon be egy OLE-objektumot ikonként egy adatfolyamból
 Használja a Dokumentumkészítőt`InsertOleObjectAsIcon` módszer egy OLE objektum ikonként történő beszúrására egy adatfolyamból a dokumentumba. Adja meg az adatfolyamot, az objektum típusát, az ikon elérési útját és a beágyazott objektum nevét.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## 4. lépés: Mentse el a dokumentumot
 Használja a dokumentumot`Save` módszerrel mentheti a dokumentumot fájlba.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Példa forráskód egy OLE objektum ikonként történő beszúrásához Aspose.Words for .NET adatfolyam használatával

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Ez egy teljes kódminta egy OLE objektum ikonként történő beszúrásához az Aspose.Words for .NET-hez tartozó adatfolyam használatával. Ügyeljen arra, hogy importálja a szükséges hivatkozásokat, és kövesse a korábban leírt lépéseket a kód projektbe való integrálásához.

## Következtetés

fenti, lépésenkénti útmutató elmagyarázza, hogyan lehet OLE-objektumot ikonként beszúrni egy Word-dokumentumba az Aspose.Words for .NET-hez tartozó folyamat segítségével. A leírt lépéseket követve integrálhatja ezt a funkciót a projektjébe. Mindenképpen importálja a szükséges hivatkozásokat, hozzon létre egy új dokumentumot és dokumentumgenerátort, illessze be az OLE objektumot ikonként a folyamból, majd mentse el a dokumentumot. Használja kiindulópontként a megadott mintakódot, és szabja testre igényeinek megfelelően.

### GYIK

#### K. Hogyan lehet importálni a szükséges hivatkozásokat az Aspose.Words for .NET használatához?

A. A szükséges referenciák importálásához kövesse az alábbi lépéseket:

 Adja hozzá a következőket`using` állítások a forrásfájl tetején:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Győződjön meg arról, hogy hozzáadta az Aspose.Words könyvtárat a projekthez.

#### K. Hogyan lehet új dokumentumot és dokumentumkészítőt létrehozni az Aspose.Words for .NET használatával?

A. Új dokumentum és dokumentumgenerátor létrehozásához kövesse az alábbi lépéseket:

 Használja a`Document` osztályban új dokumentum létrehozásához:

```csharp
Document doc = new Document();
```
 Használja a`DocumentBuilder`osztály a korábban létrehozott dokumentumhoz társított dokumentumkészítő létrehozásához:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### K. Hogyan lehet OLE objektumot ikonként beszúrni egy adatfolyamból az Aspose.Words for .NET használatával?

A. Ha egy OLE-objektumot ikonként szeretne beszúrni egy adatfolyamból, kövesse az alábbi lépéseket:

 Használja a`InsertOleObjectAsIcon` a dokumentumgenerátor módszere az OLE objektum beszúrásához:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### K. Hogyan lehet a dokumentumot fájlba menteni?

A.  A dokumentum fájlba mentéséhez használhatja a`Save` a cél elérési útját meghatározó dokumentum módszere:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### K. Hogyan ágyazhatom be a kódot egy OLE objektumnak egy adatfolyamból ikonként való beillesztéséhez a projektembe?

A. Ha be szeretné ágyazni a kódot egy OLE objektumnak egy adatfolyamból ikonként való beillesztéséhez a projektbe, kövesse az alábbi lépéseket:
-  Importálja a szükséges referenciákat a megfelelő hozzáadásával`using` nyilatkozatok.
-  Hozzon létre egy új dokumentumot és egy dokumentumkészítőt a`Document` és`DocumentBuilder` osztályok.
- Használja a kódot az OLE objektum adatfolyamból való ikonként történő beszúrásához.
-  Mentse el a dokumentumot a`Save` módszert a megfelelő célútvonallal.

Az alábbi lépések követésével sikeresen beszúrhat egy OLE-objektumot ikonként egy adatfolyamból az Aspose.Words for .NET használatával. Ügyeljen arra, hogy kövesse az utasításokat, és importálja a szükséges referenciákat a kívánt eredmények eléréséhez.