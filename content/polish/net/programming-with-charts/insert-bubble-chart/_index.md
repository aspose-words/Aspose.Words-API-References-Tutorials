---
title: Wstaw wykres bąbelkowy do dokumentu programu Word
linktitle: Wstaw wykres bąbelkowy do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić wykres bąbelkowy do dokumentu za pomocą Aspose.Words dla .NET. Dodaj dane serii z wartościami X, Y i rozmiarem bąbelka.
type: docs
weight: 10
url: /pl/net/programming-with-charts/insert-bubble-chart/
---

tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do wstawiania wykresu bąbelkowego do dokumentu. Dostarczony kod źródłowy pokazuje, jak utworzyć wykres, dodać dane serii i zapisać dokument.

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

 Następnie użyj`InsertChart` metoda`DocumentBuilder` , aby wstawić wykres bąbelkowy do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Dodaj dane serii do wykresu

Dodaj dane serii do wykresu. W tym przykładzie dodamy trzy punkty danych z odpowiadającymi im wartościami X, Y i rozmiarem bąbelka.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## Krok 4: Zapisz dokument

 Na koniec zapisz dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

To kończy implementację wstawiania wykresu bąbelkowego za pomocą Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Wstaw wykres bąbelkowy przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## Wniosek

W tym samouczku nauczyłeś się, jak wstawić wykres bąbelkowy do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z instrukcją krok po kroku i korzystając z dostarczonego kodu źródłowego, możesz utworzyć nowy dokument, wstawić wykres bąbelkowy, dodać dane serii i zapisać dokument z wykresem.

Aspose.Words dla .NET zapewnia potężny interfejs API do przetwarzania słów z wykresami w dokumentach Word. Wykresy bąbelkowe idealnie nadają się do wizualizacji danych trójwymiarowych, gdzie każdy punkt danych jest reprezentowany przez bąbelek ze współrzędnymi X i Y oraz wartością rozmiaru. Dzięki Aspose.Words dla .NET możesz tworzyć dynamiczne i pouczające wykresy bąbelkowe, które poprawiają wizualną reprezentację Twoich danych.

Używając Aspose.Words dla .NET, możesz zautomatyzować proces generowania dokumentów za pomocą wykresów bąbelkowych, oszczędzając czas i wysiłek przy ręcznym tworzeniu dokumentów. Biblioteka oferuje szeroką gamę typów wykresów i opcji dostosowywania, umożliwiając tworzenie atrakcyjnych wizualnie i bogatych w dane wykresów w dokumentach programu Word.

### Często zadawane pytania

#### Pytanie 1. Co to jest wykres bąbelkowy?
Wykres bąbelkowy to rodzaj wykresu, który wyświetla dane trójwymiarowe za pomocą bąbelków lub kul. Każdy punkt danych jest reprezentowany przez bąbelek, gdzie współrzędne X i Y określają położenie bąbelka na wykresie, a rozmiar bąbelka reprezentuje trzeci wymiar danych. Wykresy bąbelkowe są przydatne do wizualizacji relacji i wzorców między wieloma zmiennymi.

#### Pytanie 2. Czy mogę dodać wiele serii do wykresu bąbelkowego?
Tak, możesz dodać wiele serii do wykresu bąbelkowego za pomocą Aspose.Words dla .NET. Każda seria reprezentuje zestaw punktów danych z odpowiednimi wartościami X, Y i rozmiarem bąbelków. Dodając wiele serii, możesz porównywać i analizować różne zbiory danych na tym samym wykresie, zapewniając kompleksowy wgląd w dane.

#### Pytanie 3. Czy mogę dostosować wygląd wykresu bąbelkowego?
Tak, używając Aspose.Words dla .NET, możesz dostosować różne aspekty wyglądu wykresu bąbelkowego. Można modyfikować właściwości, takie jak kolor serii, rozmiar bąbelka, etykiety osi i formatowanie obszaru wykresu. Biblioteka udostępnia bogaty zestaw interfejsów API do kontrolowania elementów wizualnych wykresu i tworzenia niestandardowego wyglądu odpowiadającego Twoim potrzebom.

#### Pytanie 4. Czy mogę zapisać dokument z wstawionym wykresem bąbelkowym w różnych formatach?
 Tak, Aspose.Words dla .NET umożliwia zapisanie dokumentu z wstawionym wykresem bąbelkowym w różnych formatach, takich jak DOCX, PDF, HTML i innych. Możesz wybrać żądany format wyjściowy w oparciu o swoje wymagania i użyć`Save` metoda`Document` obiekt, aby zapisać dokument. Wstawiony wykres bąbelkowy zostanie zachowany w zapisanym dokumencie.

#### Pytanie 5. Czy mogę modyfikować dane i wygląd wykresu bąbelkowego po jego wstawieniu?
Tak, po wstawieniu wykresu bąbelkowego do dokumentu możesz modyfikować jego dane i wygląd korzystając z API udostępnionych przez Aspose.Words dla .NET. Możesz aktualizować dane serii, zmieniać rozmiar bąbelków, dostosowywać właściwości osi i stosować opcje formatowania, aby tworzyć dynamiczne i interaktywne wykresy w dokumentach programu Word.