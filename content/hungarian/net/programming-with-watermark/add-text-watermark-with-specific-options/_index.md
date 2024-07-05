---
title: Szöveg vízjel hozzáadása meghatározott beállításokkal
linktitle: Szöveg vízjel hozzáadása meghatározott beállításokkal
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan adhat hozzá szöveges vízjelet meghatározott beállításokkal az Aspose.Words for .NET használatával. Lépésről lépésre útmutató.
type: docs
weight: 10
url: /hu/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

Ebben az oktatóanyagban végigvezetjük, hogyan adhat hozzá szöveges vízjelet meghatározott beállításokkal az Aspose.Words for .NET használatával. A szöveges vízjel egy dokumentumra ráhelyezett szöveg, amely jelzi, hogy az egy piszkozat, bizalmas stb.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: A dokumentum betöltése

Egy meglévő dokumentumot töltünk be a dokumentum elérési útjával.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## 3. lépés: Adjon hozzá szöveges vízjelet meghatározott beállításokkal

 Létrehozunk egy példányt a`TextWatermarkOptions`osztályt, és állítsa be a szöveges vízjel kívánt beállításait.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## 4. lépés: Mentse el a dokumentumot

Végül elmenthetjük a dokumentumot a hozzáadott szöveges vízjellel.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Példa forráskód szöveges vízjel hozzáadására meghatározott beállításokkal az Aspose.Words for .NET segítségével

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Gratulálok ! Most megtanulta, hogyan adhat hozzá szöveges vízjelet meghatározott beállításokkal az Aspose.Words for .NET használatával.

