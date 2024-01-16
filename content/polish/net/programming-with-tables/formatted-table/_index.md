---
title: Sformatowana tabela
linktitle: Sformatowana tabela
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć sformatowaną tabelę w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/formatted-table/
---

W tym samouczku nauczymy się, jak utworzyć sformatowaną tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo tworzyć tabele z niestandardowym formatowaniem w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Tworzenie dokumentu i inicjalizacja generatora dokumentów
Aby rozpocząć budowanie sformatowanej tabeli, musimy utworzyć nowy dokument i zainicjować generator dokumentów. Wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz dokument i zainicjuj generator dokumentów
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 3: Tworzenie sformatowanej tabeli
Następnie zbudujemy sformatowaną tabelę, korzystając z metod dostarczonych przez narzędzie do tworzenia dokumentów. Użyj następującego kodu:

```csharp
// Rozpocznij budowę tablicy
Table table = builder. StartTable();

// Konstrukcja wiersza nagłówka tabeli
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// Budowa korpusu tablicy
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// Koniec budowy tablicy
builder. EndTable();
```

 Tutaj używamy narzędzia do tworzenia dokumentów, aby krok po kroku zbudować tabelę. Zaczynamy od dzwonienia`StartTable()` aby zainicjować tabelę. Następnie używamy`InsertCell()` aby wstawić komórki i`Write()` aby dodać zawartość do każdej komórki. Używamy także różnych właściwości formatowania do definiowania formatowania wierszy, komórek i tekstu tabeli.

## Krok 4: Zapisz dokument
Na koniec musimy zapisać dokument zawierający sformatowaną tabelę. Użyj następującego kodu:

```csharp
// Zapisz dokument
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy sformatowanej tabeli przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// Jeśli w tabeli znajduje się co najmniej jeden wiersz, należy zastosować formatowanie całej tabeli.
	table.LeftIndent = 20.0;
	// Ustaw wysokość i zdefiniuj regułę wysokości dla wiersza nagłówka.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// Nie musimy określać szerokości tej komórki, ponieważ jest ona dziedziczona z poprzedniej komórki.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Zresetuj wysokość i zdefiniuj inną regułę wysokości dla treści tabeli.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// Zresetuj formatowanie czcionki.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## Wniosek
tym samouczku nauczyliśmy się, jak utworzyć sformatowaną tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz programowo tworzyć niestandardowe tabele z określonym formatowaniem w dokumentach programu Word. Ta funkcja pozwala prezentować i porządkować dane w atrakcyjny wizualnie i zorganizowany sposób.