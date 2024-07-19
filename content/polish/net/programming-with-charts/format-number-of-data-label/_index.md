---
title: Formatuj liczbę etykiet danych na wykresie
linktitle: Formatuj liczbę etykiet danych na wykresie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak formatować etykiety danych na wykresach za pomocą Aspose.Words dla .NET, korzystając z tego przewodnika krok po kroku. Ulepszaj swoje dokumenty Word bez wysiłku.
type: docs
weight: 10
url: /pl/net/programming-with-charts/format-number-of-data-label/
---
## Wstęp

Tworzenie angażujących i informacyjnych dokumentów często wiąże się z dołączeniem wykresów z dobrze sformatowanymi etykietami danych. Jeśli jesteś programistą .NET i chcesz wzbogacić swoje dokumenty Word o zaawansowane wykresy, Aspose.Words dla .NET to fantastyczna biblioteka, która pomoże Ci to osiągnąć. Ten samouczek przeprowadzi Cię krok po kroku przez proces formatowania etykiet liczbowych na wykresie przy użyciu Aspose.Words dla .NET.

## Warunki wstępne

Zanim zagłębisz się w kod, musisz spełnić kilka warunków wstępnych:

-  Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words dla .NET. Jeśli jeszcze go nie zainstalowałeś, możesz[Pobierz to tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: Należy mieć skonfigurowane środowisko programistyczne .NET. Zdecydowanie zaleca się korzystanie z programu Visual Studio.
- Podstawowa znajomość języka C#: Znajomość programowania w języku C# jest niezbędna, ponieważ ten samouczek obejmuje pisanie i zrozumienie kodu C#.
-  Licencja tymczasowa: Aby korzystać z Aspose.Words bez żadnych ograniczeń, możesz uzyskać[licencja tymczasowa](https://purchase.aspose.com/temporary-license/).

Przyjrzyjmy się teraz krok po kroku procesowi formatowania etykiet liczbowych na wykresie.

## Importuj przestrzenie nazw

Po pierwsze, musimy zaimportować niezbędne przestrzenie nazw do pracy z Aspose.Words dla .NET. Dodaj następujące wiersze na górze pliku C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Krok 1: Skonfiguruj katalog dokumentów

Zanim zaczniesz manipulować dokumentem programu Word, musisz określić katalog, w którym dokument zostanie zapisany. Jest to niezbędne do późniejszego zapisu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Zainicjuj dokument i narzędzie DocumentBuilder

 Następnym krokiem jest zainicjowanie nowego`Document` i a`DocumentBuilder` . The`DocumentBuilder` jest klasą pomocniczą, która pozwala nam konstruować treść dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstaw wykres do dokumentu

 Teraz wstawmy wykres do dokumentu za pomocą`DocumentBuilder`. W tym samouczku jako przykład wykorzystamy wykres liniowy.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

Tutaj wstawiamy wykres liniowy o określonej szerokości i wysokości oraz ustalamy tytuł wykresu.

## Krok 4: Wyczyść serię domyślną i dodaj nową serię

Domyślnie wykres będzie zawierał wstępnie wygenerowane serie. Musimy je wyczyścić i dodać własną serię z określonymi punktami danych.

```csharp
// Usuń domyślnie wygenerowaną serię.
chart.Series.Clear();

// Dodaj nową serię z niestandardowymi punktami danych.
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
	new string[] { "Category 1", "Category 2", "Category 3" }, 
	new double[] { 2.5, 1.5, 3.5 });
```

## Krok 5: Włącz etykiety danych

Aby wyświetlić etykiety danych na wykresie, musimy włączyć je dla naszej serii.

```csharp
series1.HasDataLabels = true;
series1.DataLabels.ShowValue = true;
```

## Krok 6: Sformatuj etykiety danych

Podstawą tego samouczka jest formatowanie etykiet danych. Możemy zastosować różne formaty liczb indywidualnie do każdej etykiety danych.

```csharp
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00"; // Format waluty
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy"; // Format daty
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%"; // Format procentowy
```

 Ponadto można połączyć format etykiety danych z komórką źródłową. Po połączeniu,`NumberFormat` zostanie zresetowany do stanu ogólnego i odziedziczony z komórki źródłowej.

```csharp
series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
```

## Krok 7: Zapisz dokument

Na koniec zapisz dokument w określonym katalogu.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Spowoduje to zapisanie dokumentu pod określoną nazwą i zachowanie wykresu ze sformatowanymi etykietami danych.

## Wniosek

Formatowanie etykiet danych na wykresie za pomocą Aspose.Words dla .NET może znacznie zwiększyć czytelność i profesjonalizm dokumentów programu Word. Postępując zgodnie z tym przewodnikiem krok po kroku, powinieneś być teraz w stanie utworzyć wykres, dodać serie danych i sformatować etykiety danych zgodnie ze swoimi potrzebami. Aspose.Words dla .NET to potężne narzędzie, które pozwala na szerokie dostosowywanie i automatyzację dokumentów Word, co czyni go nieocenionym nabytkiem dla programistów .NET.

## Często zadawane pytania

### Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka do programowego tworzenia, manipulowania i konwertowania dokumentów programu Word przy użyciu języka C#.

### Czy mogę formatować inne typy wykresów za pomocą Aspose.Words dla .NET?
Tak, Aspose.Words dla .NET obsługuje różne typy wykresów, w tym słupkowe, kolumnowe, kołowe i inne.

### Jak uzyskać tymczasową licencję na Aspose.Words dla .NET?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).

### Czy można połączyć etykiety danych z komórkami źródłowymi w programie Excel?
Tak, możesz połączyć etykiety danych z komórkami źródłowymi, umożliwiając dziedziczenie formatu liczb z komórki źródłowej.

### Gdzie mogę znaleźć bardziej szczegółową dokumentację Aspose.Words dla .NET?
 Można znaleźć obszerną dokumentację[Tutaj](https://reference.aspose.com/words/net/).
