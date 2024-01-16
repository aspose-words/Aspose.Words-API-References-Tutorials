---
title: Zdefiniuj właściwości osi XY na wykresie
linktitle: Zdefiniuj właściwości osi XY na wykresie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zdefiniować właściwości osi XY na wykresie za pomocą Aspose.Words dla .NET. Pokazano opcje dostosowywania osi X i Y.
type: docs
weight: 10
url: /pl/net/programming-with-charts/define-xyaxis-properties/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do definiowania właściwości osi X i Y na wykresie. Dostarczony kod źródłowy pokazuje, jak utworzyć wykres, dodać dane serii i dostosować właściwości osi.

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

 Następnie wstaw wykres do dokumentu za pomocą`InsertChart` metoda`DocumentBuilder`. W tym przykładzie wstawimy wykres warstwowy.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Dodaj dane serii do wykresu

Dodaj dane serii do wykresu. W tym przykładzie dodamy pięć punktów danych z odpowiadającymi im datami i wartościami.

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

## Krok 4: Dostosuj właściwości osi X i Y

 Aby dostosować właściwości osi X i Y, przejdź do opcji`ChartAxis` obiekty powiązane z wykresem.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Zmodyfikuj właściwości pliku`xAxis` I`yAxis`obiektów, aby ustawić żądane opcje dla osi X i Y. W tym przykładzie zademonstrujemy kilka typowych właściwości, które można dostosować.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Krok 5: Zapisz dokument

 Na koniec zapisz dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

To kończy implementację definiowania właściwości osi XY na wykresie przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Zdefiniuj właściwości XYAxis przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Wstaw wykres
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Zmień oś X na kategorię zamiast na datę, aby wszystkie punkty były umieszczone w równych odstępach na osi X.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //Mierzone w jednostkach wyświetlania osi Y (setki).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Wniosek

W tym samouczku nauczyłeś się definiować właściwości osi X i Y na wykresie przy użyciu Aspose.Words dla .NET. Postępując zgodnie z przewodnikiem krok po kroku, możesz utworzyć wykres, dodać dane serii i dostosować właściwości osi, aby spełniały określone wymagania. Aspose.Words dla .NET zapewnia kompleksowe API do przetwarzania słów z wykresami w dokumentach Word, umożliwiając manipulowanie różnymi aspektami wykresu, w tym osiami.

Uzyskując dostęp do`ChartAxis` obiektów powiązanych z wykresem można modyfikować właściwości, takie jak typ kategorii, przecięcia osi, znaczniki, pozycje etykiet, skalowanie i inne. Ta elastyczność umożliwia dostosowanie wyglądu i zachowania osi wykresu w celu efektywnej prezentacji danych.

Używając Aspose.Words dla .NET, możesz bezproblemowo zintegrować możliwości tworzenia i dostosowywania wykresów z aplikacjami .NET i automatyzować generowanie profesjonalnie wyglądających dokumentów z bogatymi wizualizacjami.

### Często zadawane pytania

#### Pytanie 1. Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka do przetwarzania dokumentów, która umożliwia programistom programowe tworzenie, manipulowanie i zapisywanie dokumentów programu Word w aplikacjach .NET. Zapewnia szeroką gamę funkcji do przetwarzania tekstu z elementami dokumentu, w tym wykresami.

#### Pytanie 2. Jak mogę zainstalować Aspose.Words dla .NET?
Możesz zainstalować Aspose.Words dla .NET, pobierając go za pomocą menedżera pakietów NuGet w programie Visual Studio. Po prostu wyszukaj „Aspose.Words” w menedżerze pakietów NuGet i zainstaluj go w swoim projekcie.

#### Pytanie 3. Czy mogę dostosować inne aspekty wykresu za pomocą Aspose.Words dla .NET?
Tak, Aspose.Words dla .NET zapewnia szerokie możliwości dostosowywania różnych aspektów wykresu. Oprócz definiowania właściwości osi można modyfikować typ wykresu, serie danych, legendę, tytuł, obszar wykresu, etykiety danych i wiele innych elementów wykresu. Interfejs API zapewnia szczegółową kontrolę nad wyglądem i zachowaniem wykresów.

#### Pytanie 4. Czy mogę tworzyć różne typy wykresów za pomocą Aspose.Words dla .NET?
 Tak, Aspose.Words dla .NET obsługuje szeroką gamę typów wykresów, w tym obszarowe, słupkowe, liniowe, kołowe, punktowe i inne. Możesz skorzystać z`ChartType` wyliczenie, aby określić żądany typ wykresu podczas wstawiania kształtu wykresu do dokumentu programu Word.

#### Pytanie 5. Czy mogę zapisać wykres w różnych formatach?
Tak, Aspose.Words dla .NET umożliwia zapisanie dokumentu zawierającego wykres w różnych formatach, takich jak DOCX, PDF, HTML i innych. Możesz wybrać odpowiedni format w oparciu o swoje wymagania i użyć`Save` metoda`Document` obiekt, aby zapisać dokument.

#### Pytanie 6. Czy mogę zastosować te techniki do wielu wykresów w dokumencie?
 Tak, możesz zastosować te techniki do wielu wykresów w dokumencie, powtarzając niezbędne kroki dla każdego wykresu. Możesz stworzyć osobne`Chart` I`ChartAxis` obiekty dla każdego wykresu i odpowiednio dostosuj ich właściwości. Aspose.Words dla .NET zapewnia pełną obsługę przetwarzania słów z wieloma wykresami w jednym dokumencie.