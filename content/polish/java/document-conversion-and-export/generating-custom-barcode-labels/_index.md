---
title: Generowanie niestandardowych etykiet z kodem kreskowym w Aspose.Words dla Java
linktitle: Generowanie niestandardowych etykiet z kodem kreskowym
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Generuj niestandardowe etykiety z kodem kreskowym w Aspose.Words for Java. Dowiedz się, jak tworzyć spersonalizowane rozwiązania z kodem kreskowym za pomocą Aspose.Words for Java w tym przewodniku krok po kroku.
type: docs
weight: 10
url: /pl/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Wprowadzenie do generowania niestandardowych etykiet z kodem kreskowym w Aspose.Words dla Java

W tym kompleksowym przewodniku zagłębimy się w proces generowania niestandardowych etykiet z kodem kreskowym przy użyciu Aspose.Words for Java. Aspose.Words for Java to potężne API, które pozwala programistom programowo manipulować dokumentami Word. Jedną z jego niezwykłych cech jest możliwość pracy z etykietami z kodem kreskowym, co czyni go cennym narzędziem dla firm i organizacji, które wymagają niestandardowych rozwiązań z kodem kreskowym.

## Wymagania wstępne

Zanim zagłębimy się w szczegóły dotyczące generowania niestandardowych etykiet z kodem kreskowym, upewnijmy się, że spełniliśmy następujące wymagania:

1. Środowisko programistyczne Java: Upewnij się, że w systemie zainstalowana jest Java i zintegrowane środowisko programistyczne (IDE).

2.  Aspose.Words dla Java: Pobierz i zainstaluj Aspose.Words dla Java z[Tutaj](https://releases.aspose.com/words/java/).

3. Podstawowa znajomość języka Java: Znajomość programowania w języku Java będzie pomocna, ponieważ będziemy pisać kod Java służący do tworzenia niestandardowych etykiet z kodami kreskowymi.

## Tworzenie niestandardowych etykiet z kodem kreskowym

Teraz zacznijmy tworzyć niestandardowe etykiety z kodem kreskowym za pomocą Aspose.Words for Java. Podzielimy proces na kroki i podamy fragmenty kodu Java dla każdego kroku.

## Ustawianie wysokości kodu kreskowego

Na początek musimy ustawić wysokość naszego kodu kreskowego w twipach (1/1440 cala). Następnie przekonwertujemy tę wartość na milimetry (mm). Oto kod, który to umożliwia:

```java
	// Wartość wejściowa jest podana w 1/1440 cala (twipach)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Przelicz na mm
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Konwersja koloru obrazu kodu kreskowego

Następnie przekonwertujemy kolor obrazu kodu kreskowego z Worda na Aspose.BarCode. Kolor wejściowy powinien być w formacie „0xRRGGBB” (szesnastkowy). Oto kod konwersji:

```java
/// <podsumowanie>
/// Konwertuje kolor obrazu kodu kreskowego z programu Word na Aspose.BarCode.
/// </podsumowanie>
/// <param name="inputColor"></param>
/// <zwroty></zwroty>
private static Color convertColor(String inputColor) throws Exception {
	// Dane wejściowe powinny być od „0x000000” do „0xFFFFFF”
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Konwersja współczynnika skalowania kodu kreskowego

Teraz przekonwertujemy współczynnik skalowania kodu kreskowego z procentowego na wartość zmiennoprzecinkową. Ten współczynnik skalowania określa rozmiar kodu kreskowego. Oto kod konwersji:

```java
/// <podsumowanie>
/// Konwertuje współczynnik skalowania kodu kreskowego z procentowego na zmiennoprzecinkowy.
/// </podsumowanie>
/// <param name="współczynnik skalowania"></param>
/// <zwroty></zwroty>
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

## Implementacja metody GetBarCodeImage()

 W tym kroku wdrożymy`getBarcodeImage`metoda, która generuje obraz kodu kreskowego na podstawie podanych parametrów. Będziemy obsługiwać różne typy kodów kreskowych, ustawiać kolory, dostosowywać wymiary i wiele więcej. Oto kod dla tej metody:

```java
/// <podsumowanie>
/// Implementacja metody GetBarCodeImage() dla interfejsu IBarCodeGenerator.
/// </podsumowanie>
/// <nazwa parametru="parametry"></parametr>
/// <zwroty></zwroty>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Sprawdź, czy podano typ i wartość kodu kreskowego
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// Utwórz generator kodów kreskowych na podstawie typu kodu kreskowego
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// Tutaj obsługuj inne typy kodów kreskowych
	}
	
	// Ustaw tekst kodu kreskowego
	generator.setCodeText(parameters.getBarcodeValue());
	
	// Ustaw kolory kodu kreskowego
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// Ustaw wysokość i wymiary symbolu
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// Dostosuj lokalizację tekstu kodu
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Dodatkowe dostosowania dla kodów QR
	final float SCALE = 2.4f; // Współczynnik skalowania empirycznego do konwersji kodu kreskowego Word na Aspose.BarCode
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
	
	// Zastosuj współczynnik skalowania
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
	
	// Wygeneruj i zwróć obraz kodu kreskowego
	return generator.generateBarCodeImage();
}
```

## Implementacja metody GetOldBarcodeImage()

 W tym kroku wdrożymy`getOldBarcodeImage`metoda, która generuje obrazy kodów kreskowych dla staromodnych kodów kreskowych. Tutaj zajmiemy się konkretnym typem kodu kreskowego, takim jak POSTNET. Oto kod dla tej metody:

```java
/// <podsumowanie>
/// Implementacja metody GetOldBarcodeImage() dla interfejsu IBarCodeGenerator.
/// </podsumowanie>
/// <nazwa parametru="parametry"></parametr>
/// <zwroty></zwroty>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Typ kodu twardego dla staromodnego kodu kreskowego
	return generator.generateBarCodeImage();
}
```

## Wniosek

W tym artykule zbadaliśmy proces generowania niestandardowych etykiet z kodem kreskowym przy użyciu Aspose.Words for Java. Omówiliśmy podstawowe kroki, od ustawiania wysokości kodu kreskowego po implementację metod generowania kodu kreskowego. Aspose.Words for Java umożliwia programistom tworzenie dynamicznych i niestandardowych etykiet z kodem kreskowym, co czyni go cennym narzędziem dla różnych branż.

## Najczęściej zadawane pytania

### Jak mogę zmienić rozmiar generowanego kodu kreskowego?

Możesz dostosować rozmiar wygenerowanego kodu kreskowego, ustawiając wysokość symbolu kodu kreskowego i współczynnik skalowania w dostarczonych fragmentach kodu. Te parametry pozwalają kontrolować wymiary kodu kreskowego zgodnie z Twoimi wymaganiami.

### Czy mogę zmienić kolory kodu kreskowego?

Tak, możesz zmienić kolory kodu kreskowego, określając kolory pierwszego planu i tła w kodzie. Ta personalizacja pozwala dopasować wygląd kodu kreskowego do projektu dokumentu.

### Jakie typy kodów kreskowych są obsługiwane przez Aspose.Words dla Java?

Aspose.Words for Java obsługuje różne typy kodów kreskowych, w tym kody QR, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 i inne. Możesz wybrać typ kodu kreskowego, który odpowiada potrzebom Twojej aplikacji.

### Jak zintegrować wygenerowany kod kreskowy z dokumentem Word?

Aby zintegrować wygenerowany kod kreskowy z dokumentem Word, możesz użyć możliwości manipulacji dokumentami Aspose.Words for Java. Możesz wstawić obraz kodu kreskowego do dokumentu w żądanym miejscu.

### Czy jest dostępny przykładowy kod umożliwiający dalszą personalizację?

 Tak, przykładowe fragmenty kodu i dodatkową dokumentację można znaleźć na stronie referencyjnej Aspose.Words for Java:[Aspose.Words dla Java API Reference](https://reference.aspose.com/words/java/).