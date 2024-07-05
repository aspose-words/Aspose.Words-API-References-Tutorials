---
title: Ustaw domyślne opcje etykiet danych na wykresie
linktitle: Ustaw domyślne opcje etykiet danych na wykresie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić domyślne opcje etykiet danych na wykresie za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-charts/default-options-for-data-labels/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do ustawiania domyślnych opcji etykiet danych na wykresie. Dostarczony kod demonstruje, jak utworzyć wykres, dodać serie danych i dostosować etykiety danych za pomocą Aspose.Words.

## Krok 1: Skonfiguruj projekt

Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania:

- Zainstalowana biblioteka Aspose.Words dla .NET. Możesz go pobrać za pomocą menedżera pakietów NuGet, aby go zainstalować.
- Ścieżka katalogu dokumentu, w którym zostanie zapisany dokument wyjściowy.

## Krok 2: Utwórz nowy dokument i wstaw wykres

 Najpierw utwórzmy nowy`Document` obiekt i a`DocumentBuilder` do zbudowania dokumentu.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Następnie wstawiamy wykres do dokumentu za pomocą`InsertChart` metoda`DocumentBuilder`. W tym przykładzie wstawimy wykres kołowy.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Dodaj serię danych do wykresu

Dodajmy teraz serię danych do wykresu. W tym przykładzie dodamy trzy kategorie i odpowiadające im wartości.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Krok 4: Dostosuj etykiety danych

 Aby dostosować etykiety danych na wykresie, musimy uzyskać dostęp do`ChartDataLabelCollection` obiekt kojarzony z serią.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Następnie możemy modyfikować różne właściwości pliku`labels`obiekt, aby ustawić żądane opcje etykiet danych. W tym przykładzie umożliwimy pokazywanie procentu i wartości, wyłączymy linie odniesienia i ustawimy niestandardowy separator.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Krok 5: Zapisz dokument

 Na koniec zapisujemy dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

To kończy implementację ustawiania domyślnych opcji etykiet danych na wykresie przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy domyślnych opcji etykiet danych przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## Wniosek

W tym samouczku nauczyłeś się ustawiać domyślne opcje etykiet danych na wykresie za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem, możesz utworzyć wykres, dodać serie danych i dostosować etykiety danych do swoich konkretnych wymagań. Aspose.Words dla .NET zapewnia potężny interfejs API do przetwarzania słów z wykresami w dokumentach programu Word, umożliwiając manipulowanie różnymi elementami wykresów i osiąganie pożądanego wyglądu i funkcjonalności.

 Ustawiając właściwości pliku`ChartDataLabelCollection`obiekt powiązany z serią wykresów, możesz kontrolować wyświetlanie etykiet danych, w tym opcje takie jak pokazywanie wartości procentowych, wartości, linii odniesienia i niestandardowych separatorów. Ta elastyczność umożliwia efektywną prezentację danych i poprawę wizualnej reprezentacji wykresów.

### Często zadawane pytania

#### Pytanie 1. Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to biblioteka, która umożliwia programistom programowe tworzenie, manipulowanie i zapisywanie dokumentów programu Word przy użyciu aplikacji .NET. Zapewnia szeroką gamę funkcji do przetwarzania tekstu z elementami dokumentu, w tym wykresami.

#### Pytanie 2. Jak mogę zainstalować Aspose.Words dla .NET?
Możesz zainstalować Aspose.Words dla .NET, pobierając go za pomocą menedżera pakietów NuGet w programie Visual Studio. Po prostu wyszukaj „Aspose.Words” w menedżerze pakietów NuGet i zainstaluj go w swoim projekcie.

#### Pytanie 3. Czy mogę dostosować inne aspekty wykresu za pomocą Aspose.Words dla .NET?
Tak, Aspose.Words dla .NET umożliwia dostosowanie różnych aspektów wykresu, takich jak typ wykresu, etykiety osi, legenda, obszar wykresu i inne. Można uzyskać dostęp do różnych właściwości obiektu wykresu i je modyfikować, aby uzyskać pożądany wygląd i zachowanie.

#### Pytanie 4. Czy mogę zapisać wykres w różnych formatach?
 Tak, Aspose.Words dla .NET obsługuje zapisywanie dokumentu zawierającego wykres w różnych formatach, w tym DOCX, PDF, HTML i innych. Możesz wybrać odpowiedni format w oparciu o swoje wymagania i użyć`Save` metoda`Document` obiekt, aby zapisać dokument.

#### Pytanie 5. Czy mogę zastosować te techniki do innych typów wykresów?
Tak, techniki opisane w tym samouczku można zastosować do innych typów wykresów obsługiwanych przez Aspose.Words dla .NET. Kluczem jest dostęp do odpowiednich obiektów i właściwości specyficznych dla typu wykresu, z którym korzystasz z programu Words Processing.