---
title: Írja be a Szerző mezőt
linktitle: Írja be a Szerző mezőt
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be SZERZŐ mezőt Word-dokumentumaiba az Aspose.Words for .NET segítségével. A dokumentumok személyre szabásához adja meg a szerző nevét.
type: docs
weight: 10
url: /hu/net/working-with-fields/insert-author-field/
---


Itt található egy lépésről lépésre bemutatott útmutató a C# forráskód leírásához, amely az Aspose.Words for .NET "SZERZŐI mező beszúrása" funkcióját használja. A kívánt eredmény elérése érdekében gondosan kövesse az egyes lépéseket.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott kódban meg kell adnia dokumentumai könyvtárát. Cserélje le a „DOKUMENTUMKÖNYVTÁR” értéket a dokumentumkönyvtár megfelelő elérési útjára.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A dokumentum és a bekezdés létrehozása

Kezdjük egy új dokumentum létrehozásával és az első bekezdés lekérésével.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 3. lépés: Szúrja be a SZERZŐ mezőt

 Használjuk a`AppendField()` metódussal illeszt be egy SZERZŐ mezőt a bekezdésbe.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Ezután konfiguráljuk a mezőt`AuthorName` tulajdonság megadásához a szerző nevét.

```csharp
field. AuthorName = "Test1";
```

 Végül hívjuk a`Update()` módszer a mező frissítéséhez.

```csharp
field. Update();
```

### Példa a forráskódra egy AUTHOR mező beszúrásához az Aspose.Words .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentumkészítés.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Illessze be a SZERZŐ mezőt.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

Ebben a példában létrehoztunk egy új dokumentumot, beszúrtunk egy SZERZŐ mezőt, konfiguráltuk a szerző nevét, és elmentettük a dokumentumot egy megadott fájlnévvel.

Ezzel véget is értünk a "SZERZŐI mező beszúrása" funkció használatáról szóló útmutatónknak az Aspose.Words for .NET-hez.

### GYIK

#### K: Mi az Aspose.Words szerzői mezője?

V: Az Aspose.Words szerzői mezője egy speciális mező, amely automatikusan beszúrja és frissíti a szerző nevét egy Word-dokumentumban. Gyakran használják annak jelzésére, hogy ki készítette vagy módosította a dokumentumot.

#### K: Hogyan frissíthető a szerző mező egy Word-dokumentumban az Aspose.Words segítségével?

V: A Word-dokumentum szerzői mezője frissíthető, hogy az tükrözze az aktuális szerző nevét. Ehhez használhatja a Dokumentum osztályban elérhető UpdateFields metódust. Ez a módszer frissíti a dokumentum összes mezőjét, beleértve a szerző mezőt is.

#### K: Testreszabható a szerző mező formátuma egy Word-dokumentumban?

V: Igen, lehetőség van a szerző mező formátumának testreszabására egy Word dokumentumban. Alapértelmezés szerint a szerző mező egyszerűen a szerző nevét jeleníti meg. Az Aspose.Wordsban elérhető formázási lehetőségek segítségével azonban további információkat is hozzáadhat, például a módosítás dátumát és időpontját.

#### K: A szerző mező érzékeny a szerző nevének későbbi módosításaira?

V: Igen, a szerző mező érzékeny a szerző nevének későbbi módosításaira. Ha módosítja a szerző nevét a dokumentum tulajdonságainál, a szerző mező automatikusan frissül az új névvel a dokumentummezők frissítésekor.