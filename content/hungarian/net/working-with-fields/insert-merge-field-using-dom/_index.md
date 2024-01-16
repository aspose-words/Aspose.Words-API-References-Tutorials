---
title: Egyesítési mező beszúrása DOM segítségével
linktitle: Egyesítési mező beszúrása DOM segítségével
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be egyéni mező-egyesítési mezőket Word-dokumentumaiba az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fields/insert-merge-field-using-dom/
---

Íme egy lépésről lépésre bemutatott útmutató a C# forráskód leírásához, amely az Aspose.Words for .NET "Insert Field Merge Field" funkcióját használja. A kívánt eredmény elérése érdekében gondosan kövesse az egyes lépéseket.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott kódban meg kell adnia dokumentumai könyvtárát. Cserélje le a „DOKUMENTUMKÖNYVTÁR” értéket a dokumentumkönyvtár megfelelő elérési útjára.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A Document és a DocumentBuilder létrehozása

Kezdjük egy új dokumentum létrehozásával és a DocumentBuilder inicializálásával.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: A kurzor mozgatása a bekezdésre

 Használjuk a`MoveTo()` a DocumentBuilder metódusával mozgassa a kurzort arra a bekezdésre, ahová a mezőegyesítési mezőt be akarjuk szúrni.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## 4. lépés: A mezőegyesítési mező beszúrása

 A DocumentBuildert használjuk`InsertField()` metódussal egy mező-összevonási mezőt illeszthet be a bekezdésbe.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Ezután konfiguráljuk a mezőegyesítési mező tulajdonságait a megfelelő beállítások megadásával, mint például a mezőnév, a mező előtti és utáni szöveg, valamint a függőleges formázási beállítások.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Végül hívjuk a`Update()` módszer a mező frissítéséhez.

```csharp
field. Update();
```

### Forráskód minta mező-egyesítési mező beszúrásához az Aspose.Words for .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozza létre a dokumentumot és a DocumentBuildert.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Mozgassa a kurzort a bekezdésre.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Mezőegyesítési mező beszúrása.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Frissítse a mezőt.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

Ebben a példában létrehoztunk egy új dokumentumot, a kurzort a kívánt bekezdésre mozgattuk, majd beszúrtunk egy mezőegyesítési mezőt a dokumentumba.

### GYIK

#### K: Hogyan illeszthetek be egyesítési mezőt egy Word dokumentumba az Aspose.Words for .NET használatával a DOM-mal?

V: Ha egy egyesítési mezőt szeretne beszúrni egy Word-dokumentumba az Aspose.Words for .NET használatával DOM-mal, kövesse az alábbi lépéseket:

1. Navigáljon ahhoz a bekezdéshez, amelybe be szeretné szúrni az egyesítési mezőt.
2.  Hozzon létre egy`FieldMergeField` tárgy.
3. Állítsa be az egyesítési mező tulajdonságait, például a mező nevét és a formázási beállításokat.
4.  Adja hozzá az egyesítési mezőt a bekezdéshez a gombbal`Paragraph.AppendChild` módszer.

#### K: Hogyan adhatom meg a forrásadatokat az Aspose.Words for .NET összevonási mezőjéhez?

V: Az Aspose.Words for .NET programban az egyesítési mező forrásadatainak megadásához használja a`FieldMergeField.FieldName` metódussal állíthatja be az egyesítési mező nevét, amely egy külső adatforrásban, például CSV-fájlban, adatbázisban stb. lévő mező neve. Használhatja a`FieldMergeField.Text` módszer az egyesítési mező értékének közvetlen beállításához.

#### K: Testreszabhatom az egyesítési mező megjelenését egy Word-dokumentumban az Aspose.Words for .NET segítségével?

 V: Igen, testreszabhatja az egyesítési mező megjelenését egy Word-dokumentumban az Aspose.Words for .NET segítségével. A tulajdonságok segítségével beállíthatja a formázási beállításokat, például a kis- és nagybetűket, a betűtípust, a színt stb`FieldMergeField` tárgy.

#### K: Hogyan ellenőrizhetem, hogy az Aspose.Words for .NET segítségével sikerült-e beilleszteni egy egyesítő mezőt egy Word-dokumentumba?

 V: Az egyesítési mező sikeres beszúrásának ellenőrzéséhez böngészhet a dokumentum tartalmában, és kereshet az egyesítő mező példányaira. Használhatja a módszereit és tulajdonságait`Document` objektum a dokumentum bekezdéseinek, mezőinek és egyéb elemeinek eléréséhez.

#### K: Az egyesítési mező beszúrása DOM használatával hatással van a Word dokumentumszerkezetére az Aspose.Words for .NET használatával?

V: Az egyesítési mező DOM segítségével történő beszúrása nem befolyásolja közvetlenül a Word dokumentum szerkezetét. Azonban egy új mezőelemet ad a dokumentum tartalmához. A dokumentum szerkezetét módosíthatja a meglévő elemek hozzáadásával, törlésével vagy módosításával az Ön igényei szerint.