---
title: Format liczb dla osi na wykresie
linktitle: Format liczb dla osi na wykresie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić format liczb dla osi na wykresie za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-charts/number-format-for-axis/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do ustawiania formatu liczb dla osi na wykresie. Dostarczony kod źródłowy pokazuje, jak utworzyć wykres, dodać dane serii i sformatować etykiety osi.

## Krok 1: Skonfiguruj projekt

Upewnij się, że masz następujące wymagania wstępne:

- Zainstalowana biblioteka Aspose.Words dla .NET. Można go pobrać, używając menedżera pakietów NuGet do zainstalowania.
- Ścieżka katalogu dokumentu, w którym zostanie zapisany dokument wyjściowy.

## Krok 2: Utwórz nowy dokument i wstaw wykres.

 Stwórz nowy`Document` obiekt i a`DocumentBuilder` do zbudowania dokumentu.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Następnie użyj`InsertChart` metoda`DocumentBuilder` , aby wstawić wykres kolumnowy do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Dodaj dane serii do wykresu

Dodaj dane serii do wykresu. W tym przykładzie dodamy pięć elementów z odpowiadającymi im wartościami.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Krok 4: Sformatuj etykiety osi

 Aby ustawić format liczb dla etykiet osi Y, przejdź do`AxisY` właściwość wykresu i ustaw`NumberFormat.FormatCode` właściwość do żądanego formatu. W tym przykładzie ustawiliśmy format na „#,##0”, aby wyświetlać liczby z separatorami tysięcy.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Krok 5: Zapisz dokument

 Na koniec zapisz dokument w określonym katalogu za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

To kończy implementację ustawiania formatu liczb dla osi przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy formatu liczb dla osi przy użyciu Aspose.Words dla .NET 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Wniosek

W tym samouczku nauczyłeś się, jak ustawić format liczb dla osi na wykresie za pomocą Aspose.Words dla .NET. Postępując zgodnie z instrukcją krok po kroku i wykorzystując dostarczony kod źródłowy, możesz utworzyć nowy dokument, wstawić wykres kolumnowy, dodać dane serii i sformatować etykiety osi, aby wyświetlać liczby w określonym formacie.

Aspose.Words dla .NET zapewnia zaawansowane funkcje umożliwiające dostosowanie wyglądu wykresów w dokumentach programu Word. Ustawiając format liczb dla etykiet osi, możesz kontrolować sposób wyświetlania liczb, w tym opcje takie jak miejsca dziesiętne, separatory tysięcy, symbole walut i inne. Pozwala to na przedstawienie danych liczbowych w przejrzysty i zrozumiały sposób.

Dzięki Aspose.Words dla .NET masz elastyczność formatowania różnych aspektów wykresu, w tym etykiet osi. Ustawiając format liczb dla osi, można zapewnić spójność i poprawić czytelność wykresu, ułatwiając użytkownikom interpretację przedstawianych wartości.

### Często zadawane pytania

#### Pytanie 1. Jaki jest format liczb dla osi na wykresie?
Format liczb osi na wykresie odnosi się do formatowania zastosowanego do wartości numerycznych wyświetlanych na osi. Pozwala kontrolować sposób prezentacji liczb, w tym opcje takie jak miejsca dziesiętne, separatory tysięcy, symbole walut, znaki procentów i inne. Ustawiając format liczb, możesz dostosować wygląd danych liczbowych na wykresie do swoich konkretnych wymagań.

#### Pytanie 2. Jak ustawić format liczb dla etykiet osi?
 Aby ustawić format liczb dla etykiet osi na wykresie za pomocą Aspose.Words dla .NET, możesz uzyskać dostęp do`AxisY` właściwość wykresu i ustaw`NumberFormat.FormatCode`właściwość na żądany kod formatu. Kod formatu jest zgodny ze składnią standardowych wzorców formatowania liczb i określa sposób wyświetlania liczb. Na przykład możesz użyć „#,##0.00”, aby wyświetlić liczby z dwoma miejscami po przecinku i separatorami tysięcy.

#### Pytanie 3. Czy mogę ustawić różne formaty liczb dla etykiet osi X i Y?
Tak, możesz ustawić różne formaty liczb dla etykiet osi X i Y za pomocą Aspose.Words dla .NET. Uzyskaj dostęp do odpowiedniej osi (`AxisX` dla osi X lub`AxisY` dla osi Y) wykresu i zmodyfikuj`NumberFormat.FormatCode` właściwość indywidualnie dla każdej osi. Umożliwia to zastosowanie różnych formatów liczb do etykiet na każdej osi w zależności od konkretnych wymagań.

#### Pytanie 4. Jakich typowych kodów formatu liczb mogę użyć?
Aspose.Words dla .NET obsługuje szeroką gamę kodów formatu liczb, których można używać do formatowania etykiet osi na wykresie. Niektóre typowe kody formatu obejmują:

- `0` Lub`#` - Wyświetla liczbę bez miejsc po przecinku.
- `0.00` Lub`#.00` - Wyświetla liczbę z dwoma miejscami po przecinku.
- `#,##0` Wyświetla liczbę z tysiącami separatorów.
- `"€"0.00` - Wyświetla liczbę z symbolem waluty euro i dwoma miejscami po przecinku.
- `"%"0` - Wyświetla liczbę jako procent.

 Więcej informacji o numerze znajdziesz[kody formatu](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) w dokumentacji API Aspose.Words dla .NET.

#### Pytanie 5. Czy mogę dostosować inne właściwości etykiet osi?
Tak, Aspose.Words dla .NET zapewnia szeroką gamę właściwości umożliwiających dostosowanie wyglądu i zachowania etykiet osi. Oprócz formatu liczb można modyfikować właściwości, takie jak czcionka, rozmiar, kolor, orientacja, wyrównanie i inne. Umożliwia to pełne dostosowanie etykiet osi do żądanego stylu i wymagań dotyczących prezentacji.