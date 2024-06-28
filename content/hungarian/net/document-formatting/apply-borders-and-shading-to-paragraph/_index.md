---
title: Szegélyek és árnyékolások alkalmazása a Word-dokumentum bekezdésére
linktitle: Szegélyek és árnyékolások alkalmazása a Word-dokumentum bekezdésére
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan alkalmazhat szegélyeket és árnyékolást egy bekezdésre Word dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
Ebben az oktatóanyagban bemutatjuk, hogyan alkalmazhat szegélyeket és árnyékolást egy bekezdésre Word dokumentumban az Aspose.Words for .NET funkciójával. Kövesse az alábbi lépéseket a forráskód megértéséhez és a formázási módosítások alkalmazásához.

## 1. lépés: A dokumentum létrehozása és konfigurálása

Kezdésként hozzon létre egy új dokumentumot és egy kapcsolódó DocumentBuilder objektumot. Itt van, hogyan:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Szegély beállítása

Most állítsuk be a bekezdés határait úgy, hogy minden oldalhoz megadjuk a szegélystílust. Itt van, hogyan:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## 3. lépés: Kitöltés beállítása

Most konfiguráljuk a bekezdés kitöltését a textúra és a kitöltési színek megadásával. Itt van, hogyan:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## 4. lépés: Tartalom hozzáadása

Néhány formázott tartalmat fogunk hozzáadni a bekezdéshez. Itt van, hogyan:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## 3. lépés: A dokumentum mentése

 A szövegbeviteli űrlapmező beszúrása után mentse a dokumentumot a kívánt helyre a gombbal`Save` módszer. Ügyeljen arra, hogy megadja a megfelelő fájl elérési utat:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Példa forráskódra a Szegélyek és árnyékolás alkalmazása bekezdéshez az Aspose.Words for .NET használatával

Íme az Aspose.Words for .NET Szegélyek alkalmazása és árnyékolás a bekezdéshez funkció teljes forráskódja:

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## Következtetés

 Ebben az oktatóanyagban megtanultuk, hogyan lehet szegélyeket és árnyékolást alkalmazni egy Word-dokumentum bekezdésére az Aspose.Words for .NET használatával. A bekezdések beállításával`Borders` és`Shading` tulajdonságokkal, be tudtuk állítani a bekezdés keretének stílusát, vonalszínét és kitöltési színét. Az Aspose.Words for .NET hatékony formázási lehetőségeket biztosít a bekezdések megjelenésének testreszabásához és a dokumentumok vizuális megjelenítésének javításához.

### GYIK

#### K: Hogyan alkalmazhatok szegélyeket és árnyékolást egy Word-dokumentum bekezdésében az Aspose.Words for .NET használatával?

V: Ha egy Word-dokumentumban az Aspose.Words for .NET használatával szeretne szegélyeket és árnyékolást alkalmazni, kövesse az alábbi lépéseket:
1.  Hozzon létre egy új dokumentumot, és a`DocumentBuilder` tárgy.
2.  Állítsa be a bekezdés szegélyeit a`Borders` tulajdona a`ParagraphFormat` és állítsa be a szegélystílust mindkét oldalhoz.
3. Konfigurálja a bekezdés kitöltését a`Shading` tulajdona a`ParagraphFormat` valamint a textúra és a kitöltési színek megadása.
4.  Adjon hozzá tartalmat a bekezdéshez a`Write` módszere a`DocumentBuilder`.
5.  Mentse el a dokumentumot a`Save` módszer.

#### K: Hogyan állíthatom be a szegélystílust a bekezdés mindkét oldalán?

 V: A bekezdés mindkét oldalának szegélystílusának beállításához elérheti a`Borders` tulajdona a`ParagraphFormat` és állítsa be a`LineStyle` ingatlan mindegyiknek`BorderType` (például.,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). Különféle vonalstílusokat adhat meg, mint pl`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`stb.

#### K: Hogyan adhatom meg a textúrát és a kitöltési színeket a bekezdésárnyékoláshoz?

 V: A bekezdésárnyékolás textúrájának és kitöltési színeinek megadásához elérheti a`Shading` tulajdona a`ParagraphFormat` és állítsa be a`Texture` tulajdonság egy kívánt textúra indexhez (pl.`TextureIndex.TextureDiagonalCross` ). Azt is beállíthatja a`BackgroundPatternColor` és`ForegroundPatternColor` tulajdonságait a kívánt színekhez a segítségével`System.Drawing.Color` osztály.