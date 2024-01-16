---
title: Dostosuj etykietę danych wykresu
linktitle: Dostosuj etykietę danych wykresu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodawać i dostosowywać etykiety danych na wykresie za pomocą Aspose.Words dla .NET, aby zapewnić dodatkowe informacje o punktach danych.
type: docs
weight: 10
url: /pl/net/programming-with-charts/chart-data-label/
---

W tym samouczku wyjaśniono, jak dodawać i dostosowywać etykiety danych na wykresie za pomocą Aspose.Words dla .NET. Etykiety danych dostarczają dodatkowych informacji o punktach danych na wykresie.

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

## Krok 3: Wstaw i skonfiguruj wykres
 Wstaw wykres do dokumentu za pomocą`InsertChart` metoda`DocumentBuilder` obiekt. Ustaw żądany typ wykresu i wymiary.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Krok 4: Dostosuj etykiety danych
Uzyskaj dostęp do kolekcji etykiet danych serii wykresów i zmodyfikuj różne właściwości, aby dostosować wygląd etykiet danych.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Krok 5: Zapisz dokument
 Zapisz dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithCharts.ChartDataLabel.docx”.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Przykładowy kod źródłowy etykiety danych wykresu przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// Domyślnie po dodaniu etykiet danych do punktów danych na wykresie kołowym wyświetlane są linie odniesienia dla odpowiednich etykiet danych
	// umieszczone daleko poza końcami punktów danych. Linie odniesienia tworzą wizualne połączenie pomiędzy etykietą danych a jej etykietą
	// odpowiedni punkt danych.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

Otóż to! Pomyślnie dodałeś i dostosowałeś etykiety danych na wykresie za pomocą Aspose.Words dla .NET.

## Wniosek
tym samouczku nauczyłeś się dodawać i dostosowywać etykiety danych na wykresie za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem, możesz wstawić wykres, uzyskać dostęp do kolekcji etykiet danych i zmodyfikować właściwości, aby dostosować wygląd etykiet danych. Aspose.Words dla .NET zapewnia potężny interfejs API do przetwarzania słów z dokumentami i wykresami programu Word, umożliwiając tworzenie atrakcyjnych wizualnie i informacyjnych wykresów z dostosowanymi etykietami danych.

### Często zadawane pytania

#### Pytanie 1. Co to są etykiety danych na wykresie?
Etykiety danych na wykresie dostarczają dodatkowych informacji o punktach danych reprezentowanych na wykresie. Mogą wyświetlać wartości, kategorie, nazwy serii, wartości procentowe lub inne istotne szczegóły w zależności od typu wykresu i konfiguracji.

#### Pytanie 2. Czy mogę dostosować wygląd etykiet danych?
Tak, możesz dostosować wygląd etykiet danych na wykresie. Aspose.Words dla .NET udostępnia opcje modyfikowania różnych właściwości etykiet danych, takich jak pokazywanie kluczy legendy, linii odniesienia, nazw kategorii, nazw serii, wartości i innych. Możesz także ustawić separatory i sformatować etykiety zgodnie ze swoimi specyficznymi wymaganiami.

#### Pytanie 3. Czy mogę dodać etykiety danych do wykresu dowolnego typu?
Tak, możesz dodawać etykiety danych do różnych typów wykresów, w tym wykresów słupkowych, wykresów kołowych, wykresów liniowych i innych. Proces dodawania i dostosowywania etykiet danych może się nieznacznie różnić w zależności od typu wykresu oraz używanej biblioteki lub narzędzia.
