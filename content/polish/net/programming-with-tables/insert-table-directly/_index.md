---
title: Wstaw tabelę bezpośrednio
linktitle: Wstaw tabelę bezpośrednio
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić tabelę bezpośrednio do dokumentu programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/insert-table-directly/
---

W tym samouczku nauczymy się, jak bezpośrednio wstawić tabelę do dokumentu programu Word za pomocą Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo wstawiać tabele bezpośrednio do dokumentów programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Tworzenie dokumentu i tabeli
Aby rozpocząć przetwarzanie słów z tablicą, musimy utworzyć nowy dokument i zainicjować tablicę. Wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tworzenie dokumentów
Document doc = new Document();

//Utwórz tablicę
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 3: Budowanie tablicy
Następnie zbudujemy tabelę, dodając wiersze i komórki. Użyj poniższego kodu jako przykładu:

```csharp
// Utwórz pierwszy rząd
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Utwórz pierwszą komórkę
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Duplikuj komórkę dla drugiej komórki w wierszu
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Tutaj tworzymy wiersz z`AllowBreakAcrossPages` właściwość ustawiona na`true` aby umożliwić dzielenie strony między wierszami. Następnie tworzymy komórkę z kolorowym tłem, stałą szerokością i określoną zawartością tekstową. Następnie duplikujemy tę komórkę, aby utworzyć drugą komórkę w wierszu.

## Krok 4: Tabela automatycznego dopasowania
Możemy zastosować automatyczne dostosowania do tabeli, aby ją poprawnie sformatować. Użyj następującego kodu:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Ta linia kodu stosuje automatyczne dopasowanie w oparciu o stałą szerokość kolumn.

## Krok 5: Rejestracja

  zmodyfikowany dokument
Na koniec musimy zapisać zmodyfikowany dokument z bezpośrednio wstawioną tabelą. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy dla Wstaw tabelę bezpośrednio przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Zaczynamy od utworzenia obiektu tabeli. Pamiętaj, że musimy przekazać obiekt document
	//do konstruktora każdego węzła. Dzieje się tak, ponieważ każdy węzeł, który tworzymy, musi należeć
	// do jakiegoś dokumentu.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Tutaj moglibyśmy wywołać SureMinimum, aby utworzyć dla nas wiersze i komórki. Ta metoda jest stosowana
	// aby upewnić się, że określony węzeł jest prawidłowy. W takim przypadku prawidłowa tabela powinna zawierać co najmniej jeden wiersz i jedną komórkę.
	// Zamiast tego zajmiemy się tworzeniem wiersza i tabeli samodzielnie.
	// Byłby to najlepszy sposób, aby to zrobić, gdybyśmy tworzyli tabelę wewnątrz algorytmu.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Możemy teraz zastosować dowolne ustawienia automatycznego dopasowania.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Następnie powtórzylibyśmy proces dla pozostałych komórek i wierszy tabeli.
	// Możemy także przyspieszyć działanie klonując istniejące komórki i wiersze.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Wniosek
tym samouczku nauczyliśmy się, jak bezpośrednio wstawić tabelę do dokumentu programu Word za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz programowo wstawiać tabele bezpośrednio do dokumentów programu Word. Ta funkcja umożliwia tworzenie i dostosowywanie tabel zgodnie z własnymi potrzebami.