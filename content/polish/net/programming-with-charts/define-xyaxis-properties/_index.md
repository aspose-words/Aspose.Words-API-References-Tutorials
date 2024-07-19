---
title: Zdefiniuj właściwości osi XY na wykresie
linktitle: Zdefiniuj właściwości osi XY na wykresie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zdefiniować właściwości osi XY na wykresie za pomocą Aspose.Words dla .NET, korzystając z tego przewodnika krok po kroku. Idealny dla programistów .NET.
type: docs
weight: 10
url: /pl/net/programming-with-charts/define-xyaxis-properties/
---
## Wstęp

Wykresy są potężnym narzędziem do wizualizacji danych. Kiedy potrzebujesz tworzyć profesjonalne dokumenty z dynamicznymi wykresami, Aspose.Words dla .NET jest nieocenioną biblioteką. Ten artykuł przeprowadzi Cię przez proces definiowania właściwości osi XY na wykresie przy użyciu Aspose.Words dla .NET, dzieląc każdy krok w celu zapewnienia przejrzystości i łatwości zrozumienia.

## Warunki wstępne

Zanim zagłębisz się w kodowanie, musisz spełnić kilka warunków wstępnych:

1. Aspose.Words dla .NET: Upewnij się, że masz bibliotekę Aspose.Words dla .NET. Możesz[Pobierz to tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: potrzebujesz zintegrowanego środowiska programistycznego (IDE), takiego jak Visual Studio.
3. .NET Framework: Upewnij się, że środowisko programistyczne jest skonfigurowane pod kątem programowania .NET.
4. Podstawowa znajomość języka C#: W tym przewodniku założono, że masz podstawową wiedzę na temat programowania w języku C#.

## Importuj przestrzenie nazw

Na początek musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Dzięki temu masz dostęp do wszystkich klas i metod wymaganych do tworzenia dokumentów i wykresów oraz manipulowania nimi.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

Podzielimy ten proces na proste kroki, z których każdy skupia się na określonej części definiowania właściwości osi XY na wykresie.

## Krok 1: Zainicjuj dokument i narzędzie DocumentBuider

 Najpierw musisz zainicjować nowy dokument i a`DocumentBuilder` obiekt. The`DocumentBuilder` pomaga we wstawieniu treści do dokumentu.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstaw wykres

Następnie wstawisz wykres do dokumentu. W tym przykładzie użyjemy wykresu warstwowego. W razie potrzeby możesz dostosować wymiary wykresu.

```csharp
// Wstaw wykres
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Wyczyść serię domyślną i dodaj dane niestandardowe

Domyślnie wykres będzie zawierał kilka predefiniowanych serii. Wyczyścimy je i dodamy naszą niestandardową serię danych.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
	new DateTime[]
	{
		new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
		new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
	},
	new double[] { 640, 320, 280, 120, 150 });
```

## Krok 4: Zdefiniuj właściwości osi X

Teraz czas na zdefiniowanie właściwości osi X. Obejmuje to ustawienie typu kategorii, dostosowanie skrzyżowania osi oraz dostosowanie znaczników i etykiet.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3; //Mierzone w jednostkach wyświetlania osi Y (setki).
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;
```

## Krok 5: Zdefiniuj właściwości osi Y

Podobnie ustawisz właściwości osi Y. Obejmuje to ustawienie położenia etykiety znacznika, jednostek głównych i pomocniczych, jednostki wyświetlania i skalowania.

```csharp
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Krok 6: Zapisz dokument

Na koniec zapisz dokument w określonym katalogu. Spowoduje to wygenerowanie dokumentu programu Word z dostosowanym wykresem.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Wniosek

Tworzenie i dostosowywanie wykresów w dokumentach programu Word przy użyciu Aspose.Words dla .NET jest proste, jeśli zrozumiesz poszczególne kroki. Ten przewodnik przeprowadził Cię przez proces definiowania właściwości osi XY na wykresie, od inicjalizacji dokumentu po zapisanie produktu końcowego. Dzięki tym umiejętnościom możesz tworzyć szczegółowe, profesjonalnie wyglądające wykresy, które wzbogacą Twoje dokumenty.

## Często zadawane pytania

### Jakie typy wykresów mogę tworzyć za pomocą Aspose.Words dla .NET?
Możesz tworzyć różne typy wykresów, w tym obszarowe, słupkowe, liniowe, kołowe i inne.

### Jak zainstalować Aspose.Words dla .NET?
 Możesz pobrać Aspose.Words dla .NET z[Tutaj](https://releases.aspose.com/words/net/) i postępuj zgodnie z dostarczonymi instrukcjami instalacji.

### Czy mogę dostosować wygląd moich wykresów?
Tak, Aspose.Words dla .NET umożliwia szerokie dostosowywanie wykresów, w tym kolorów, czcionek i właściwości osi.

### Czy dostępna jest bezpłatna wersja próbna Aspose.Words dla .NET?
 Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć więcej samouczków i dokumentacji?
 Więcej samouczków i szczegółową dokumentację można znaleźć na stronie[Strona dokumentacji Aspose.Words dla platformy .NET](https://reference.aspose.com/words/net/).
