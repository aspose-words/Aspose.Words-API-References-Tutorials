---
title: Zaznacz opcję Wyrównanie etykiet wieloliniowych na wykresie
linktitle: Zaznacz opcję Wyrównanie etykiet wieloliniowych na wykresie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wyrównywać wieloliniowe etykiety znaczników na osi wykresu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-charts/tick-multi-line-label-alignment/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do ustawiania wyrównania wieloliniowych etykiet znaczników na osi wykresu. Dostarczony kod źródłowy pokazuje, jak utworzyć wykres, uzyskać dostęp do osi i zmodyfikować wyrównanie etykiety znacznika.

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
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Krok 3: Ustaw wyrównanie etykiety znacznika

 Aby ustawić wyrównanie wieloliniowych etykiet znaczników, przejdź do opcji`AxisX` właściwość wykresu i ustaw`TickLabelAlignment` właściwość do żądanego wyrównania. W tym przykładzie ustawiliśmy wyrównanie na`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Krok 4: Zapisz dokument

 Na koniec zapisz dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

To kończy implementację ustawiania wyrównania wielowierszowych etykiet przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla wyrównania etykiet wieloliniowych zaznaczonych przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Ta właściwość ma wpływ tylko na etykiety wielowierszowe.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Wniosek

W tym samouczku nauczyłeś się, jak ustawić wyrównanie wieloliniowych etykiet znaczników na osi wykresu za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz utworzyć nowy dokument, wstawić wykres punktowy, uzyskać dostęp do osi wykresu i zmodyfikować wyrównanie znaczników.

Aspose.Words dla .NET zapewnia zaawansowane funkcje do manipulowania wykresami w dokumentach Word. Etykiety wielowierszowe zaznaczenia są przydatne, gdy etykiety osi zawierają długi tekst, który wymaga zawijania lub dzielenia na wiele wierszy. Ustawiając wyrównanie etykiet znaczników, możesz kontrolować poziome wyrównanie wieloliniowych etykiet na osi wykresu, zapewniając optymalną prezentację i czytelność.

Dostosowanie wyrównania wieloliniowych etykiet znaczników pozwala dostosować wygląd wykresu, szczególnie w przypadku długich lub złożonych etykiet. Wyrównując etykiety do prawej, lewej, do środka lub wyjustowane, można uzyskać zrównoważone i atrakcyjne wizualnie rozmieszczenie etykiet wzdłuż osi.

Dzięki Aspose.Words dla .NET możesz łatwo uzyskać dostęp i modyfikować właściwość wyrównania znaczników osi wykresu, zapewniając pełną kontrolę nad wyglądem i układem znaczników na wykresach dokumentów programu Word.

### Często zadawane pytania

#### Pytanie 1. Co to są wieloliniowe etykiety znaczników na osi wykresu?
Zaznaczenie etykiet wieloliniowych na osi wykresu odnosi się do etykiet osi rozciągających się na wiele linii, gdy tekst etykiety jest długi lub wymaga zawinięcia w celu zmieszczenia się w dostępnej przestrzeni. Zamiast obcinać tekst etykiety lub powodować bałagan wizualny, oś wykresu automatycznie dzieli etykiety na wiele linii, aby zapewnić czytelność. Etykiety wieloliniowe ze znacznikami są szczególnie przydatne w przypadku długich etykiet kategorii lub wartości na wykresach.

#### Pytanie 2. Czy mogę dostosować wyrównanie etykiet znaczników na osi wykresu?
 Tak, możesz dostosować wyrównanie etykiet znaczników na osi wykresu za pomocą Aspose.Words dla .NET. Uzyskując dostęp do`TickLabelAlignment` własność`ChartAxis` obiektu, możesz ustawić żądane wyrównanie etykiet znaczników. Opcje wyrównania obejmują wyrównanie do lewej, prawej, do środka lub wyrównane. Regulacja wyrównania pozwala kontrolować poziome położenie znaczników wzdłuż osi wykresu, zapewniając odpowiednią czytelność i prezentację wizualną.

#### Pytanie 3. Kiedy należy rozważyć zmianę wyrównania znaczników na osi wykresu?
Zmiana wyrównania znaczników na osi wykresu jest korzystna w przypadku długich lub wielowierszowych etykiet, które wymagają optymalnej prezentacji i czytelności. Dostosowując wyrównanie, możesz upewnić się, że etykiety są odpowiednio wyrównane i rozmieszczone w odpowiednich odstępach, unikając nakładania się lub obcinania. Rozważ zmianę wyrównania etykiet znaczników w przypadku wykresów z długimi nazwami kategorii, pełnymi etykietami wartości lub w innych sytuacjach, w których domyślne wyrównanie nie zapewnia pożądanego wyglądu.

#### Pytanie 4. Czy wyrównanie etykiet znaczników wpływa na etykiety jednowierszowe na osi wykresu?
Nie, właściwość wyrównania etykiet znaczników nie wpływa na etykiety jednowierszowe na osi wykresu. Jest specjalnie zaprojektowany do etykiet wielowierszowych, które wymagają zawijania lub dzielenia. Etykiety jednowierszowe są wyrównywane w oparciu o domyślne ustawienia wyrównania osi wykresu. Właściwość wyrównania etykiety zaznaczenia ma zastosowanie tylko do etykiet rozciągających się na wiele linii, umożliwiając kontrolowanie wyrównania każdej linii w etykiecie wielowierszowej.

#### Pytanie 5. Czy mogę inaczej wyrównać etykiety znaczników dla osi X i osi Y na wykresie?
 Tak, możesz inaczej wyrównywać etykiety znaczników dla osi X i osi Y na wykresie, używając Aspose.Words dla .NET. Właściwość wyrównania znaczników jest specyficzna dla każdej osi wykresu. Uzyskując dostęp do odpowiedniego`ChartAxis` obiektu dla osi X lub Y, możesz niezależnie ustawić wyrównanie etykiety znacznika na różne wartości. Zapewnia to elastyczność w różnicowaniu etykiet znaczników w zależności od konkretnych wymagań dla każdej osi na wykresie.