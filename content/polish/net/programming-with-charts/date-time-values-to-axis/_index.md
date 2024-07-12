---
title: Dodaj wartości daty i godziny do osi wykresu
linktitle: Dodaj wartości daty i godziny do osi wykresu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodać wartości daty i godziny do osi wykresu za pomocą Aspose.Words dla .NET w tym kompleksowym przewodniku krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-charts/date-time-values-to-axis/
---
## Wstęp

Tworzenie wykresów w dokumentach może być skutecznym sposobem wizualizacji danych. W przypadku danych szeregów czasowych dodanie wartości daty i godziny na osi wykresu ma kluczowe znaczenie dla przejrzystości. W tym samouczku przeprowadzimy Cię przez proces dodawania wartości daty i godziny do osi wykresu za pomocą Aspose.Words dla .NET. Ten przewodnik krok po kroku pomoże Ci skonfigurować środowisko, napisać kod i zrozumieć każdą część procesu. Zanurzmy się!

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:

1. Visual Studio lub dowolne środowisko .NET IDE: Do pisania i uruchamiania kodu .NET potrzebne jest środowisko programistyczne.
2.  Aspose.Words dla .NET: Powinieneś mieć zainstalowaną bibliotekę Aspose.Words dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/words/net/).
3. Podstawowa znajomość języka C#: W tym samouczku założono, że masz podstawową wiedzę na temat programowania w języku C#.
4.  Ważna licencja Aspose: Możesz uzyskać tymczasową licencję od[Tutaj](https://purchase.aspose.com/temporary-license/).

## Importuj przestrzenie nazw

Na początek upewnij się, że w projekcie zaimportowano niezbędne przestrzenie nazw. Ten krok jest kluczowy dla uzyskania dostępu do klas i metod Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Krok 1: Skonfiguruj katalog dokumentów

Najpierw musisz zdefiniować katalog, w którym zostanie zapisany dokument. Jest to ważne dla uporządkowania plików i zapewnienia prawidłowego działania kodu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz nowy dokument i narzędzie DocumentBuider

 Następnie utwórz nową instancję pliku`Document` klasa i A`DocumentBuilder` obiekt. Obiekty te pomogą Ci w tworzeniu dokumentu i manipulowaniu nim.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstaw wykres do dokumentu

 Teraz wstaw wykres do swojego dokumentu za pomocą`DocumentBuilder` obiekt. W tym przykładzie używamy wykresu kolumnowego, ale możesz wybrać także inne typy.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Krok 4: Wyczyść istniejącą serię

Wyczyść wszystkie istniejące serie na wykresie, aby mieć pewność, że zaczynasz od czystej karty. Ten krok jest niezbędny w przypadku danych niestandardowych.

```csharp
chart.Series.Clear();
```

## Krok 5: Dodaj wartości daty i godziny do serii

Dodaj wartości daty i godziny do serii wykresów. Ten krok polega na utworzeniu tablic dla dat i odpowiadających im wartości.

```csharp
chart.Series.Add("Aspose Series 1",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Krok 6: Skonfiguruj oś X

Ustaw skalowanie i znaczniki dla osi X. Dzięki temu daty będą wyświetlane prawidłowo i w odpowiednich odstępach czasu.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Krok 7: Zapisz dokument

Na koniec zapisz dokument we wskazanym katalogu. Ten krok kończy proces, a Twój dokument powinien teraz zawierać wykres z wartościami daty i godziny na osi X.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

## Wniosek

Dodawanie wartości daty i godziny do osi wykresu w dokumencie jest prostym procesem dzięki Aspose.Words dla .NET. Wykonując kroki opisane w tym samouczku, możesz utworzyć przejrzyste i pouczające wykresy, które skutecznie wizualizują dane szeregów czasowych. Niezależnie od tego, czy przygotowujesz raporty, prezentacje, czy jakikolwiek dokument wymagający szczegółowej reprezentacji danych, Aspose.Words zapewnia narzędzia potrzebne do osiągnięcia sukcesu.

## Często zadawane pytania

### Czy mogę używać innych typów wykresów w Aspose.Words dla .NET?

Tak, Aspose.Words obsługuje różne typy wykresów, w tym liniowe, słupkowe, kołowe i inne.

### Jak mogę dostosować wygląd mojego wykresu?

Możesz dostosować wygląd, uzyskując dostęp do właściwości wykresu i ustawiając style, kolory i nie tylko.

### Czy można dodać wiele serii do wykresu?

 Absolutnie! Możesz dodać wiele serii do swojego wykresu, wywołując metodę`Series.Add` metodę wielokrotnie z różnymi danymi.

### Co się stanie, jeśli będę musiał dynamicznie aktualizować dane wykresu?

Możesz dynamicznie aktualizować dane wykresu, programowo manipulując właściwościami serii i osi w oparciu o swoje wymagania.

### Gdzie mogę znaleźć bardziej szczegółową dokumentację Aspose.Words dla .NET?

 Bardziej szczegółową dokumentację można znaleźć[Tutaj](https://reference.aspose.com/words/net/).