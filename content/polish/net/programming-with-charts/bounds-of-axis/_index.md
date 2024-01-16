---
title: Granice osi na wykresie
linktitle: Granice osi na wykresie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić granice osi na wykresie za pomocą Aspose.Words dla .NET kontrolującego zakres wartości wyświetlanych na osi.
type: docs
weight: 10
url: /pl/net/programming-with-charts/bounds-of-axis/
---

W tym samouczku wyjaśniono, jak ustawić granice osi na wykresie za pomocą Aspose.Words dla .NET. Wstawiając wykres, dodając dane serii i konfigurując skalowanie osi, możesz zdefiniować minimalne i maksymalne wartości osi.

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Krok 4: Dodaj dane serii
Wyczyść wszystkie istniejące serie na wykresie i dodaj dane nowych serii. W tym przykładzie dodajemy serię z etykietami „Element 1” do „Element 5” i odpowiadającymi im wartościami.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Krok 5: Ustaw granice osi
 Skonfiguruj skalowanie osi Y, ustawiając wartości minimalne i maksymalne za pomocą`Scaling.Minimum` I`Scaling.Maximum` właściwości osi.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Krok 6: Zapisz dokument
 Zapisz dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithCharts.BoundsOfAxis.docx”.

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Przykładowy kod źródłowy Bounds Of Axis przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Otóż to! Pomyślnie ustawiłeś granice osi na wykresie za pomocą Aspose.Words dla .NET.

## Wniosek
W tym samouczku nauczyłeś się, jak ustawić granice osi na wykresie za pomocą Aspose.Words dla .NET. Postępując zgodnie z instrukcją krok po kroku, możesz wstawić i skonfigurować wykres, dodać dane serii oraz zdefiniować minimalne i maksymalne wartości skalowania osi. Aspose.Words dla .NET zapewnia potężny i elastyczny interfejs API do przetwarzania słów w dokumentach programu Word, umożliwiając łatwe tworzenie dynamicznych i atrakcyjnych wizualnie wykresów.


### Często zadawane pytania

#### Pytanie 1. Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to biblioteka, która umożliwia programistom programową pracę z dokumentami programu Word. Zapewnia szeroką gamę funkcji i funkcjonalności do tworzenia, manipulowania i zapisywania dokumentów Word.

#### Pytanie 2. Jak mogę zainstalować Aspose.Words dla .NET?
Aby zainstalować Aspose.Words dla .NET, możesz użyć menedżera pakietów NuGet w Visual Studio. Po prostu wyszukaj „Aspose.Words” w menedżerze pakietów NuGet i zainstaluj go w swoim projekcie.

#### Pytanie 3. Czy mogę używać Aspose.Words dla .NET z innymi językami programowania?
Nie, Aspose.Words dla .NET jest specjalnie zaprojektowany dla aplikacji .NET. Współpracuje z językami programowania, takimi jak C# i VB.NET.

#### Pytanie 4. Czy są jakieś inne wymagania wstępne dotyczące korzystania z Aspose.Words dla .NET?
Oprócz instalacji biblioteki Aspose.Words for .NET powinieneś posiadać podstawową wiedzę z zakresu programowania w C# i przetwarzania tekstu w dokumentach Word. Pomocna będzie także znajomość frameworku .NET.
