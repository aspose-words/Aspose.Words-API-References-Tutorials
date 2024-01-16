---
title: Ole objektum beszúrása Word dokumentumba
linktitle: Ole objektum beszúrása Word dokumentumba
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be OLE-objektumot Word-dokumentumba az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Az alábbiakban egy lépésről lépésre bemutatjuk a C# forráskódot, amely bemutatja, hogyan lehet OLE objektumot beszúrni a Word dokumentumba az Aspose.Words for .NET használatával.

## 1. lépés: Importálja a szükséges referenciákat
Mielőtt elkezdené, győződjön meg arról, hogy importálta az Aspose.Words for .NET használatához szükséges hivatkozásokat a projektbe. Ez magában foglalja az Aspose.Words könyvtár importálását és a szükséges névterek hozzáadását a forrásfájlhoz.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 2. lépés: Hozzon létre egy új dokumentumot és dokumentumgenerátort
 Ebben a lépésben egy új dokumentumot hozunk létre a`Document` osztályt és egy dokumentumkészítőt a`DocumentBuilder` osztály.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Szúrjon be egy OLE objektumot
 Használja a Dokumentumkészítőt`InsertOleObject` módszer egy OLE objektum beszúrására a dokumentumba. Adja meg az OLE objektum URL-címét, az objektum típusát, a megjelenítési beállításokat és az egyéb szükséges beállításokat.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

## 4. lépés: Mentse el a dokumentumot
 Használja a dokumentumot`Save` módszerrel mentheti a dokumentumot fájlba.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Példa forráskódra egy OLE objektum beszúrásához az Aspose.Words for .NET-hez

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Ez egy teljes kódminta egy Aspose.Words for .NET OLE objektum beszúrásához. Ügyeljen arra, hogy importálja a szükséges hivatkozásokat, és kövesse a korábban leírt lépéseket a kód projektbe való integrálásához.

## Következtetés

Összefoglalva, az OLE-objektumok beillesztése egy Word-dokumentumba az Aspose.Words for .NET hatékony szolgáltatása. Ezzel a könyvtárral egyszerűen beágyazhat OLE-objektumokat, például HTML-fájlokat, Excel-táblázatokat, PowerPoint-prezentációkat stb., Word-dokumentumaiba.

Ebben a cikkben egy lépésről lépésre bemutatott útmutatón keresztül elmagyarázzuk a forráskódot C#-ban, amely bemutatja, hogyan lehet OLE-objektumot beszúrni egy Word-dokumentumba. Kitértünk a szükséges hivatkozásokra, egy új dokumentum és egy dokumentumgenerátor létrehozására, valamint az OLE objektum beszúrásának és a dokumentum mentésének lépéseire.

### GYIK OLE objektumok Word-dokumentumba történő beszúrásához

#### K: Milyen hitelesítő adatokat kell importálnom az Aspose.Words for .NET használatához?

V: Az Aspose.Words for .NET használatához importálnia kell a következő hivatkozásokat:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### K: Hogyan lehet új dokumentumot és dokumentumgenerátort létrehozni?

 V: Új dokumentumot hozhat létre a`Document` osztályt és egy dokumentumkészítőt a`DocumentBuilder` osztály, az alábbiak szerint:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### K: Hogyan lehet OLE objektumot beszúrni a dokumentumba?

 V: Használja a`InsertOleObject` dokumentumkészítő módszere (`DocumentBuilder`) egy OLE objektum beszúrásához a dokumentumba. Adja meg az OLE objektum URL-címét, az objektum típusát, a megjelenítési beállításokat és az egyéb szükséges beállításokat. Íme egy példa:

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

#### K: Hogyan lehet menteni a dokumentumot?

 V: Használja a dokumentumot`Save` módszerrel mentheti a dokumentumot fájlba. Íme egy példa:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### K: Tudna mutatni egy teljes példát egy OLE objektum beszúrására az Aspose.Words for .NET segítségével?

V: Íme egy teljes mintakód egy OLE objektum beszúrásához az Aspose.Words for .NET-hez. Ügyeljen arra, hogy importálja a szükséges hivatkozásokat, és kövesse a korábban leírt lépéseket a kód projektbe való integrálásához:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
