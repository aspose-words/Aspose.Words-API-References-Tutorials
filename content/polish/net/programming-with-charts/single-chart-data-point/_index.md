---
title: Dostosuj pojedynczy punkt danych na wykresie
linktitle: Dostosuj pojedynczy punkt danych na wykresie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dostosować pojedynczy punkt danych na wykresie za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-charts/single-chart-data-point/
---

tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do dostosowywania pojedynczego punktu danych na wykresie. Dostarczony kod źródłowy pokazuje, jak utworzyć wykres, uzyskać dostęp do określonych punktów danych i zmodyfikować ich właściwości.

## Krok 1: Skonfiguruj projekt

Upewnij się, że masz następujące wymagania wstępne:

- Zainstalowana biblioteka Aspose.Words dla .NET. Można go pobrać, używając menedżera pakietów NuGet do zainstalowania.
- Ścieżka katalogu dokumentu, w którym zostanie zapisany dokument wyjściowy.

## Krok 2: Utwórz nowy dokument i wstaw wykres

 Stwórz nowy`Document` obiekt i a`DocumentBuilder` do zbudowania dokumentu.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Następnie użyj`InsertChart` metoda`DocumentBuilder` , aby wstawić wykres liniowy do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Uzyskaj dostęp i dostosuj punkty danych

 Aby zmodyfikować poszczególne punkty danych, należy uzyskać dostęp do pliku`ChartDataPointCollection` serii i wybierz żądany punkt danych za pomocą indeksu.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## Krok 4: Zapisz dokument

 Na koniec zapisz dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

To kończy implementację dostosowywania pojedynczego punktu danych na wykresie przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla pojedynczego punktu danych na wykresie przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Wniosek

W tym samouczku nauczyłeś się, jak dostosować pojedynczy punkt danych na wykresie za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz utworzyć nowy dokument, wstawić wykres liniowy, uzyskać dostęp do określonych punktów danych w serii wykresów i zmodyfikować ich właściwości, aby uzyskać żądane dostosowanie.

Aspose.Words dla .NET zapewnia zaawansowane funkcje do manipulowania wykresami w dokumentach Word. Uzyskując dostęp do poszczególnych punktów danych w serii wykresów, możesz zastosować określone modyfikacje, aby dostosować ich wygląd i zachowanie. Umożliwia to wyróżnianie określonych punktów danych, zmianę symboli znaczników, dostosowywanie rozmiarów znaczników i wykonywanie innych czynności w celu ulepszenia wizualnej reprezentacji wykresu.

Dostosowywanie poszczególnych punktów danych zapewnia elastyczność podkreślania ważnych danych lub wyróżniania określonych trendów na wykresie. Dzięki Aspose.Words dla .NET możesz łatwo uzyskać dostęp i modyfikować punkty danych na różnych typach wykresów, umożliwiając tworzenie atrakcyjnych wizualnie i bogatych w informacje wykresów w dokumentach Word.

### Często zadawane pytania

#### Pytanie 1. Czy mogę dostosować wiele punktów danych na wykresie?
 Tak, możesz dostosować wiele punktów danych na wykresie za pomocą Aspose.Words dla .NET. Uzyskując dostęp do`ChartDataPointCollection`serii, można wybierać i modyfikować wiele punktów danych w oparciu o ich indeksy. Użyj pętli lub indywidualnych przypisań, aby zmodyfikować żądane właściwości każdego punktu danych. W ten sposób możesz zastosować różne dostosowania do wielu punktów danych na tym samym wykresie.

#### Pytanie 2. Jak mogę zmienić symbol znacznika punktu danych?
 Aby zmienić symbol znacznika punktu danych na wykresie przy użyciu Aspose.Words dla .NET, musisz uzyskać dostęp do`Marker` własność`ChartDataPoint` obiekt i ustaw`Symbol` właściwość do żądanego symbolu znacznika. Symbole znaczników reprezentują kształt lub ikonę używaną do reprezentowania każdego punktu danych na wykresie. Możesz wybierać spośród wielu wbudowanych symboli znaczników, takich jak okrąg, kwadrat, romb, trójkąt, gwiazda i inne.

#### Pytanie 3. Czy mogę dostosować rozmiar znacznika punktu danych?
 Tak, możesz dostosować rozmiar znacznika punktu danych na wykresie za pomocą Aspose.Words dla .NET. Uzyskać dostęp do`Marker` własność`ChartDataPoint` obiekt i ustaw`Size`właściwość do żądanego rozmiaru znacznika. Rozmiar znacznika jest zwykle podawany w punktach, gdzie większa wartość oznacza większy rozmiar znacznika. Dostosowanie rozmiaru znacznika pozwala uwypuklić określone punkty danych lub rozróżnić je na podstawie ich znaczenia.

#### Pytanie 4. Jakie inne właściwości mogę modyfikować dla punktu danych?
Aspose.Words dla .NET udostępnia szereg właściwości, które można modyfikować dla punktu danych na wykresie. Niektóre z często modyfikowanych właściwości obejmują symbol znacznika, rozmiar znacznika, kolor znacznika, widoczność etykiety danych, eksplozję, odwrócenie, jeśli jest ujemne i inne. Właściwości te umożliwiają dostosowanie wyglądu, zachowania i interaktywności poszczególnych punktów danych, umożliwiając tworzenie wykresów dostosowanych do konkretnych wymagań.

#### Pytanie 5. Czy mogę dostosować punkty danych na wykresach innych typów?
Tak, możesz dostosować punkty danych na różnych typach wykresów za pomocą Aspose.Words dla .NET. Chociaż w tym samouczku przedstawiono dostosowywanie punktów danych na wykresie liniowym, podobne techniki można zastosować do innych typów wykresów, takich jak wykresy kolumnowe, wykresy słupkowe, wykresy kołowe i inne. Proces ten obejmuje dostęp do serii i punktów danych na wykresie oraz odpowiednią modyfikację ich właściwości.