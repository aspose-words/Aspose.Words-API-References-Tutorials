---
title: Sorok ismétlése a következő oldalakon
linktitle: Sorok ismétlése a következő oldalakon
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan ismételheti meg a táblázat sorait a következő oldalakon egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

Ebben az oktatóanyagban megtanuljuk, hogyan ismételheti meg a táblázat sorait egy Word-dokumentum következő oldalain az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végére megadhatja azokat a sorokat, amelyeket meg kell ismételnie a táblázat következő oldalain a Word-dokumentumokban.

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

## 3. lépés: A táblázat felépítése ismétlődő sorokkal
Ezután elkészítünk egy táblázatot a következő oldalakon ismétlődő sorokkal. Használja a következő kódot:

```csharp
// A táblázat eleje
builder. StartTable();

// Az első sor paramétereinek konfigurálása (fejlécsorok)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

//Szúrja be az első sor első celláját
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Illessze be az első sor második celláját
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Állítsa be a következő sorok paramétereit
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Hurok a cellák beszúrásához a következő sorokba
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// A táblázat vége
builder. EndTable();
```

 Itt a dokumentumkészítőt használjuk két fejlécsorral és több adatsorral rendelkező táblázat összeállítására. A`RowFormat.HeadingFormat` paraméterek a fejlécsorok megjelölésére szolgálnak, amelyeket a következő oldalakon meg kell ismételni.

## 4. lépés: Mentse el a módosított dokumentumot
Végül az USA

  el kell mentenie a módosított dokumentumot úgy, hogy a fejlécek a táblázat következő oldalain ismétlődnek. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód a Sorok ismétlése a következő oldalakon az Aspose.Words for .NET használatával 

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan ismételheti meg a táblázat sorait egy Word-dokumentum következő oldalain az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, megadhatja, hogy mely sorokat ismételje meg az Ön egyedi igényei szerint a Word-dokumentumokban.