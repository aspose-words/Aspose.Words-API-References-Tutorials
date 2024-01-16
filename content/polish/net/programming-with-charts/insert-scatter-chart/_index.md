---
title: Wstaw wykres punktowy do dokumentu programu Word
linktitle: Wstaw wykres punktowy do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić wykres punktowy do dokumentu za pomocą Aspose.Words dla .NET. Dodaj dane serii ze współrzędnymi X i Y.
type: docs
weight: 10
url: /pl/net/programming-with-charts/insert-scatter-chart/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do wstawiania wykresu punktowego do dokumentu. Dostarczony kod źródłowy pokazuje, jak utworzyć wykres, dodać dane serii i zapisać dokument.

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

 Następnie użyj`InsertChart` metoda`DocumentBuilder` , aby wstawić wykres punktowy do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Dodaj dane serii do wykresu

Dodaj dane serii do wykresu. W tym przykładzie dodamy dwa zestawy współrzędnych X i Y.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Krok 4: Zapisz dokument

 Na koniec zapisz dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

To kończy implementację wstawiania wykresu punktowego przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Wstaw wykres punktowy przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Wniosek

W tym samouczku nauczyłeś się, jak wstawić wykres punktowy do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z instrukcją krok po kroku i wykorzystując dostarczony kod źródłowy, możesz utworzyć nowy dokument, wstawić wykres punktowy, dodać dane serii ze współrzędnymi X i Y oraz zapisać dokument z wykresem.

Aspose.Words dla .NET zapewnia kompleksowe API do przetwarzania słów z wykresami w dokumentach Word. Wykresy punktowe są przydatne do wizualizacji i analizowania danych za pomocą dwóch zmiennych numerycznych. Dzięki Aspose.Words dla .NET możesz łatwo tworzyć wykresy punktowe przedstawiające relacje między wartościami X i Y oraz identyfikować wzorce i trendy w danych.

Używając Aspose.Words dla .NET, możesz zautomatyzować proces generowania dokumentów za pomocą wykresów punktowych, oszczędzając czas i wysiłek przy ręcznym tworzeniu dokumentów. Biblioteka oferuje szeroką gamę typów wykresów, w tym wykresy punktowe, a także zapewnia różne opcje dostosowywania, aby dostosować wygląd wykresu do własnych potrzeb.

### Często zadawane pytania

#### Pytanie 1. Co to jest wykres punktowy?
Wykres punktowy to rodzaj wykresu przedstawiającego relację między dwiema zmiennymi liczbowymi. Składa się z szeregu punktów naniesionych na siatkę współrzędnych, przy czym jedna zmienna jest reprezentowana na osi X, a druga na osi Y. Wykresy punktowe służą do identyfikowania wzorców, korelacji lub trendów między dwoma zestawami punktów danych.

#### Pytanie 2. Czy mogę dodać wiele serii do wykresu punktowego?
Tak, możesz dodać wiele serii do wykresu punktowego za pomocą Aspose.Words dla .NET. Każda seria reprezentuje zestaw punktów danych z odpowiednimi współrzędnymi X i Y. Dodając wiele serii, możesz porównywać i analizować różne zbiory danych na tym samym wykresie punktowym, zapewniając kompleksowy wgląd w dane.

#### Pytanie 3. Czy mogę dostosować wygląd wykresu punktowego?
Tak, używając Aspose.Words dla .NET, możesz dostosować różne aspekty wyglądu wykresu punktowego. Można modyfikować właściwości, takie jak kolor serii, kształt znacznika, etykiety osi i formatowanie obszaru wykresu. Biblioteka udostępnia bogaty zestaw interfejsów API do kontrolowania elementów wizualnych wykresu i tworzenia niestandardowego wyglądu odpowiadającego Twoim potrzebom.

#### Pytanie 4. Czy mogę zapisać dokument z wstawionym wykresem punktowym w różnych formatach?
Tak, Aspose.Words dla .NET umożliwia zapisanie dokumentu z wstawionym wykresem punktowym w różnych formatach, takich jak DOCX, PDF, HTML i innych. Możesz wybrać żądany format wyjściowy w oparciu o swoje wymagania i użyć`Save` metoda`Document` obiekt, aby zapisać dokument. Wstawiony wykres punktowy zostanie zachowany w zapisanym dokumencie.

#### Pytanie 5. Czy mogę modyfikować dane i wygląd wykresu punktowego po jego wstawieniu?
Tak, po wstawieniu wykresu punktowego do dokumentu, możesz modyfikować jego dane i wygląd, korzystając z API udostępnianych przez Aspose.Words dla .NET. Możesz aktualizować dane serii o nowe współrzędne X i Y, zmieniać kształty i kolory znaczników, dostosowywać właściwości osi i stosować opcje formatowania, aby tworzyć dynamiczne i interaktywne wykresy w dokumentach programu Word.