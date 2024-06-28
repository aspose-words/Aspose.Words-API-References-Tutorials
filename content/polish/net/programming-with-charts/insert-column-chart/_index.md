---
title: Wstaw wykres kolumnowy do dokumentu programu Word
linktitle: Wstaw wykres kolumnowy do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić wykres kolumnowy do dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-charts/insert-column-chart/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do wstawiania wykresu kolumnowego do dokumentu. Dostarczony kod źródłowy pokazuje, jak utworzyć wykres, dodać dane serii i zapisać dokument.

## Krok 1: Skonfiguruj projekt

Upewnij się, że masz następujące wymagania wstępne:

- Zainstalowana biblioteka Aspose.Words dla .NET. Można go pobrać, używając menedżera pakietów NuGet do zainstalowania.
- Ścieżka katalogu dokumentu, w którym zostanie zapisany dokument wyjściowy.

## Krok 2: Utwórz nowy dokument i wstaw wykres.

 Stwórz nowy`Document` obiekt i a`DocumentBuilder` do zbudowania dokumentu.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Następnie użyj`InsertChart` metoda`DocumentBuilder` , aby wstawić wykres kolumnowy do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Dodaj dane serii do wykresu

Dodaj dane serii do wykresu. W tym przykładzie dodamy dwie kategorie i odpowiadające im wartości.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## Krok 4: Zapisz dokument

 Na koniec zapisz dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

To kończy implementację wstawiania wykresu kolumnowego przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Wstaw wykres kolumnowy przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## Wniosek

tym samouczku nauczyłeś się, jak wstawić wykres kolumnowy do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z instrukcją krok po kroku i korzystając z udostępnionego kodu źródłowego, możesz utworzyć nowy dokument, wstawić wykres kolumnowy, dodać dane serii i zapisać dokument z wykresem.

Aspose.Words dla .NET zapewnia potężny interfejs API do przetwarzania słów z wykresami w dokumentach Word. Wykresy kolumnowe są powszechnie używane do wyświetlania i porównywania danych w różnych kategoriach lub grupach. Dzięki Aspose.Words dla .NET możesz łatwo tworzyć wykresy kolumnowe, które skutecznie wizualizują Twoje dane i dostarczają cennych spostrzeżeń.

Używając Aspose.Words dla .NET, możesz zautomatyzować proces generowania dokumentów z wykresami kolumnowymi, oszczędzając czas i wysiłek przy ręcznym tworzeniu dokumentów. Biblioteka oferuje szeroką gamę typów wykresów i opcji dostosowywania, umożliwiając tworzenie atrakcyjnych wizualnie i bogatych w dane wykresów w dokumentach programu Word.

### Często zadawane pytania

#### Pytanie 1. Co to jest wykres kolumnowy?
Wykres kolumnowy to typ wykresu przedstawiający dane w postaci pionowych słupków lub kolumn. Każda kolumna zazwyczaj reprezentuje kategorię lub grupę, a wysokość lub długość kolumny wskazuje wartość danych skojarzonych z tą kategorią. Wykresy kolumnowe są powszechnie używane do porównywania danych w różnych kategoriach lub śledzenia zmian w czasie.

#### Pytanie 2. Czy mogę dodać wiele serii do wykresu kolumnowego?
Tak, możesz dodać wiele serii do wykresu kolumnowego za pomocą Aspose.Words dla .NET. Każda seria reprezentuje zestaw punktów danych z odpowiednimi kategoriami i wartościami. Dodając wiele serii, możesz porównywać i analizować różne zbiory danych na tym samym wykresie, zapewniając kompleksowy wgląd w dane.

#### Pytanie 3. Czy mogę dostosować wygląd wykresu kolumnowego?
Tak, używając Aspose.Words dla .NET, możesz dostosować różne aspekty wyglądu wykresu kolumnowego. Można modyfikować właściwości, takie jak kolor serii, etykiety osi, szerokość kolumny i formatowanie obszaru wykresu. Biblioteka udostępnia bogaty zestaw interfejsów API do kontrolowania elementów wizualnych wykresu i tworzenia niestandardowego wyglądu odpowiadającego Twoim potrzebom.

#### Pytanie 4. Czy mogę zapisać dokument z wstawionym wykresem kolumnowym w różnych formatach?
 Tak, Aspose.Words dla .NET umożliwia zapisanie dokumentu z wstawionym wykresem kolumnowym w różnych formatach, takich jak DOCX, PDF, HTML i innych. Możesz wybrać żądany format wyjściowy w oparciu o swoje wymagania i użyć`Save` metoda`Document` obiekt, aby zapisać dokument. Wstawiony wykres kolumnowy zostanie zachowany w zapisanym dokumencie.

#### Pytanie 5. Czy mogę modyfikować dane i wygląd wykresu kolumnowego po jego wstawieniu?
Tak, po wstawieniu wykresu kolumnowego do dokumentu, możesz modyfikować jego dane i wygląd, korzystając z API udostępnianych przez Aspose.Words dla .NET. Możesz aktualizować dane serii, zmieniać kolory kolumn, dostosowywać właściwości osi i stosować opcje formatowania, aby tworzyć dynamiczne i interaktywne wykresy w dokumentach programu Word.