---
title: Formatuj liczbę etykiet danych na wykresie
linktitle: Formatuj liczbę etykiet danych na wykresie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak sformatować liczbę etykiet danych na wykresie za pomocą Aspose.Words dla .NET. Z łatwością dostosowuj formaty liczb w etykietach danych.
type: docs
weight: 10
url: /pl/net/programming-with-charts/format-number-of-data-label/
---

tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do formatowania liczby etykiet danych na wykresie. Dostarczony kod źródłowy pokazuje, jak utworzyć wykres, dodać dane serii i dostosować format liczbowy etykiet danych.

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

 Następnie wstaw wykres do dokumentu za pomocą`InsertChart` metoda`DocumentBuilder`. W tym przykładzie wstawimy wykres liniowy.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Krok 3: Dodaj dane serii do wykresu

Dodaj dane serii do wykresu. W tym przykładzie dodamy trzy kategorie i odpowiadające im wartości.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Krok 4: Dostosuj format liczbowy etykiet danych

 Aby sformatować liczbę etykiet danych, przejdź do`DataLabels` Kolekcja związana z serią.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

W tym przykładzie dla każdej etykiety danych ustawiamy różne formaty liczb. Pierwsza etykieta danych jest sformatowana jako waluta, druga jako data, a trzecia jako wartość procentowa.

## Krok 5: Zapisz dokument

 Na koniec zapisz dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

To kończy implementację formatowania liczby etykiet danych na wykresie przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy formatu etykiety liczby danych przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Usuń domyślnie wygenerowaną serię.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Możesz też ustawić kod formatu, który ma być powiązany z komórką źródłową,
	// tym przypadku NumberFormat zostanie zresetowany do ogólnego i odziedziczony z komórki źródłowej.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Wniosek

W tym samouczku nauczyłeś się formatować liczbę etykiet danych na wykresie za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz utworzyć wykres, dodać dane serii i dostosować format liczbowy etykiet danych zgodnie ze swoimi wymaganiami.

 Aspose.Words dla .NET zapewnia kompleksowe API do przetwarzania słów z wykresami w dokumentach Word, umożliwiając manipulowanie różnymi aspektami wykresów, w tym etykietami danych. Uzyskując dostęp do`DataLabels` kolekcji powiązanej z serią, możesz dostosować format liczbowy poszczególnych etykiet danych.

Interfejs API pozwala kontrolować wyświetlanie wartości, ustawiać różne formaty liczb dla każdej etykiety danych i łączyć format liczb z komórką źródłową. Ta elastyczność umożliwia prezentowanie danych liczbowych na wykresach w żądanym formacie, takim jak symbole walut, formaty dat i wartości procentowe.

Używając Aspose.Words dla .NET, możesz włączyć zaawansowane możliwości tworzenia wykresów do swoich aplikacji .NET i generować profesjonalnie wyglądające dokumenty z w pełni sformatowanymi wykresami i etykietami danych.

### Często zadawane pytania

#### Pytanie 1. Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to bogata w funkcje biblioteka do przetwarzania dokumentów, która umożliwia programistom programowe tworzenie, manipulowanie i zapisywanie dokumentów programu Word w aplikacjach .NET. Zapewnia szeroką gamę funkcji do przetwarzania tekstu z elementami dokumentu, w tym wykresami i etykietami danych.

#### Pytanie 2. Jak mogę zainstalować Aspose.Words dla .NET?
Możesz zainstalować Aspose.Words dla .NET, pobierając go za pomocą menedżera pakietów NuGet w programie Visual Studio. Po prostu wyszukaj „Aspose.Words” w menedżerze pakietów NuGet i zainstaluj go w swoim projekcie.

#### Pytanie 3. Czy mogę sformatować inne aspekty wykresu za pomocą Aspose.Words dla .NET?
Tak, Aspose.Words dla .NET zapewnia szerokie możliwości formatowania różnych aspektów wykresu. Oprócz etykiet danych możesz dostosować typ wykresu, dane serii, właściwości osi, legendę, tytuł, obszar wykresu i wiele innych elementów wykresu. Interfejs API zapewnia szczegółową kontrolę nad wyglądem i formatowaniem wykresów.

#### Pytanie 4. Czy mogę zastosować różne formaty liczb do różnych etykiet danych w tej samej serii?
Tak, Aspose.Words dla .NET umożliwia zastosowanie różnych formatów liczb do poszczególnych etykiet danych w tej samej serii. Uzyskując dostęp do`DataLabels` kolekcję powiązaną z serią, możesz ustawić`FormatCode` właściwość każdej etykiety danych, aby określić żądany format liczb. Dzięki temu możesz prezentować wartości liczbowe w różnych formatach na tym samym wykresie.

#### Pytanie 5. Czy mogę używać niestandardowych formatów liczb w etykietach danych?
 Tak, Aspose.Words dla .NET obsługuje niestandardowe formaty liczb dla etykiet danych. Możesz określić żądany format liczb, ustawiając`FormatCode` właściwość etykiety danych na kod formatu niestandardowego. Zapewnia to elastyczność stosowania szerokiego zakresu formatów liczb, takich jak symbole walut, formaty dat, wartości procentowe i inne.

#### Pytanie 6. Czy mogę zapisać wykres ze sformatowanymi etykietami danych w różnych formatach?
Tak, Aspose.Words dla .NET umożliwia zapisanie dokumentu zawierającego wykres ze sformatowanymi etykietami danych w różnych formatach, takich jak DOCX, PDF, HTML i innych. Możesz wybrać odpowiedni format w oparciu o swoje wymagania i użyć`Save` metoda`Document` obiekt, aby zapisać dokument. Sformatowane etykiety danych zostaną zachowane w zapisanym dokumencie.