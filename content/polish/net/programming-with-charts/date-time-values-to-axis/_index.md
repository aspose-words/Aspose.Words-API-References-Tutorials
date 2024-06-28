---
title: Dodaj wartości daty i godziny do osi wykresu
linktitle: Dodaj wartości daty i godziny do osi wykresu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodać wartości daty i czasu do osi wykresu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-charts/date-time-values-to-axis/
---

W tym samouczku wyjaśniono, jak dodać wartości daty i godziny do osi wykresu za pomocą Aspose.Words dla .NET.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Zacznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz nowy dokument i narzędzie DocumentBuider
 Utwórz nową instancję`Document` klasa i A`DocumentBuilder` sprzeciwić się pracy z dokumentem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstaw i skonfiguruj kształt wykresu
 Wstaw kształt wykresu do dokumentu za pomocą`InsertChart` metoda`DocumentBuilder` obiekt. Ustaw żądany typ wykresu i wymiary.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Krok 4: Dodaj dane do wykresu
Dodaj dane do serii wykresów, w tym wartości daty i godziny.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Krok 5: Skonfiguruj oś
Skonfiguruj oś X wykresu, aby wyświetlała wartości daty i godziny.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Krok 6: Zapisz dokument
 Zapisz dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithCharts.DateTimeValuesToAxis.docx”.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Przykładowy kod źródłowy wartości daty i godziny do osi przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Ustaw główne jednostki na tydzień, a mniejsze jednostki na dzień.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Ten przykładowy kod tworzy nowy dokument Worda, wstawia wykres kolumnowy z wartościami daty i godziny na osi X i zapisuje dokument we wskazanym katalogu.

## Wniosek
tym samouczku nauczyłeś się dodawać wartości daty i godziny do osi wykresu za pomocą Aspose.Words dla .NET. Postępując zgodnie z instrukcją krok po kroku, możesz utworzyć wykres, dodać wartości daty i godziny do serii oraz skonfigurować oś tak, aby dokładnie wyświetlała wartości daty i godziny. Aspose.Words dla .NET zapewnia potężny zestaw funkcji do przetwarzania słów z wykresami w dokumentach Word, umożliwiając efektywne reprezentowanie i wizualizację danych z wartościami daty i godziny.

### Często zadawane pytania

#### Pytanie 1. Czy mogę dodać wartości daty i czasu do osi wykresu za pomocą Aspose.Words dla .NET?
Tak, dzięki Aspose.Words dla .NET możesz dodawać i wyświetlać wartości daty i godziny na osi wykresu w dokumencie Word. Aspose.Words zapewnia interfejsy API i funkcjonalności umożliwiające pracę z różnymi typami wykresów i dostosowywanie ich wyglądu, w tym obsługę wartości daty i godziny na osi.

#### Pytanie 2. Jak dodać wartości daty i godziny do serii wykresów?
 Aby dodać wartości daty i godziny do serii wykresów, możesz użyć opcji`Add`metoda szeregów wykresu. Podaj tablicę wartości daty i czasu jako dane kategorii (oś X) wraz z odpowiednimi wartościami serii. Pozwala to na wykreślenie punktów danych z wartościami daty i godziny na wykresie.

#### Pytanie 3. Jak skonfigurować oś, aby wyświetlała wartości daty i godziny?
 Możesz skonfigurować oś wykresu tak, aby wyświetlała wartości daty i czasu, ustawiając odpowiednie właściwości. Na przykład możesz określić minimalne i maksymalne wartości osi za pomocą`Scaling.Minimum` I`Scaling.Maximum` właściwości, odpowiednio. Dodatkowo można ustawić jednostki główne i poboczne w celu zdefiniowania odstępu i znaczników osi.
