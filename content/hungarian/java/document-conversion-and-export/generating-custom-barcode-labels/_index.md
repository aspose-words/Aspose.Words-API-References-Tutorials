---
title: Egyéni vonalkód-címkék generálása az Aspose.Words for Java programban
linktitle: Egyéni vonalkód címkék generálása
second_title: Aspose.Words Java Document Processing API
description: Hozzon létre egyéni vonalkódcímkéket az Aspose.Words for Java programban. Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan hozhat létre személyre szabott vonalkód-megoldásokat az Aspose.Words for Java használatával.
type: docs
weight: 10
url: /hu/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Bevezetés az egyéni vonalkódcímkék generálásához az Aspose.Words for Java programban

Ebben az átfogó útmutatóban az Aspose.Words for Java használatával egyéni vonalkódcímkék létrehozásának folyamatát mutatjuk be. Az Aspose.Words for Java egy hatékony API, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék a Word dokumentumokat. Egyik figyelemreméltó tulajdonsága a vonalkódcímkékkel való munkavégzés képessége, így értékes eszközzé válik azon vállalkozások és szervezetek számára, amelyek testreszabott vonalkód-megoldásokat igényelnek.

## Előfeltételek

Mielőtt belemerülnénk az egyéni vonalkódcímkék létrehozásának részleteibe, győződjünk meg arról, hogy megvannak az előfeltételek:

1. Java fejlesztői környezet: Győződjön meg arról, hogy a Java és az Integrated Development Environment (IDE) telepítve van a rendszeren.

2.  Aspose.Words for Java: Töltse le és telepítse az Aspose.Words for Java programot innen[itt](https://releases.aspose.com/words/java/).

3. Alapvető Java ismeretek: A Java programozás ismerete hasznos lesz, mivel Java kódot írunk az egyedi vonalkódcímkék létrehozásához.

## Egyedi vonalkód címkék létrehozása

Most kezdjük el az egyéni vonalkódcímkék létrehozását az Aspose.Words for Java használatával. A folyamatot lépésekre bontjuk, és minden lépéshez Java-kódrészleteket biztosítunk.

## A vonalkód magasságának beállítása

Kezdésként be kell állítani a vonalkódunk magasságát duplákban (1/1440 hüvelyk). Ezután ezt az értéket átváltjuk milliméterre (mm). Íme a kód ennek végrehajtásához:

```java
	// A bemeneti érték 1/1440 hüvelykben van megadva (twips)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Átalakítás mm-re
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Vonalkód kép színének konvertálása

Ezután a vonalkód kép színét Wordből Aspose.BarCode-ba konvertáljuk. A beviteli szín formátuma "0xRRGGBB" (hexadecimális). Íme az átalakítás kódja:

```java
/// <összefoglaló>
/// Vonalkód kép színét Wordből Aspose.BarCode-ba konvertálja.
/// </summary>
/// <param name="inputColor"></param>
/// <returns></returns>
private static Color convertColor(String inputColor) throws Exception {
	// A beviteli értéknek "0x000000" és "0xFFFFFF" között kell lennie
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Vonalkód skálázási tényező konvertálása

Most a vonalkód skálázási tényezőjét százalékról lebegő értékre konvertáljuk. Ez a méretezési tényező határozza meg a vonalkód méretét. Íme az átalakítás kódja:

```java
/// <összefoglaló>
/// A vonalkód skálázási tényezőjét százalékról lebegővé alakítja.
/// </summary>
/// <param name="scalingFactor"></param>
/// <returns></returns>
private static float convertScalingFactor(String scalingFactor) throws Exception {
	boolean isParsed = false;
	int percent = tryParseInt(scalingFactor);
	if (percent != Integer.MIN_VALUE && percent >= 10 && percent <= 10000)
		isParsed = true;
	if (!isParsed)
		throw new Exception("Error! Incorrect scaling factor - " + scalingFactor + ".");
	return percent / 100.0f;
}
```

## A GetBarCodeImage() metódus megvalósítása

 Ebben a lépésben megvalósítjuk a`getBarcodeImage`módszerrel, amely a megadott paraméterek alapján állítja elő a vonalkód képet. Különböző vonalkód-típusokat kezelünk, színeket állítunk be, méreteket állítunk be és még sok mást. Íme a módszer kódja:

```java
/// <összefoglaló>
/// A GetBarCodeImage() metódus megvalósítása IBarCodeGenerator interfészhez.
/// </summary>
/// <param name="parameters"></param>
/// <returns></returns>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Ellenőrizze, hogy megadta-e a vonalkód típusát és értékét
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// Hozzon létre egy vonalkódgenerátort a vonalkód típusa alapján
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// Itt kezelheti a többi vonalkód típust
	}
	
	// Állítsa be a vonalkód szövegét
	generator.setCodeText(parameters.getBarcodeValue());
	
	// Állítsa be a vonalkód színeit
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// Állítsa be a szimbólum magasságát és méretét
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// A kódszöveg helyének testreszabása
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// További beállítások a QR-kódokhoz
	final float SCALE = 2.4f; // Empirikus méretezési tényező a Word vonalkódjának Aspose.BarCode-ba való konvertálásához
	float xdim = 1.0f;
	if (generator.getBarcodeType().equals(EncodeTypes.QR))
	{
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NEAREST);
		generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageWidth().getInches() * SCALE);
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageWidth().getInches());
		xdim = generator.getParameters().getImageHeight().getInches() / 25;
		generator.getParameters().getBarcode().getXDimension().setInches(xdim);
		generator.getParameters().getBarcode().getBarHeight().setInches(xdim);
	}
	
	// Méretezési tényező alkalmazása
	if (parameters.getScalingFactor() != null)
	{
		float scalingFactor = convertScalingFactor(parameters.getScalingFactor());
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageHeight().getInches() * scalingFactor);
		if (generator.getBarcodeType().equals(EncodeTypes.QR))
		{
			generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageHeight().getInches());
			generator.getParameters().getBarcode().getXDimension().setInches(xdim * scalingFactor);
			generator.getParameters().getBarcode().getBarHeight().setInches(xdim * scalingFactor);
		}
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// Létrehozza és visszaküldi a vonalkód képet
	return generator.generateBarCodeImage();
}
```

## A GetOldBarcodeImage() metódus megvalósítása

 Ebben a lépésben megvalósítjuk a`getOldBarcodeImage`módszerrel, amely vonalkód képeket generál a régimódi vonalkódokhoz. Itt egy adott vonalkódtípust kezelünk, például a POSTNET-et. Íme a módszer kódja:

```java
/// <összefoglaló>
/// A GetOldBarcodeImage() metódus megvalósítása IBarCodeGenerator interfészhez.
/// </summary>
/// <param name="parameters"></param>
/// <returns></returns>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Hardcode típus a régimódi vonalkódhoz
	return generator.generateBarCodeImage();
}
```

## Következtetés

Ebben a cikkben az Aspose.Words for Java használatával egyéni vonalkódcímkék létrehozásának folyamatát vizsgáltuk. Áttekintettük a lényeges lépéseket, a vonalkód magasságának beállításától a vonalkód generálási módszerek megvalósításáig. Az Aspose.Words for Java felhatalmazza a fejlesztőket arra, hogy dinamikus és testreszabott vonalkódcímkéket hozzanak létre, így értékes eszköz a különféle iparágak számára.

## GYIK

### Hogyan állíthatom be a generált vonalkód méretét?

Beállíthatja a generált vonalkód méretét a vonalkód szimbólum magasságának és méretezési tényezőjének beállításával a mellékelt kódrészletekben. Ezek a paraméterek lehetővé teszik a vonalkód méreteinek szabályozását az Ön igényei szerint.

### Megváltoztathatom a vonalkód színeit?

Igen, módosíthatja a vonalkód színeit az előtér és a háttér színének a kódban történő megadásával. Ez a testreszabás lehetővé teszi, hogy a vonalkód megjelenését a dokumentum tervéhez igazítsa.

### Mely vonalkódtípusokat támogatja az Aspose.Words for Java?

Az Aspose.Words for Java különféle vonalkódtípusokat támogat, beleértve a QR-kódokat, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 stb. Kiválaszthatja az alkalmazás igényeinek megfelelő vonalkód típust.

### Hogyan integrálhatom a generált vonalkódot a Word dokumentumomba?

A generált vonalkód Word dokumentumba való integrálásához használhatja az Aspose.Words for Java dokumentumkezelési képességeit. A vonalkód képet a kívánt helyre beillesztheti a dokumentumba.

### Rendelkezésre áll valamilyen mintakód a további testreszabáshoz?

 Igen, mintakódrészleteket és további dokumentációt találhat az Aspose.Words for Java hivatkozási webhelyén:[Aspose.Words for Java API Reference](https://reference.aspose.com/words/java/).