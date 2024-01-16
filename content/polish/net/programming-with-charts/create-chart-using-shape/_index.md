---
title: Utwórz i dostosuj wykres za pomocą kształtu
linktitle: Utwórz i dostosuj wykres za pomocą kształtu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak tworzyć i dostosowywać wykres przy użyciu kształtu w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-charts/create-chart-using-shape/
---

W tym samouczku wyjaśniono, jak utworzyć wykres przy użyciu kształtu w dokumencie programu Word przy użyciu Aspose.Words dla .NET.

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
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Krok 4: Dostosuj wykres
Dostosuj wykres, modyfikując różne właściwości, takie jak tytuł wykresu i legenda.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Krok 5: Zapisz dokument
 Zapisz dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithCharts.CreateChartUsingShape.docx”.

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Przykładowy kod źródłowy narzędzia Utwórz wykres przy użyciu kształtu przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Należy pamiętać, że jeśli jako tekst tytułu zostanie określona wartość null lub pusta, wyświetlony zostanie tytuł wygenerowany automatycznie.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Otóż to! Pomyślnie utworzyłeś wykres przy użyciu kształtu w dokumencie programu Word przy użyciu Aspose.Words dla .NET.

## Wniosek
tym samouczku nauczyłeś się tworzyć wykres przy użyciu kształtu w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem, możesz wstawić i skonfigurować kształt wykresu, dostosować jego wygląd i zapisać dokument. Aspose.Words dla .NET zapewnia kompleksowy zestaw funkcji do przetwarzania słów z dokumentami i wykresami programu Word, umożliwiając tworzenie profesjonalnie wyglądających i atrakcyjnych wizualnie wykresów bezpośrednio w aplikacjach .NET.

### Często zadawane pytania

#### Pytanie 1. Czy mogę tworzyć wykresy w dokumencie programu Word przy użyciu Aspose.Words dla .NET?
Tak, dzięki Aspose.Words dla .NET możesz programowo tworzyć wykresy w dokumencie Word. Aspose.Words zapewnia interfejsy API i funkcje umożliwiające wstawianie różnych typów wykresów, dostosowywanie ich wyglądu i manipulowanie danymi wykresów.

#### Pytanie 2. Jakie typy wykresów są obsługiwane przez Aspose.Words dla .NET?
Aspose.Words dla .NET obsługuje szeroką gamę typów wykresów, w tym wykresy liniowe, wykresy słupkowe, wykresy kołowe, wykresy warstwowe, wykresy punktowe i inne. Możesz wybrać odpowiedni typ wykresu w oparciu o wymagania dotyczące danych i wizualizacji.

#### Pytanie 3. Czy mogę dostosować wygląd tworzonego wykresu?
Tak, możesz dostosować wygląd utworzonego wykresu za pomocą Aspose.Words dla .NET. Możesz modyfikować właściwości, takie jak tytuł wykresu, pozycja legendy, etykiety danych, etykiety osi, kolory i inne elementy wizualne, aby spełnić Twoje specyficzne potrzeby związane z projektem i formatowaniem.
