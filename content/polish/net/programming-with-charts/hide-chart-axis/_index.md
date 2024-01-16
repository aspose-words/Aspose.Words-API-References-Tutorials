---
title: Ukryj oś wykresu w dokumencie programu Word
linktitle: Ukryj oś wykresu w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ukryć oś wykresu w dokumencie za pomocą Aspose.Words dla .NET. Ukryj oś, aby uzyskać czystszy i bardziej skupiony widok wykresu.
type: docs
weight: 10
url: /pl/net/programming-with-charts/hide-chart-axis/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do ukrywania osi wykresu w dokumencie. Dostarczony kod źródłowy pokazuje, jak utworzyć wykres, dodać dane serii i ukryć oś wykresu.

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

 Następnie wstaw wykres do dokumentu za pomocą`InsertChart` metoda`DocumentBuilder`. W tym przykładzie wstawimy wykres kolumnowy.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Dodaj dane serii do wykresu

Dodaj dane serii do wykresu. W tym przykładzie dodamy pięć elementów i odpowiadające im wartości.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Krok 4: Ukryj oś wykresu

 Aby ukryć oś wykresu, przejdź do`AxisY` właściwość wykresu i ustaw`Hidden`własność do`true`.

```csharp
chart.AxisY.Hidden = true;
```

tym przykładzie ukrywamy oś Y wykresu.

## Krok 5: Zapisz dokument

 Na koniec zapisz dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

To kończy implementację ukrywania osi wykresu za pomocą Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla opcji Ukryj oś wykresu przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Wniosek

W tym samouczku nauczyłeś się, jak ukryć oś wykresu w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z instrukcją krok po kroku i wykorzystując dostarczony kod źródłowy, możesz utworzyć wykres, dodać dane serii i ukryć oś wykresu, aby uzyskać pożądany efekt wizualny.

 Aspose.Words dla .NET zapewnia kompleksowe API do przetwarzania słów z wykresami w dokumentach Word, umożliwiając manipulowanie różnymi aspektami wykresu, w tym właściwościami osi. Uzyskując dostęp do`AxisY` wykresu, możesz ukryć oś Y, aby usunąć ją z wizualizacji wykresu.

Ukrycie osi wykresu może być przydatne, gdy chcesz skupić się na danych wykresu bez rozpraszania linii osi i etykiet. Zapewnia czystszy i bardziej minimalistyczny wygląd wykresu.

Używając Aspose.Words dla .NET, możesz łatwo włączyć możliwości tworzenia wykresów do swoich aplikacji .NET i generować profesjonalnie wyglądające dokumenty z niestandardowymi wykresami i ukrytymi osiami wykresów.

### Często zadawane pytania

#### Pytanie 1. Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka do przetwarzania dokumentów, która umożliwia programistom programowe tworzenie, manipulowanie i zapisywanie dokumentów programu Word w aplikacjach .NET. Zapewnia szeroką gamę funkcji do przetwarzania tekstu z elementami dokumentu, w tym wykresami i osiami wykresów.

#### Pytanie 2. Jak mogę zainstalować Aspose.Words dla .NET?
Możesz zainstalować Aspose.Words dla .NET, pobierając go za pomocą menedżera pakietów NuGet w programie Visual Studio. Po prostu wyszukaj „Aspose.Words” w menedżerze pakietów NuGet i zainstaluj go w swoim projekcie.

#### Pytanie 3. Czy mogę ukryć zarówno oś X, jak i oś Y wykresu?
 Tak, możesz ukryć zarówno oś X, jak i Y wykresu, używając Aspose.Words dla .NET. Aby ukryć oś X, możesz uzyskać dostęp do`AxisX` właściwość wykresu i ustaw`Hidden`własność do`true` . Podobnie, aby ukryć oś Y, możesz uzyskać dostęp do`AxisY` właściwość i ustaw`Hidden`własność do`true`. Dzięki temu można usunąć obie osie z wizualizacji wykresu.

#### Pytanie 4. Czy mogę ponownie pokazać oś po jej ukryciu?
Tak, możesz ponownie wyświetlić oś wykresu po jej ukryciu za pomocą Aspose.Words dla .NET. Aby wyświetlić ukrytą oś, po prostu ustaw`Hidden` właściwość odpowiedniego`AxisX` Lub`AxisY` oponować`false`. Spowoduje to, że oś będzie ponownie widoczna na wykresie.

#### Pytanie 5. Czy mogę dostosować inne właściwości osi wykresu?
 Tak, Aspose.Words dla .NET pozwala dostosować różne właściwości osi wykresu, takie jak tytuł osi, etykiety, kolor linii i inne. Uzyskując dostęp do`AxisX` I`AxisY` właściwości wykresu, możesz modyfikować właściwości, takie jak`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, i wiele innych. Daje to precyzyjną kontrolę nad wyglądem i zachowaniem osi wykresu.

#### Pytanie 6. Czy mogę zapisać wykres z ukrytą osią w różnych formatach plików?
 Tak, Aspose.Words dla .NET umożliwia zapisanie dokumentu zawierającego wykres z ukrytą osią w różnych formatach plików, takich jak DOCX, PDF, HTML i inne. Możesz wybrać żądany format wyjściowy w oparciu o swoje wymagania i użyć`Save` metoda`Document` obiekt, aby zapisać dokument. Ukryta oś zostanie zachowana w zapisanym dokumencie.