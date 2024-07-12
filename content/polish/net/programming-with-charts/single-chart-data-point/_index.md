---
title: Dostosuj pojedynczy punkt danych na wykresie
linktitle: Dostosuj pojedynczy punkt danych na wykresie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dostosować pojedyncze punkty danych na wykresie za pomocą Aspose.Words dla .NET w szczegółowym przewodniku krok po kroku. Ulepsz swoje wykresy dzięki unikalnym znacznikom i rozmiarom.
type: docs
weight: 10
url: /pl/net/programming-with-charts/single-chart-data-point/
---
## Wstęp

Czy zastanawiałeś się kiedyś, jak sprawić, by Twoje wykresy wyróżniały się unikalnymi punktami danych? Cóż, dzisiaj jest twój szczęśliwy dzień! Zagłębiamy się w dostosowywanie pojedynczego punktu danych na wykresie za pomocą Aspose.Words dla .NET. Zapnij pasy i skorzystaj z samouczka krok po kroku, który jest nie tylko pouczający, ale także zabawny i łatwy do zrozumienia.

## Warunki wstępne

Zanim zaczniemy, upewnijmy się, że masz wszystkie niezbędne elementy:

-  Aspose.Words dla biblioteki .NET: Upewnij się, że masz najnowszą wersję.[Pobierz to tutaj](https://releases.aspose.com/words/net/).
- .NET Framework: Upewnij się, że na komputerze jest zainstalowana platforma .NET Framework.
- Podstawowa znajomość języka C#: Pomocna będzie podstawowa znajomość programowania w języku C#.
- Zintegrowane środowisko programistyczne (IDE): zalecany jest program Visual Studio.

## Importuj przestrzenie nazw

Na początek zaimportujmy niezbędne przestrzenie nazw, aby ruszyć z piłką:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Krok 1: Zainicjuj dokument i narzędzie DocumentBuider

W porządku, zacznijmy od zainicjowania nowego dokumentu i narzędzia DocumentBuilder. To będzie płótno dla naszego wykresu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tutaj,`dataDir` to ścieżka katalogu, w którym zapiszesz swój dokument. The`DocumentBuilder` klasa pomaga w konstruowaniu dokumentu.

## Krok 2: Wstaw wykres

Następnie wstawmy do dokumentu wykres liniowy. To będzie nasz plac zabaw do dostosowywania punktów danych.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

 The`InsertChart` Metoda przyjmuje jako parametry typ, szerokość i wysokość wykresu. W tym przypadku wstawiamy wykres liniowy o szerokości 432 i wysokości 252.

## Krok 3: Uzyskaj dostęp do serii wykresów

Teraz nadszedł czas, aby uzyskać dostęp do serii na naszym wykresie. Wykres może składać się z wielu serii, a każda seria zawiera punkty danych.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];
```

Tutaj mamy dostęp do pierwszych dwóch serii na naszym wykresie. 

## Krok 4: Dostosuj punkty danych

Tutaj dzieje się magia! Dostosujmy określone punkty danych w naszej serii.

```csharp
ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];
```

Pobieramy punkty danych z pierwszej serii. Teraz dostosujmy te punkty.

### Dostosuj punkt danych 00

```csharp
dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;
```

 Dla`dataPoint00`, ustawiamy eksplozję (przydatne w przypadku wykresów kołowych), zmieniamy symbol znacznika na okrąg i ustawiamy rozmiar znacznika na 15.

### Dostosuj punkt danych 01

```csharp
dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;
```

 Dla`dataPoint01`, zmieniamy symbol znacznika na romb i ustawiamy rozmiar znacznika na 20.

### Dostosuj punkt danych w serii 1

```csharp
ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

 Dla trzeciego punktu danych w`series1`, ustawiamy go na odwracanie, jeśli wartość jest ujemna, zmieniamy symbol znacznika na gwiazdkę i ustawiamy rozmiar znacznika na 20.

## Krok 5: Zapisz dokument

Na koniec zapiszmy nasz dokument ze wszystkimi dostosowaniami.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

 Ta linia zapisuje dokument w określonym katalogu pod nazwą`WorkingWithCharts.SingleChartDataPoint.docx`.

## Wniosek

masz to! Pomyślnie dostosowałeś poszczególne punkty danych na wykresie za pomocą Aspose.Words dla .NET. Dostosowując kilka właściwości, możesz sprawić, że Twoje wykresy będą o wiele bardziej informacyjne i atrakcyjne wizualnie. Zatem śmiało eksperymentuj z różnymi znacznikami i rozmiarami, aby zobaczyć, co najlepiej sprawdzi się w przypadku Twoich danych.

## Często zadawane pytania

### Czy mogę dostosować punkty danych na wykresach innych typów?

Absolutnie! Możesz dostosowywać punkty danych na różnych typach wykresów, w tym na wykresach słupkowych, wykresach kołowych i nie tylko. Proces jest podobny w przypadku różnych typów wykresów.

### Czy można dodać niestandardowe etykiety do punktów danych?

 Tak, możesz dodawać niestandardowe etykiety do punktów danych za pomocą`ChartDataPoint.Label` nieruchomość. Dzięki temu można zapewnić większy kontekst dla każdego punktu danych.

### Jak mogę usunąć punkt danych z serii?

 Można usunąć punkt danych, ustawiając jego widoczność na wartość Fałsz za pomocą`dataPoint.IsVisible = false`.

### Czy mogę używać obrazów jako znaczników punktów danych?

Chociaż Aspose.Words nie obsługuje używania obrazów bezpośrednio jako znaczników, możesz tworzyć niestandardowe kształty i używać ich jako znaczników.

### Czy można animować punkty danych na wykresie?

Aspose.Words dla .NET nie obsługuje animacji punktów danych na wykresie. Można jednak tworzyć animowane wykresy za pomocą innych narzędzi i osadzać je w dokumentach programu Word.