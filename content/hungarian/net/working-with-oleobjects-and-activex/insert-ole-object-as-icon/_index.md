---
title: Illessze be az Ole objektumot a Word dokumentumba ikonként
linktitle: Illessze be az Ole objektumot a Word dokumentumba ikonként
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be egy OLE objektumot a Word dokumentumba ikonként az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Az alábbiakban egy lépésről lépésre bemutatjuk a C# forráskódot, amely bemutatja, hogyan lehet OLE objektumot beszúrni a Word dokumentumba ikonként az Aspose.Words for .NET használatával.

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

## 3. lépés: Szúrjon be egy OLE objektumot ikonként
 Használja a Dokumentumkészítőt`InsertOleObjectAsIcon` módszer egy OLE objektum ikonként történő beszúrására a dokumentumba. Adja meg az OLE fájl elérési útját, a megjelenítési jelzőt, az ikon elérési útját és a beágyazott objektum nevét.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## 4. lépés: Mentse el a dokumentumot
 Használja a dokumentumot`Save` módszerrel mentheti a dokumentumot fájlba.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Példa forráskódra egy OLE objektum ikonként történő beszúrásához az Aspose.Words for .NET-hez

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Ez egy teljes kódminta egy OLE objektum ikonként történő beszúrásához az Aspose.Words for .NET-hez. Ügyeljen arra, hogy importálja a szükséges hivatkozásokat, és kövesse a korábban leírt lépéseket a kód projektbe való integrálásához.

## Következtetés

Végezetül megvizsgáltunk egy lépésről lépésre bemutatott útmutatót, amellyel az Aspose.Words for .NET segítségével egy OLE-objektumot ikonként illeszthetünk be egy Word-dokumentumba.

Ha követi ezeket a lépéseket, az Aspose.Words for .NET segítségével sikeresen beszúrhat egy OLE-objektumot ikonként a Word-dokumentumokba. Ügyeljen arra, hogy importálja a szükséges referenciákat, és gondosan kövesse az utasításokat a kívánt eredmény elérése érdekében.

### GYIK az objektum Word dokumentumba ikonként történő beszúrásához

#### K. Milyen hivatkozásokra van szükség egy OLE objektum ikonként történő beszúrásához egy Word dokumentumba az Aspose.Words for .NET használatával?

V: Az Aspose.Words for .NET használatához importálnia kell a következő hivatkozásokat a projektbe:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### K. Hogyan lehet új dokumentumot és dokumentumgenerátort létrehozni az Aspose.Words for .NET-ben?

 V: Új dokumentumot hozhat létre a`Document` osztályt és egy dokumentumkészítőt a`DocumentBuilder`osztály. Íme egy példa:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### K. Hogyan lehet OLE objektumot ikonként beszúrni a dokumentumba?

 V: Használja a Dokumentumkészítőt`InsertOleObjectAsIcon` módszer egy OLE objektum ikonként történő beszúrására. Adja meg az OLE fájl elérési útját, a megjelenítési jelzőt, az ikon elérési útját és a beágyazott objektum nevét. Íme egy példa:

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### K. Hogyan lehet elmenteni a dokumentumot az ikonként beszúrt OLE objektummal?

 V: Használja a dokumentumot`Save`módszerrel mentheti a dokumentumot fájlba. Íme egy példa:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```