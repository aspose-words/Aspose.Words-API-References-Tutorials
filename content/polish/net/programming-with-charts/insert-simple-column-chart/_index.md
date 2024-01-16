---
title: Wstaw prosty wykres kolumnowy w dokumencie programu Word
linktitle: Wstaw prosty wykres kolumnowy w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić prosty wykres kolumnowy do dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-charts/insert-simple-column-chart/
---

tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do wstawiania prostego wykresu kolumnowego do dokumentu. Dostarczony kod źródłowy pokazuje, jak utworzyć wykres, dodać dane serii i zapisać dokument.

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

 Następnie użyj`InsertChart` metoda`DocumentBuilder` , aby wstawić wykres kolumnowy do dokumentu. Możesz określić różne typy i rozmiary wykresów zgodnie ze swoimi wymaganiami.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Dodaj dane serii do wykresu

Dodaj dane serii do wykresu. W tym przykładzie dodamy wiele serii po dwie kategorie każda.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Krok 4: Zapisz dokument

 Na koniec zapisz dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

To kończy implementację wstawiania prostego wykresu kolumnowego przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla opcji Wstaw prosty wykres kolumnowy przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Można określić różne typy i rozmiary wykresów.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Usuń domyślnie wygenerowaną serię.
	seriesColl.Clear();
	// Utwórz tablicę nazw kategorii. W tym samouczku mamy dwie kategorie.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Należy pamiętać, że tablice danych nie mogą być puste, a tablice muszą mieć ten sam rozmiar.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Wniosek

tym samouczku nauczyłeś się, jak wstawić prosty wykres kolumnowy do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z instrukcją krok po kroku i korzystając z dostarczonego kodu źródłowego, możesz utworzyć nowy dokument, wstawić wykres kolumnowy, dodać wiele serii z kategoriami i odpowiadającymi im wartościami oraz zapisać dokument z wykresem.

Aspose.Words dla .NET zapewnia potężny i elastyczny interfejs API do przetwarzania słów z wykresami w dokumentach programu Word. Prosty wykres kolumnowy to skuteczny sposób przedstawiania i porównywania danych w różnych kategoriach. Dzięki Aspose.Words dla .NET możesz łatwo tworzyć wykresy kolumnowe z niestandardowymi danymi, dodawać wiele serii w celu wizualnego porównania i dostosowywać wygląd wykresu zgodnie z własnymi wymaganiami.

Używając Aspose.Words dla .NET, możesz zautomatyzować proces generowania dokumentów z wykresami kolumnowymi, oszczędzając czas i wysiłek przy ręcznym tworzeniu dokumentów. Biblioteka oferuje szeroką gamę typów wykresów, w tym proste wykresy kolumnowe, a także zapewnia różne opcje dostosowywania, aby dostosować wygląd wykresu do własnych potrzeb.

### Często zadawane pytania

#### Pytanie 1. Co to jest wykres kolumnowy?
Wykres kolumnowy to typ wykresu, na którym dane są wyświetlane za pomocą pionowych słupków o różnej wysokości. Każda kolumna reprezentuje kategorię, a wysokość kolumny odpowiada wartości tej kategorii. Wykresy kolumnowe są powszechnie używane do porównywania danych w różnych kategoriach lub śledzenia zmian w czasie.

#### Pytanie 2. Czy mogę dodać wiele serii do wykresu kolumnowego?
Tak, używając Aspose.Words dla .NET, możesz dodać wiele serii do wykresu kolumnowego. Każda seria reprezentuje zestaw punktów danych z odpowiednimi kategoriami i wartościami. Dodając wiele serii, możesz porównywać i analizować różne zbiory danych na tym samym wykresie kolumnowym, zapewniając kompleksowy wgląd w dane.

#### Pytanie 3. Czy mogę dostosować wygląd wykresu kolumnowego?
Tak, Aspose.Words dla .NET pozwala dostosować różne aspekty wyglądu wykresu kolumnowego. Można modyfikować właściwości, takie jak kolor serii, etykiety osi, etykiety danych i formatowanie obszaru wykresu. Biblioteka udostępnia bogaty zestaw interfejsów API do kontrolowania elementów wizualnych wykresu i tworzenia niestandardowego wyglądu odpowiadającego Twoim potrzebom.

#### Pytanie 4. Czy mogę zapisać dokument z wstawionym wykresem kolumnowym w różnych formatach?
 Tak, Aspose.Words dla .NET umożliwia zapisanie dokumentu z wstawionym wykresem kolumnowym w różnych formatach, takich jak DOCX, PDF, HTML i innych. Możesz wybrać żądany format wyjściowy w oparciu o swoje wymagania i użyć`Save` metoda`Document` obiekt, aby zapisać dokument. Wstawiony wykres kolumnowy zostanie zachowany w zapisanym dokumencie.

#### Pytanie 5. Czy mogę modyfikować dane i wygląd wykresu kolumnowego po jego wstawieniu?
Tak, po wstawieniu wykresu kolumnowego do dokumentu, możesz modyfikować jego dane i wygląd, korzystając z API udostępnianych przez Aspose.Words dla .NET. Możesz aktualizować dane serii o nowe kategorie i wartości, zmieniać kolory i formatowanie kolumn, dostosowywać właściwości osi i stosować różne opcje formatowania, aby tworzyć dynamiczne i atrakcyjne wizualnie wykresy w dokumentach programu Word.