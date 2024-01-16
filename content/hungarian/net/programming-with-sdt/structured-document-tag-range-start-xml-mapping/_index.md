---
title: Strukturált dokumentumcímke-tartomány Indítsa el az Xml-leképezést
linktitle: Strukturált dokumentumcímke-tartomány Indítsa el az Xml-leképezést
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthat be XML-leképezést egy Word-dokumentumban kezdődő strukturált dokumentumcímke-tartományhoz az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Ez az oktatóanyag elmagyarázza, hogyan állíthat be XML-leképezést egy strukturált dokumentumcímke-tartományhoz egy Word-dokumentumban az Aspose.Words for .NET használatával. Az XML-leképezés lehetővé teszi az XML-adatforrás meghatározott részeinek megjelenítését a tartalomvezérlőn belül.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahol a dokumentum található.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a dokumentumot és hozzon létre XML részt
 Töltse be a Word dokumentumot a`Document` konstruktor, paraméterként átadva a dokumentum elérési útját. Hozzon létre egy XML-részt, amely tartalmazza a strukturált dokumentumcímkén belül megjeleníteni kívánt adatokat.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## 3. lépés: Állítsa be az XML-leképezést a strukturált dokumentumcímkéhez
strukturált dokumentumcímke-tartomány lekérése a dokumentumtól kezdve. Ezután állítsa be a strukturált dokumentumcímke XML-leképezését úgy, hogy az XPath-kifejezés használatával jelenítse meg az egyéni XML-rész egy meghatározott részét.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## 4. lépés: Mentse el a dokumentumot
 Mentse el a módosított dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Példa forráskód a strukturált dokumentumcímke-tartományhoz Indítsa el az Xml-leképezést az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Hozzon létre egy XML részt, amely adatokat tartalmaz, és adja hozzá a dokumentum CustomXmlPart gyűjteményéhez.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Hozzon létre egy StructuredDocumentTag-et, amely megjeleníti a CustomXmlPart rész tartalmát a dokumentumban.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Ha beállítunk egy leképezést a StructuredDocumentTag-hez,
	// csak a CustomXmlPart azon részét jeleníti meg, amelyre az XPath mutat.
	// Ez az XPath a CustomXmlPart első "<root>" elemének második "<text>" elemére mutat.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Ez az! Sikeresen beállította az XML-leképezést egy strukturált dokumentumcímke-tartomány kezdetéhez a Word-dokumentumban az Aspose.Words for .NET használatával.