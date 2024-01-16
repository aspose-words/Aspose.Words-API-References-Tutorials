---
title: Dostosuj serię pojedynczych wykresów na wykresie
linktitle: Dostosuj serię pojedynczych wykresów na wykresie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dostosować pojedyncze serie wykresów na wykresie za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-charts/single-chart-series/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do dostosowywania pojedynczych serii wykresów na wykresie. Dostarczony kod źródłowy pokazuje, jak utworzyć wykres, uzyskać dostęp do określonych serii i zmodyfikować ich właściwości.

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

## Krok 3: Uzyskaj dostęp do serii wykresów i dostosuj je

 Aby zmodyfikować serię pojedynczych wykresów, musisz uzyskać dostęp do pliku`ChartSeries` obiekty wykresu.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Krok 4: Zapisz dokument

 Na koniec zapisz dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

To kończy implementację dostosowywania pojedynczej serii wykresów przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla serii pojedynczych wykresów przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Można także określić, czy linia łącząca punkty na wykresie ma być wygładzana za pomocą splajnów Catmull-Rom.
	series0.Smooth = true;
	series1.Smooth = true;
	// Określa, czy element nadrzędny domyślnie odwraca swoje kolory, jeśli wartość jest ujemna.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Wniosek

W tym samouczku nauczyłeś się, jak dostosować pojedynczą serię wykresów na wykresie za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz utworzyć nowy dokument, wstawić wykres liniowy, uzyskać dostęp do określonych serii wykresów i zmodyfikować ich właściwości, aby uzyskać żądane dostosowanie.

Aspose.Words dla .NET zapewnia zaawansowane funkcje do manipulowania wykresami w dokumentach Word. Uzyskując dostęp do poszczególnych serii wykresów, możesz zastosować określone modyfikacje, aby dostosować ich wygląd i zachowanie. Umożliwia to zmianę nazwy serii, włączenie wygładzania linii wykresu, dostosowanie znaczników punktów danych, odwrócenie kolorów dla wartości ujemnych i wiele więcej, aby poprawić wizualną reprezentację wykresu.

Dostosowywanie pojedynczej serii wykresów zapewnia elastyczność wyróżniania określonych danych lub podkreślania określonych trendów na wykresie. Dzięki Aspose.Words dla .NET możesz łatwo uzyskać dostęp do właściwości serii wykresów i je modyfikować, umożliwiając tworzenie atrakcyjnych wizualnie i bogatych w informacje wykresów w dokumentach programu Word.

### Często zadawane pytania

#### Pytanie 1. Czy mogę dostosować wiele serii wykresów na jednym wykresie?
 Tak, możesz dostosować wiele serii wykresów na wykresie za pomocą Aspose.Words dla .NET. Uzyskując dostęp do`ChartSeries`obiektów na wykresie, możesz wybierać i modyfikować wiele serii na podstawie ich indeksów lub określonych kryteriów. Użyj pętli lub indywidualnych przypisań, aby zmodyfikować żądane właściwości każdej serii wykresów. W ten sposób możesz zastosować różne dostosowania do wielu serii na tym samym wykresie.

#### Pytanie 2. Jak zmienić nazwę serii wykresów?
 Aby zmienić nazwę serii wykresów na wykresie za pomocą Aspose.Words dla .NET, musisz uzyskać dostęp do`Name` własność`ChartSeries` obiekt i ustaw mu żądaną nazwę. Nazwa serii jest zwykle wyświetlana w legendzie wykresu lub etykietach danych, zapewniając opisową etykietę serii. Modyfikując nazwę serii, można nadać zrozumiałe nazwy, które odzwierciedlają dane reprezentowane przez każdą serię.

#### Pytanie 3. Co to jest wygładzanie serii wykresów?
Wygładzanie serii wykresów to technika poprawy wizualnej, która pozwala utworzyć gładką linię łączącą punkty na wykresie. Stosuje algorytm wygładzania, taki jak splajny Catmull-Rom, do interpolacji między punktami danych i tworzenia przyjemnej wizualnie krzywej. Aby włączyć wygładzanie serii na wykresie za pomocą Aspose.Words dla .NET, przejdź do`Smooth` własność`ChartSeries` obiekt i ustaw go na`true`. Wygładzanie może być przydatne do wyświetlania trendów lub wzorców w danych o nieregularnych wahaniach.

#### Pytanie 4. Jak dostosować znaczniki punktów danych w serii wykresów?
 Aby dostosować znaczniki punktów danych w serii wykresów za pomocą Aspose.Words dla .NET, musisz uzyskać dostęp do`Marker` własność`ChartSeries` obiektu i modyfikować jego właściwości, takie jak`Symbol` I`Size`. Markery to wizualne wskaźniki umieszczane na wykresie w celu przedstawienia poszczególnych punktów danych. Można wybierać spośród wielu wbudowanych symboli znaczników i dostosowywać ich rozmiar, aby wyróżnić lub rozróżnić określone punkty danych w serii.

#### Pytanie 5. Czy mogę odwrócić kolory wartości ujemnych w serii wykresów?
 Tak, możesz odwracać kolory wartości ujemnych w serii wykresów za pomocą Aspose.Words dla .NET. Ustawiając`InvertIfNegative` własność`ChartSeries` oponować`true`, kolory punktów danych o wartościach ujemnych zostaną odwrócone, dzięki czemu będą wizualnie odmienne od wartości dodatnich. Ta funkcja może być przydatna podczas porównywania wartości dodatnich i ujemnych w serii wykresów, zapewniając wyraźne rozróżnienie między nimi.