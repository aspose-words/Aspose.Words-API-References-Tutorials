---
title: A tartalomvezérlők módosítása
linktitle: A tartalomvezérlők módosítása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan módosíthat szöveget, legördülő listákat és képeket egy Word-dokumentum tartalomvezérlőjén belül az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-sdt/modify-content-controls/
---

Ez az oktatóanyag elmagyarázza, hogyan módosíthatja a különböző típusú tartalomvezérlőket egy Word-dokumentumban az Aspose.Words for .NET használatával. A tartalomvezérlőn belül frissítheti a szöveget, a legördülő lista kiválasztott értékét, vagy lecserélheti a képet.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahol a dokumentum található.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a dokumentumot, és ismételje meg a tartalomvezérlőket
 Töltse be a Word dokumentumot a`Document` konstruktor, paraméterként átadva a dokumentum elérési útját. Iteráljon a dokumentumban lévő összes strukturált dokumentumcímkén a a segítségével`foreach` hurok.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // A tartalomvezérlés típusa alapján hajtson végre műveleteket
}
```

## 3. lépés: Módosítsa az egyszerű szöveges tartalomvezérlőt
 A típusú tartalomvezérlőkhöz`SdtType.PlainText`, távolítsa el az összes meglévő gyermeket, hozzon létre egy új bekezdést, és fűzze hozzá a kívánt szöveget.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## 4. lépés: A legördülő lista tartalomvezérlőjének módosítása
 A típusú tartalomvezérlőkhöz`SdtType.DropDownList` , frissítse a kiválasztott értéket egy adott értékre állítva`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## 5. lépés: Módosítsa a Képtartalom-szabályozást
 A típusú tartalomvezérlőkhöz`SdtType.Picture`, kérje le az alakzatot a tartalomvezérlőn belül, és cserélje ki a képét egy újra.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## 6. lépés: Mentse el a módosított dokumentumot
 Mentse el a módosított dokumentumot a megadott könyvtárba a`Save`módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithSdt.ModifyContentControls.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Példa forráskódra a tartalomvezérlők módosításához az Aspose.Words segítségével .NET-hez 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

Ez az! Sikeresen módosította a Word-dokumentum különböző típusú tartalomvezérlőit az Aspose.Words for .NET segítségével.