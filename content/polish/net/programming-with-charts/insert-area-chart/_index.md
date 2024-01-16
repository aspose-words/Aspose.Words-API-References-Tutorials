---
title: Wstaw wykres warstwowy do dokumentu programu Word
linktitle: Wstaw wykres warstwowy do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić wykres warstwowy do dokumentu za pomocą Aspose.Words dla .NET. Dodaj dane serii i zapisz dokument z wykresem.
type: docs
weight: 10
url: /pl/net/programming-with-charts/insert-area-chart/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do wstawiania wykresu warstwowego do dokumentu. Dostarczony kod źródłowy pokazuje, jak utworzyć wykres, dodać dane serii i zapisać dokument.

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

 Następnie użyj`InsertChart` metoda`DocumentBuilder` , aby wstawić wykres warstwowy do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Dodaj dane serii do wykresu

Dodaj dane serii do wykresu. W tym przykładzie dodamy pięć punktów danych z odpowiadającymi im datami i wartościami.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## Krok 4: Zapisz dokument

 Na koniec zapisz dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

To kończy implementację wstawiania wykresu warstwowego za pomocą Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Wstaw wykres obszarowy przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Wniosek

W tym samouczku nauczyłeś się, jak wstawić wykres warstwowy do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z instrukcją krok po kroku i korzystając z dostarczonego kodu źródłowego, możesz utworzyć nowy dokument, wstawić wykres warstwowy, dodać dane serii i zapisać dokument z wykresem.

Aspose.Words dla .NET zapewnia potężny interfejs API do przetwarzania słów z wykresami w dokumentach Word. Za pomocą zaledwie kilku linijek kodu możesz utworzyć profesjonalnie wyglądające wykresy warstwowe i dostosować je do swoich wymagań. Wykresy warstwowe są powszechnie używane do wyświetlania wielkości i trendów danych w czasie lub w kategoriach.

Używając Aspose.Words dla .NET, możesz zautomatyzować proces generowania dokumentów z wykresami warstwowymi, oszczędzając czas i wysiłek przy ręcznym tworzeniu dokumentów. Biblioteka oferuje szeroką gamę typów wykresów i opcji dostosowywania, umożliwiając tworzenie atrakcyjnych wizualnie i informacyjnych wykresów w dokumentach programu Word.

### Często zadawane pytania

#### Pytanie 1. Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka do przetwarzania dokumentów, która umożliwia programistom programowe tworzenie, modyfikowanie i konwertowanie dokumentów programu Word w aplikacjach .NET. Zapewnia kompleksowy zestaw interfejsów API do przetwarzania tekstu z elementami dokumentu, w tym wykresami, akapitami, tabelami i nie tylko.

#### Pytanie 2. Jak zainstalować Aspose.Words dla .NET?
Aby zainstalować Aspose.Words dla .NET, możesz użyć menedżera pakietów NuGet w Visual Studio, aby zainstalować bibliotekę bezpośrednio w projekcie. Po prostu wyszukaj „Aspose.Words” w menedżerze pakietów NuGet i zainstaluj pakiet.

#### Pytanie 3. Czy mogę dostosować wygląd wykresu warstwowego?
Tak, używając Aspose.Words dla .NET, możesz dostosować różne aspekty wyglądu wykresu warstwowego. Można modyfikować właściwości, takie jak tytuł wykresu, kolor serii, etykiety osi i formatowanie obszaru wykresu. Biblioteka udostępnia bogaty zestaw interfejsów API do kontrolowania elementów wizualnych wykresu i tworzenia niestandardowego wyglądu odpowiadającego Twoim potrzebom.

#### Pytanie 4. Czy mogę dodać wiele serii do wykresu warstwowego?
Tak, możesz dodać wiele serii do wykresu warstwowego za pomocą Aspose.Words dla .NET. Każda seria reprezentuje zestaw punktów danych naniesionych na wykres. Możesz dodawać serie z różnymi zestawami danych i dostosowywać każdą serię indywidualnie, włączając jej nazwę, punkty danych i wygląd.

#### Pytanie 5. Czy mogę zapisać dokument z wstawionym wykresem warstwowym w różnych formatach?
 Tak, Aspose.Words dla .NET umożliwia zapisanie dokumentu z wstawionym wykresem warstwowym w różnych formatach, takich jak DOCX, PDF, HTML i innych. Możesz wybrać żądany format wyjściowy w oparciu o swoje wymagania i użyć`Save` metoda`Document` obiekt, aby zapisać dokument. Wstawiony wykres warstwowy zostanie zachowany w zapisanym dokumencie.

#### Pytanie 6. Czy mogę modyfikować dane i wygląd wykresu warstwowego po jego wstawieniu?
Tak, po wstawieniu wykresu warstwowego do dokumentu możesz modyfikować jego dane i wygląd, korzystając z interfejsów API udostępnianych przez Aspose.Words dla .NET. Możesz aktualizować dane serii, zmieniać typ wykresu, dostosowywać właściwości osi i stosować opcje formatowania, aby tworzyć dynamiczne i interaktywne wykresy w dokumentach programu Word.