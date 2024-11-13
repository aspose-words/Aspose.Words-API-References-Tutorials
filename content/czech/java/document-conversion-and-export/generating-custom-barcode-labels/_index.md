---
title: Generování vlastních štítků s čárovým kódem v Aspose.Words pro Java
linktitle: Generování vlastních štítků s čárovými kódy
second_title: Aspose.Words Java Document Processing API
description: Generujte vlastní štítky s čárovými kódy v Aspose.Words pro Java. V tomto podrobném průvodci se dozvíte, jak vytvářet personalizovaná řešení čárových kódů pomocí Aspose.Words for Java.
type: docs
weight: 10
url: /cs/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Úvod do generování vlastních štítků s čárovým kódem v Aspose.Words pro Javu

V tomto komplexním průvodci se ponoříme do procesu generování vlastních štítků s čárovými kódy pomocí Aspose.Words pro Java. Aspose.Words for Java je výkonné API, které umožňuje vývojářům programově manipulovat s dokumenty Wordu. Jednou z jeho pozoruhodných vlastností je schopnost pracovat se štítky s čárovými kódy, což z něj činí cenný nástroj pro podniky a organizace, které vyžadují přizpůsobená řešení čárových kódů.

## Předpoklady

Než se ponoříme do podrobností o generování vlastních štítků s čárovými kódy, ujistíme se, že máme splněny předpoklady:

1. Vývojové prostředí Java: Ujistěte se, že máte v systému nainstalovanou Javu a integrované vývojové prostředí (IDE).

2.  Aspose.Words for Java: Stáhněte si a nainstalujte Aspose.Words for Java z[zde](https://releases.aspose.com/words/java/).

3. Základní znalost jazyka Java: Znalost programování v jazyce Java bude užitečná, protože budeme psát kód Java pro vytváření vlastních štítků s čárovými kódy.

## Vytváření vlastních štítků s čárovými kódy

Nyní začněme vytvářet vlastní štítky s čárovými kódy pomocí Aspose.Words for Java. Proces rozdělíme do kroků a pro každý krok poskytneme úryvky kódu Java.

## Nastavení výšky čárového kódu

Pro začátek musíme nastavit výšku našeho čárového kódu v twipech (1/1440 palce). Tuto hodnotu pak převedeme na milimetry (mm). Zde je kód, jak toho dosáhnout:

```java
	// Vstupní hodnota je v 1/1440 palcích (twipech)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Převést na mm
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Převod barvy obrázku čárového kódu

Dále převedeme barvu obrázku čárového kódu z Wordu do Aspose.BarCode. Vstupní barva by měla být ve formátu "0xRRGGBB" (hexadecimální). Zde je kód pro konverzi:

```java
/// <souhrn>
/// Převede barvu obrázku čárového kódu z Wordu do Aspose.BarCode.
/// </summary>
/// <param name="inputColor"></param>
/// <returns></returns>
private static Color convertColor(String inputColor) throws Exception {
	// Vstup by měl být od "0x000000" do "0xFFFFFF"
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Převod měřítka čárového kódu

Nyní převedeme faktor měřítka čárového kódu z procent na plovoucí hodnotu. Tento faktor měřítka určuje velikost čárového kódu. Zde je kód pro konverzi:

```java
/// <souhrn>
/// Převede faktor měřítka čárového kódu z procent na plovoucí.
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

## Implementace metody GetBarCodeImage().

 V tomto kroku implementujeme`getBarcodeImage`způsob, který generuje obrázek čárového kódu na základě poskytnutých parametrů. Poradíme si s různými typy čárových kódů, nastavíme barvy, upravíme rozměry a další. Zde je kód pro tuto metodu:

```java
/// <souhrn>
/// Implementace metody GetBarCodeImage() pro rozhraní IBarCodeGenerator.
/// </summary>
/// <param name="parameters"></param>
/// <returns></returns>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Zkontrolujte, zda je uveden typ a hodnota čárového kódu
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// Vytvořte BarcodeGenerator na základě typu čárového kódu
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// Ostatní typy čárových kódů zde vyřešte
	}
	
	// Nastavte text čárového kódu
	generator.setCodeText(parameters.getBarcodeValue());
	
	// Nastavení barev čárových kódů
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// Nastavte výšku a rozměry symbolu
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// Přizpůsobte umístění textu kódu
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Další úpravy pro QR kódy
	final float SCALE = 2.4f; // Empirický faktor měřítka pro převod čárového kódu aplikace Word na Aspose.BarCode
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
	
	// Použít faktor měřítka
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
	
	// Vygenerujte a vraťte obrázek čárového kódu
	return generator.generateBarCodeImage();
}
```

## Implementace metody GetOldBarcodeImage().

 V tomto kroku implementujeme`getOldBarcodeImage`metoda, která generuje obrázky čárových kódů pro staromódní čárové kódy. Zde se budeme zabývat konkrétním typem čárového kódu, jako je POSTNET. Zde je kód pro tuto metodu:

```java
/// <souhrn>
/// Implementace metody GetOldBarcodeImage() pro rozhraní IBarCodeGenerator.
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
	// Typ pevného kódu pro staromódní čárový kód
	return generator.generateBarCodeImage();
}
```

## Závěr

V tomto článku jsme prozkoumali proces generování vlastních štítků s čárovým kódem pomocí Aspose.Words for Java. Probrali jsme základní kroky, od nastavení výšky čárového kódu až po implementaci metod pro generování čárového kódu. Aspose.Words for Java umožňuje vývojářům vytvářet dynamické a přizpůsobené štítky s čárovým kódem, což z něj činí cenný nástroj pro různá průmyslová odvětví.

## FAQ

### Jak mohu upravit velikost vygenerovaného čárového kódu?

Velikost vygenerovaného čárového kódu můžete upravit nastavením výšky symbolu čárového kódu a faktoru měřítka v poskytnutých úryvcích kódu. Tyto parametry vám umožňují řídit rozměry čárového kódu podle vašich požadavků.

### Mohu změnit barvy čárového kódu?

Ano, můžete změnit barvy čárového kódu zadáním barvy popředí a pozadí v kódu. Toto přizpůsobení vám umožní sladit vzhled čárového kódu s designem vašeho dokumentu.

### Které typy čárových kódů podporuje Aspose.Words for Java?

Aspose.Words for Java podporuje různé typy čárových kódů, včetně QR kódů, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 a dalších. Můžete si vybrat typ čárového kódu, který vyhovuje potřebám vaší aplikace.

### Jak integruji vygenerovaný čárový kód do dokumentu aplikace Word?

Chcete-li integrovat vygenerovaný čárový kód do dokumentu aplikace Word, můžete použít funkce Aspose.Words for Java pro manipulaci s dokumenty. Obrázek čárového kódu můžete vložit do dokumentu na požadované místo.

### Je k dispozici nějaký ukázkový kód pro další přizpůsobení?

 Ano, ukázkové úryvky kódu a další dokumentaci naleznete na referenčním webu Aspose.Words for Java:[Aspose.Words for Java API Reference](https://reference.aspose.com/words/java/).