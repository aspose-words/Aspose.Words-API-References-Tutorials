---
title: Generowanie niestandardowych etykiet z kodami kreskowymi w Aspose.Words dla Java
linktitle: Generowanie niestandardowych etykiet z kodami kreskowymi
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Generuj niestandardowe etykiety z kodami kreskowymi w Aspose.Words dla Java. Dowiedz się, jak tworzyć spersonalizowane rozwiązania w zakresie kodów kreskowych przy użyciu Aspose.Words dla Java w tym przewodniku krok po kroku.
type: docs
weight: 10
url: /pl/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Wprowadzenie do generowania niestandardowych etykiet z kodami kreskowymi w Aspose.Words dla Java

tym obszernym przewodniku zagłębimy się w proces generowania niestandardowych etykiet z kodami kreskowymi za pomocą Aspose.Words dla Java. Aspose.Words for Java to potężny interfejs API, który umożliwia programistom programowe manipulowanie dokumentami programu Word. Jedną z jego niezwykłych funkcji jest możliwość pracy z etykietami z kodami kreskowymi, co czyni go cennym narzędziem dla firm i organizacji wymagających niestandardowych rozwiązań w zakresie kodów kreskowych.

## Warunki wstępne

Zanim zagłębimy się w szczegóły generowania niestandardowych etykiet z kodami kreskowymi, upewnijmy się, że mamy spełnione wymagania wstępne:

1. Środowisko programistyczne Java: Upewnij się, że w systemie jest zainstalowana Java i zintegrowane środowisko programistyczne (IDE).

2.  Aspose.Words dla Java: Pobierz i zainstaluj Aspose.Words dla Java z[Tutaj](https://releases.aspose.com/words/java/).

3. Podstawowa znajomość języka Java: Znajomość programowania w języku Java będzie pomocna, gdy będziemy pisać kod w języku Java w celu tworzenia niestandardowych etykiet z kodami kreskowymi.

## Tworzenie niestandardowych etykiet z kodami kreskowymi

Teraz zacznijmy tworzyć niestandardowe etykiety z kodami kreskowymi za pomocą Aspose.Words dla Java. Podzielimy proces na etapy i udostępnimy fragmenty kodu Java dla każdego kroku.

## Ustawianie wysokości kodu kreskowego

Na początek musimy ustawić wysokość naszego kodu kreskowego w twipsach (1/1440 cala). Następnie przekonwertujemy tę wartość na milimetry (mm). Oto kod, aby to osiągnąć:

```java
	// Wartość wejściowa jest wyrażona w 1/1440 cala (twipach)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Zamień na mm
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Konwersja koloru obrazu kodu kreskowego

Następnie przekonwertujemy kolor obrazu kodu kreskowego z programu Word na Aspose.BarCode. Kolor wejściowy powinien mieć format „0xRRGGBB” (szesnastkowy). Oto kod konwersji:

```java
/// <podsumowanie>
/// Konwertuje kolor obrazu kodu kreskowego z programu Word na Aspose.BarCode.
/// </podsumowanie>
/// <param name="inputColor"></param>
/// <powroty></powroty>
private static Color convertColor(String inputColor) throws Exception {
	// Dane wejściowe powinny mieć wartość od „0x000000” do „0xFFFFFF”
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Konwersja współczynnika skalowania kodu kreskowego

Teraz przekonwertujemy współczynnik skalowania kodu kreskowego z wartości procentowej na wartość zmiennoprzecinkową. Ten współczynnik skalowania określa rozmiar kodu kreskowego. Oto kod konwersji:

```java
/// <podsumowanie>
/// Konwertuje współczynnik skalowania kodu kreskowego z procentu na wartość zmiennoprzecinkową.
/// </podsumowanie>
/// <param name="scalingFactor"></param>
/// <powroty></powroty>
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

## Implementacja metody GetBarCodeImage().

 Na tym etapie zaimplementujemy`getBarcodeImage` metodę, która generuje obraz kodu kreskowego na podstawie podanych parametrów. Zajmiemy się różnymi typami kodów kreskowych, ustawimy kolory, dostosujemy wymiary i nie tylko. Oto kod tej metody:

```java
/// <podsumowanie>
/// Implementacja metody GetBarCodeImage() dla interfejsu IBarCodeGenerator.
/// </podsumowanie>
/// <param name="parametry"></param>
/// <powroty></powroty>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Sprawdź, czy podany jest typ i wartość kodu kreskowego
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
		// Tutaj obsłużysz inne typy kodów kreskowych
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
	
	//Dostosuj lokalizację tekstu kodu
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Dodatkowe dostosowania dla kodów QR
	final float SCALE = 2.4f; // Empiryczny współczynnik skalowania do konwersji kodu kreskowego Word na Aspose.BarCode
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

## Implementacja metody GetOldBarcodeImage().

 Na tym etapie zaimplementujemy`getOldBarcodeImage` metoda, która generuje obrazy kodów kreskowych dla staromodnych kodów kreskowych. Tutaj zajmiemy się konkretnym typem kodu kreskowego, takim jak POSTNET. Oto kod tej metody:

```java
/// <podsumowanie>
/// Implementacja metody GetOldBarcodeImage() dla interfejsu IBarCodeGenerator.
/// </podsumowanie>
/// <param name="parametry"></param>
/// <powroty></powroty>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Typ kodu stałego dla staromodnego kodu kreskowego
	return generator.generateBarCodeImage();
}
```

## Wniosek

W tym artykule zbadaliśmy proces generowania niestandardowych etykiet z kodami kreskowymi przy użyciu Aspose.Words dla Java. Omówiliśmy najważniejsze etapy, od ustawienia wysokości kodu kreskowego po wdrożenie metod generowania kodu kreskowego. Aspose.Words dla Java umożliwia programistom tworzenie dynamicznych i niestandardowych etykiet z kodami kreskowymi, co czyni go cennym narzędziem dla różnych branż.

## Często zadawane pytania

### Jak mogę dostosować rozmiar wygenerowanego kodu kreskowego?

Możesz dostosować rozmiar wygenerowanego kodu kreskowego, ustawiając wysokość symbolu kodu kreskowego i współczynnik skalowania w dostarczonych fragmentach kodu. Parametry te pozwalają na kontrolę wymiarów kodu kreskowego według własnych potrzeb.

### Czy mogę zmienić kolory kodu kreskowego?

Tak, możesz zmienić kolory kodu kreskowego, określając kolor pierwszego planu i tła w kodzie. To dostosowanie pozwala dopasować wygląd kodu kreskowego do projektu dokumentu.

### Jakie typy kodów kreskowych są obsługiwane przez Aspose.Words dla Java?

Aspose.Words dla Java obsługuje różne typy kodów kreskowych, w tym kody QR, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 i inne. Możesz wybrać typ kodu kreskowego odpowiadający potrzebom Twojej aplikacji.

### Jak zintegrować wygenerowany kod kreskowy z dokumentem programu Word?

Aby zintegrować wygenerowany kod kreskowy z dokumentem Word, możesz użyć Aspose.Words do obsługi dokumentów w Javie. Możesz wstawić obraz kodu kreskowego do dokumentu w żądanym miejscu.

### Czy dostępny jest przykładowy kod umożliwiający dalsze dostosowywanie?

 Tak, przykładowe fragmenty kodu i dodatkową dokumentację można znaleźć w witrynie referencyjnej Aspose.Words for Java:[Aspose.Words dla odniesienia do API Java](https://reference.aspose.com/words/java/).