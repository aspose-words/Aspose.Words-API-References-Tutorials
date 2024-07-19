---
title: Field Update Culture
linktitle: Field Update Culture
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan frissítheti a terepi kultúrát Word-dokumentumaiban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fields/field-update-culture/
---

Itt található egy lépésről lépésre bemutatott útmutató a C# forráskód leírásához, amely az Aspose.Words for .NET "Field Culture Update" funkcióját használja. A kívánt eredmény elérése érdekében gondosan kövesse az egyes lépéseket.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott kódban meg kell adnia dokumentumai könyvtárát. Cserélje le a „DOKUMENTUMKÖNYVTÁR” értéket a dokumentumkönyvtár megfelelő elérési útjára.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A dokumentum és a dokumentumgenerátor létrehozása

Kezdjük egy új dokumentum és egy dokumentumgenerátor létrehozásával.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Az időmező beszúrása

 Használjuk a`InsertField()`módszer egy időmező beillesztésére a dokumentumba.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

Ezzel beszúr egy időmezőt a dokumentumba.

## 4. lépés: A Field Update Culture konfigurálása

A mezőbeállításokat úgy konfiguráljuk, hogy a mező frissítési kultúrájának a mezőkódon kell alapulnia.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

Ezek a beállítások határozzák meg a mezők frissítéséhez használt kultúrát.

### Mintaforráskód a terepi kultúra frissítéséhez az Aspose.Words segítségével .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozd létre a dokumentumot és a dokumentumgenerátort.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Illessze be az időmezőt.
builder. InsertField(FieldType.FieldTime, true);

// Állítsa be a helyszíni frissítési kultúrát.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// Mentse el a dokumentumot.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

Ebben a példában létrehoztunk egy új dokumentumot, beszúrtunk egy időmezőt, és konfiguráltuk a mezőfrissítési kultúrát. Ezután megadott fájlnévvel elmentettük a dokumentumot.

Ezzel véget is értünk az "Update Field Culture" funkció használatáról szóló útmutatónknak az Aspose.Words for .NET-hez.

### GYIK

#### K: Mi az Aspose.Words mezőfrissítési kultúrája?

V: Az Aspose.Words mezőfrissítési kultúrája a Word-dokumentum mezőértékeinek formázására és frissítésére használt kultúrára vonatkozik. A kultúra határozza meg, hogyan jelenjenek meg a számok, dátumok és egyéb adatok a mezőkben, amikor frissítik őket.

#### K: Hogyan lehet beállítani a frissítési kultúrát a Word-dokumentum mezőihez az Aspose.Words segítségével?

V: A Word-dokumentum mezőinek frissítési kultúrájának beállításához az Aspose.Words segítségével, kövesse az alábbi lépéseket:

1. Importálja a Document osztályt az Aspose.Words névtérből.
2. Hozzon létre egy példányt a dokumentumból a meglévő dokumentum betöltésével.
3. A mezők frissítési kultúrájának beállításához használja a Document.UpdateFieldsCultureInfo tulajdonságot.

#### K: Melyek a támogatott kultúrák az Aspose.Words mezőinek frissítéséhez?

V: Az Aspose.Words különböző kultúrákat támogat a mezők frissítéséhez. Megadhat bármilyen, az operációs rendszer által támogatott kultúrát. Például "en-US" az amerikai angolhoz, "fr-FR" a franciához, "de-DE" a némethez stb.

#### K: Beállítható-e egy adott kultúra egy adott területre, nem pedig a teljes dokumentumra?

V: Igen, beállítható egy adott kultúra egy adott területre, nem pedig a teljes dokumentumra. Az Aspose.Wordsben minden mező rendelkezik egy Format tulajdonsággal, amellyel beállítható az adott mezőre jellemző formázási kultúra. Ez lehetővé teszi a mező megjelenítésének és frissítésének szabályozását a dokumentum többi mezőitől függetlenül.

#### K: Hogyan ellenőrizhetem a jelenleg meghatározott mezőfrissítési kultúrát egy Word-dokumentumban?

V: Az aktuálisan meghatározott mezőfrissítési kultúra Word-dokumentumban történő ellenőrzéséhez használja a Document.UpdateFieldsCultureInfo tulajdonságot. Ez a tulajdonság azt a CultureInfo objektumot adja vissza, amely a mezőfrissítések beállításához jelenleg használt kultúrát képviseli.