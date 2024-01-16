---
title: Állítsa be a Tartalomvezérlési stílust
linktitle: Állítsa be a Tartalomvezérlési stílust
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja be a tartalomvezérlő stílusát egy Word-dokumentumban az Aspose.Words for .NET használatával, következetes formázást alkalmazva.
type: docs
weight: 10
url: /hu/net/programming-with-sdt/set-content-control-style/
---

Ez az oktatóanyag elmagyarázza, hogyan állíthatja be a tartalomvezérlő stílusát egy Word-dokumentumban az Aspose.Words for .NET használatával. A következetes formázás érdekében előre meghatározott vagy egyéni stílusokat alkalmazhat a tartalomvezérlőkre.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahol a dokumentum található.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a dokumentumot, és töltse le a tartalomvezérlőt
 Töltse be a Word dokumentumot a`Document` konstruktor, paraméterként átadva a dokumentum elérési útját. Töltse le a kívánt tartalomvezérlőt a dokumentumból. Ebben a példában feltételezzük, hogy a tartalomvezérlő az első strukturált dokumentumcímke a dokumentumban.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 3. lépés: Töltse le a stílust, és alkalmazza a tartalomvezérlőre
 A kívánt stílus lekérése a dokumentum stílusgyűjteményéből. Ebben a példában az "Idézet" stílust a használatával kérjük le`StyleIdentifier.Quote` . Ezután rendelje hozzá a lekért stílust a`Style` a strukturált dokumentumcímke tulajdonsága.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## 4. lépés: Mentse el a dokumentumot
 Mentse el a módosított dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithSdt.SetContentControlStyle.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Példa forráskódra a Set Content Control Style funkcióhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Ez az! Sikeresen beállította egy tartalomvezérlő stílusát a Word-dokumentumban az Aspose.Words for .NET segítségével.