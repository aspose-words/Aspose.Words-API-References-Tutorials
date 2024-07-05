---
title: Táblázat beszúrása HTML-ből
linktitle: Táblázat beszúrása HTML-ből
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szúrhat be táblázatot HTML-kódból Word-dokumentumba az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/insert-table-from-html/
---

Ebben az oktatóanyagban megtanuljuk, hogyan lehet táblázatot beszúrni egy Word dokumentumba HTML-ből az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végére képes lesz programozottan beszúrni HTML-táblázatokat Word-dokumentumaiba.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum létrehozása és a dokumentumgenerátor inicializálása
A Szövegfeldolgozás elindításához a dokumentummal és a dokumentumgenerátorral, kövesse az alábbi lépéseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentumkészítés
Document doc = new Document();

// Inicializálja a dokumentumgenerátort
DocumentBuilder builder = new DocumentBuilder(doc);
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 3. lépés: A táblázat beszúrása HTML-ből
Ezután HTML kód segítségével beszúrjuk a táblázatot a dokumentumba. Használja a következő kódot:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Itt használjuk a`InsertHtml` a dokumentumkészítő módszere a táblázatot tartalmazó HTML beillesztéséhez. A megadott HTML létrehoz egy táblázatot két sorral és két cellával minden sorban. A táblázat tartalmát testreszabhatja a HTML kód igény szerinti módosításával.

## 4. lépés: Mentse el a módosított dokumentumot
Végül el kell mentenünk a módosított dokumentumot a HTML-ből beillesztett táblázattal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód a Táblázat beszúrása HTML-ből az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Vegye figyelembe, hogy az AutoFitSettings nem vonatkozik a HTML-ből beszúrt táblázatokra.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet táblázatot beszúrni egy Word dokumentumba HTML-ből az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, akkor programozottan illeszthet be táblázatokat HTML-ből a Word dokumentumaiba. Ez a funkció lehetővé teszi a táblázatos adatok konvertálását és importálását HTML-forrásokból Word-dokumentumaiba.
