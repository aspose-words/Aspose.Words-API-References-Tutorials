---
title: Generera anpassade streckkodsetiketter i Aspose.Words för Java
linktitle: Generera anpassade streckkodsetiketter
second_title: Aspose.Words Java Document Processing API
description: Generera anpassade streckkodsetiketter i Aspose.Words för Java. Lär dig hur du skapar personliga streckkodslösningar med Aspose.Words för Java i denna steg-för-steg-guide.
type: docs
weight: 10
url: /sv/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Introduktion till att skapa anpassade streckkodsetiketter i Aspose.Words för Java

den här omfattande guiden kommer vi att fördjupa oss i processen att skapa anpassade streckkodsetiketter med Aspose.Words för Java. Aspose.Words för Java är ett kraftfullt API som tillåter utvecklare att manipulera Word-dokument programmatiskt. En av dess anmärkningsvärda egenskaper är förmågan att arbeta med streckkodsetiketter, vilket gör det till ett värdefullt verktyg för företag och organisationer som kräver skräddarsydda streckkodslösningar.

## Förutsättningar

Innan vi dyker in i detaljerna för att skapa anpassade streckkodsetiketter, låt oss se till att vi har förutsättningarna på plats:

1. Java Development Environment: Se till att du har Java och en Integrated Development Environment (IDE) installerad på ditt system.

2.  Aspose.Words för Java: Ladda ner och installera Aspose.Words för Java från[här](https://releases.aspose.com/words/java/).

3. Grundläggande kunskaper om Java: Bekantskap med Java-programmering kommer att vara till hjälp eftersom vi kommer att skriva Java-kod för att skapa anpassade streckkodsetiketter.

## Skapa anpassade streckkodsetiketter

Låt oss nu börja skapa anpassade streckkodsetiketter med Aspose.Words för Java. Vi delar upp processen i steg och tillhandahåller Java-kodavsnitt för varje steg.

## Ställa in streckkodens höjd

Till att börja med måste vi ställa in höjden på vår streckkod i twips (1/1440 tum). Vi konverterar sedan detta värde till millimeter (mm). Här är koden för att åstadkomma detta:

```java
	// Inmatningsvärdet är i 1/1440 tum (twips)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Konvertera till mm
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Konvertera streckkodsbildfärg

Därefter konverterar vi streckkodens bildfärg från Word till Aspose.BarCode. Inmatningsfärgen ska vara i formatet "0xRRGGBB" (hexadecimal). Här är koden för konverteringen:

```java
/// <sammanfattning>
/// Konverterar streckkodsbildens färg från Word till Aspose.BarCode.
/// </summary>
/// <param name="inputColor"></param>
/// <returns></returns>
private static Color convertColor(String inputColor) throws Exception {
	// Indata ska vara från "0x000000" till "0xFFFFFF"
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Konvertera streckkodsskalningsfaktor

Nu konverterar vi streckkodens skalningsfaktor från en procentsats till ett flytande värde. Denna skalningsfaktor bestämmer storleken på streckkoden. Här är koden för konverteringen:

```java
/// <sammanfattning>
/// Konverterar streckkodsskalningsfaktor från procent till flytande.
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

## Implementering av GetBarCodeImage()-metoden

 I det här steget kommer vi att implementera`getBarcodeImage` metod, som genererar streckkodsbilden baserat på de angivna parametrarna. Vi kommer att hantera olika streckkodstyper, ställa in färger, justera mått och mer. Här är koden för denna metod:

```java
/// <sammanfattning>
/// Implementering av metoden GetBarCodeImage() för IBarCodeGenerator-gränssnittet.
/// </summary>
/// <param name="parameters"></param>
/// <returns></returns>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Kontrollera om streckkodstyp och värde anges
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// Skapa en BarcodeGenerator baserat på streckkodstypen
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// Hantera andra streckkodstyper här
	}
	
	// Ställ in streckkodstexten
	generator.setCodeText(parameters.getBarcodeValue());
	
	// Ställ in streckkodsfärger
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// Ställ in symbolhöjd och dimensioner
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	//Anpassa kodtextens plats
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Ytterligare justeringar för QR-koder
	final float SCALE = 2.4f; // Empirisk skalningsfaktor för att konvertera Word streckkod till Aspose.BarCode
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
	
	// Använd skalningsfaktor
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
	
	// Generera och returnera streckkodsbilden
	return generator.generateBarCodeImage();
}
```

## Implementering av metoden GetOldBarcodeImage()

 I det här steget kommer vi att implementera`getOldBarcodeImage` metod, som genererar streckkodsbilder för gammaldags streckkoder. Här kommer vi att hantera en specifik streckkodstyp, såsom POSTNET. Här är koden för denna metod:

```java
/// <sammanfattning>
/// Implementering av metoden GetOldBarcodeImage() för IBarCodeGenerator-gränssnittet.
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
	// Hårdkodstyp för gammaldags streckkod
	return generator.generateBarCodeImage();
}
```

## Slutsats

I den här artikeln har vi utforskat processen för att skapa anpassade streckkodsetiketter med Aspose.Words för Java. Vi täckte viktiga steg, från att ställa in streckkodens höjd till att implementera metoder för generering av streckkoder. Aspose.Words för Java ger utvecklare möjlighet att skapa dynamiska och anpassade streckkodsetiketter, vilket gör det till ett värdefullt verktyg för olika branscher.

## FAQ's

### Hur kan jag justera storleken på den genererade streckkoden?

Du kan justera storleken på den genererade streckkoden genom att ställa in streckkodens symbolhöjd och skalningsfaktor i de medföljande kodavsnitten. Dessa parametrar låter dig styra streckkodens dimensioner enligt dina krav.

### Kan jag ändra färgerna på streckkoden?

Ja, du kan ändra streckkodens färger genom att ange förgrunds- och bakgrundsfärgerna i koden. Denna anpassning låter dig matcha streckkodens utseende med ditt dokuments design.

### Vilka streckkodstyper stöds av Aspose.Words för Java?

Aspose.Words för Java stöder olika streckkodstyper, inklusive QR-koder, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 och mer. Du kan välja den streckkodstyp som passar din applikations behov.

### Hur integrerar jag den genererade streckkoden i mitt Word-dokument?

För att integrera den genererade streckkoden i ditt Word-dokument kan du använda Aspose.Words för Javas dokumenthanteringsfunktioner. Du kan infoga streckkodsbilden i ditt dokument på önskad plats.

### Finns det någon exempelkod tillgänglig för ytterligare anpassning?

 Ja, du kan hitta exempel på kodavsnitt och ytterligare dokumentation på Aspose.Words för Javas referenswebbplats:[Aspose.Words för Java API Referens](https://reference.aspose.com/words/java/).