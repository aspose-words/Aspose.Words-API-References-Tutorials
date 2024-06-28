---
title: Egyéni Xml-részhez leképezve táblázat ismétlődő szakasz létrehozása
linktitle: Egyéni Xml-részhez leképezve táblázat ismétlődő szakasz létrehozása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre egy ismétlődő szakaszt egy CustomXmlPart-hoz leképezve egy táblázatot egy Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Ez az oktatóanyag bemutatja, hogyan hozható létre egy ismétlődő szakaszt tartalmazó táblázat egy Word-dokumentum egyéni Xml-részéhez leképezve az Aspose.Words for .NET használatával. Az ismétlődő szakasz lehetővé teszi sorok dinamikus hozzáadását az Egyéni Xml-részben tárolt XML-adatok alapján.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahová a dokumentumot menteni szeretné.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy dokumentumot és a DocumentBuildert
 Hozzon létre egy új példányt a`Document` osztály és a`DocumentBuilder` a dokumentum tartalmának felépítéséhez.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Adjon hozzá egyéni XML-adatokat egy CustomXmlPart-hoz
 Hozzon létre egy`CustomXmlPart` és egyéni XML-adatokat adjon hozzá. Ebben a példában egy XML-karakterláncot hozunk létre, amely könyvek gyűjteményét képviseli a címükkel és szerzőikkel.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## 4. lépés: Hozzon létre egy táblázatot és táblázatszerkezetet
 Kezdje el a táblázat létrehozását a`StartTable` módszere a`DocumentBuilder` . Adja hozzá a táblázat celláit és tartalmát a`InsertCell` és`Write` mód.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## 5. lépés: Hozzon létre egy egyéni XML-re leképezett Ismétlődő szakaszt
 Hozzon létre egy`StructuredDocumentTag` val vel`SdtType.RepeatingSection` az ismétlődő szakasz ábrázolására. Állítsa be az ismétlődő szakasz XML-leképezését a`SetMapping` módszere a`XmlMapping` ingatlan. Ebben a példában leképezzük az ismétlődő szakaszt`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## 6. lépés: Hozza létre az Ismétlődő szakasz elemet, és adja hozzá a cellákat
 Hozzon létre egy`StructuredDocumentTag` val vel`SdtType.RepeatingSectionItem` hogy képviselje az ismétlődő szakaszelemet. Gyermekként fűzze hozzá az ismétlődő részhez.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Hozzon létre egy`Row`hogy az ismétlődő szakasz minden elemét képviselje, és hozzáfűzze az ismétlődő szakaszelemhez.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## 7. lépés: Adjon hozzá tartalomvezérlőket az Ismétlés szakaszhoz
 Teremt`StructuredDocumentTag` tárgyakkal`SdtType.PlainText`

  a cím és a szerző tartalomvezérlőinek megjelenítésére. Állítsa be az XML-leképezést minden tartalomvezérlőhöz a segítségével`SetMapping` módszere a`XmlMapping` ingatlan. Ebben a példában a címvezérlőt a következőre rendeljük`/books[1]/book[1]/title[1]` és a szerző vezérli`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## 8. lépés: Mentse el a dokumentumot
 Mentse el a módosított dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Példa forráskódra az Aspose.Words for .NET használatával táblázatismétlő szakasz létrehozásához egyéni Xml-részhez leképezve 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

Ez az! Az Aspose.Words for .NET segítségével sikeresen létrehozott egy táblázatot, amely ismétlődő szakaszt tartalmaz a Word-dokumentum CustomXmlPart-részére leképezve.