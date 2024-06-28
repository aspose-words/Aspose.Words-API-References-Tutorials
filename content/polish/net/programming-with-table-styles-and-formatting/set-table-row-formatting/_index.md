---
title: Ustaw formatowanie wierszy tabeli
linktitle: Ustaw formatowanie wierszy tabeli
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący ustawiania formatowania wierszy tabeli przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

W tym samouczku przeprowadzimy Cię krok po kroku przez proces ustawiania formatowania wierszy tabeli za pomocą Aspose.Words dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak dostosować wysokość i dopełnienie wiersza tabeli w dokumentach programu Word za pomocą Aspose.Words dla .NET.

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. To jest lokalizacja, w której chcesz zapisać edytowany dokument programu Word. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Utwórz nowy dokument i narzędzie do tworzenia dokumentów
 Następnie musisz utworzyć nową instancję pliku`Document` class i konstruktor dokumentu dla tego dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Rozpocznij nową tabelę i dodaj komórkę
Aby rozpocząć tworzenie tabeli, używamy`StartTable()` metodą konstruktora dokumentu, następnie dodajemy komórkę do tabeli za pomocą metody`InsertCell()` metoda.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Krok 4: Zdefiniuj formatowanie linii
 Teraz możemy ustawić formatowanie wierszy, uzyskując dostęp do pliku`RowFormat` obiekt`DocumentBuilder` obiekt. Wysokość linii i marginesy (dopełnienia) możemy ustawić za pomocą odpowiednich właściwości.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Krok 5: Ustaw marginesy tabeli
 Następnie możemy ustawić dopełnienia tabeli, uzyskując dostęp do odpowiednich właściwości pliku`Table` obiekt. Marginesy te zostaną zastosowane do wszystkich wierszy tabeli.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Krok 6: Dodaj treść do wiersza
 Na koniec możemy dodać treść do linii za pomocą narzędzia do tworzenia dokumentów`Writeln()` metoda.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Krok 7: Zakończ tabelę i zapisz dokument
W

 koniec, kończymy tworzenie tabeli za pomocą`EndRow()` I`EndTable()` metodę, następnie zapisujemy zmodyfikowany dokument do pliku.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Przykładowy kod źródłowy dla ustawienia formatowania wierszy tabeli przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Te właściwości formatowania są ustawiane w tabeli i stosowane do wszystkich wierszy w tabeli.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Wniosek
tym samouczku nauczyliśmy się, jak ustawić formatowanie wierszy tabeli za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz łatwo dostosować wysokość wierszy tabeli i marginesy w dokumentach programu Word. Aspose.Words oferuje potężny i elastyczny interfejs API do manipulowania i formatowania tabel w dokumentach. Dzięki tej wiedzy możesz dostosować układ wizualny swoich stołów do swoich konkretnych potrzeb.