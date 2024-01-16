---
title: Formatuj tabelę i komórkę z różnymi obramowaniami
linktitle: Formatuj tabelę i komórkę z różnymi obramowaniami
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący formatowania tabeli i komórki z różnymi obramowaniami przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

tym samouczku przeprowadzimy Cię krok po kroku przez proces formatowania tabeli i komórki z różnymi obramowaniami przy użyciu Aspose.Words dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak zastosować niestandardowe obramowania do określonych tabel i komórek w dokumentach programu Word przy użyciu Aspose.Words dla .NET.

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

## Krok 3: Rozpocznij nową tabelę i dodaj komórki
Aby rozpocząć tworzenie tabeli, używamy`StartTable()` metodą konstruktora dokumentów, następnie dodajemy komórki do tabeli za pomocą metody`InsertCell()` metodę i zapisujemy zawartość komórek do metody using`Writeln()` metoda.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// Ustaw obramowanie dla całego stołu.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Ustaw dopełnienie tej komórki.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// Określ inne wypełnienie komórki dla drugiej komórki.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// Wyczyść formatowanie komórek z poprzednich operacji.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// Utwórz grubsze obramowanie dla pierwszej komórki w tym wierszu. Będzie inaczej
// względem granic zdefiniowanych dla tabeli.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Krok 4: Zapisz dokument

  zmieniony
Na koniec zapisz zmodyfikowany dokument do pliku. Możesz wybrać odpowiednią nazwę i lokalizację dokumentu wyjściowego.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Gratulacje! Sformatowałeś teraz tabelę i komórkę z różnymi obramowaniami przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy formatu tabeli i komórki z różnymi obramowaniami przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//Ustaw obramowanie całej tabeli.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// Ustaw cieniowanie komórki dla tej komórki.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// Określ inne cieniowanie komórki dla drugiej komórki.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// Usuń formatowanie komórki z poprzednich operacji.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// Utwórz większe obramowanie dla pierwszej komórki tego wiersza. To będzie inne
	// w porównaniu z granicami ustawionymi dla tabeli.
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak formatować tabelę i komórkę z różnymi krawędziami za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz łatwo dostosować obramowania tabel i komórek w dokumentach programu Word. Aspose.Words oferuje potężny i elastyczny interfejs API do manipulowania i formatowania tabel w dokumentach. Dzięki tej wiedzy możesz ulepszyć wizualną prezentację dokumentów Word i spełnić określone potrzeby.