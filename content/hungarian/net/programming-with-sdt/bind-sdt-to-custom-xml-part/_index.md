---
title: Kösse az SDT-t az egyéni Xml-részhez
linktitle: Kösse az SDT-t az egyéni Xml-részhez
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan köthet össze SDT-t egy egyéni Xml-részhez az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Ez az oktatóanyag bemutatja, hogyan lehet strukturált dokumentumcímkét (SDT) egy egyéni Xml-részhez kötni az Aspose.Words for .NET használatával. Az SDT-k lehetővé teszik strukturált tartalomvezérlők hozzáadását a Word-dokumentumokhoz, a CustomXmlParts pedig lehetőséget biztosít a dokumentumhoz társított egyéni XML-adatok tárolására.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és XML alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahová a dokumentumot menteni szeretné.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy dokumentumot és a CustomXmlPart-ot
 Hozzon létre egy új példányt a`Document` osztály és a`CustomXmlPart` az egyéni XML adatok tárolására. Az egyéni XML-nek érvényes XML formátumban kell lennie. Ebben a példában egy egyszerű XML karakterláncot használunk`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## 3. lépés: Adjon hozzá egy StructuredDocumentTag-et (SDT) a dokumentumhoz
 Add hozzá a`StructuredDocumentTag` a dokumentumhoz, hogy tartalomvezérlőként szolgáljon. Adja meg a`SdtType` mint`PlainText` és a`MarkupLevel` mint`Block` blokk szintű SDT létrehozásához.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## 4. lépés: Állítsa be az XML-leképezést az SDT-hez
 Térképezze az SDT-t a`CustomXmlPart` segítségével`SetMapping` módszere a`XmlMapping` ingatlan. Adja meg a`CustomXmlPart` , az XPath kifejezés a kívánt XML-csomópont megkereséséhez, valamint a névtér előtag, ha szükséges. Ebben a példában az SDT-t leképezzük a következőre`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## 5. lépés: Mentse el a dokumentumot
 Mentse el a módosított dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithSdt.BindSDTtoCustomXmlPart.doc" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Példa forráskód a Bind Sd Tto Custom Xml Parthoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

Ez az! Sikeresen kötött egy SDT-t egy CustomXmlPart-hoz a Word-dokumentumban az Aspose.Words for .NET használatával.