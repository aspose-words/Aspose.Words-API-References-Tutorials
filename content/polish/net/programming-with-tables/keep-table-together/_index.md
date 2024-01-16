---
title: Trzymajcie razem stół
linktitle: Trzymajcie razem stół
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak połączyć tabelę w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/keep-table-together/
---

W tym samouczku nauczymy się, jak łączyć tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz w stanie zachować tabelę w stanie nienaruszonym bez dzielenia jej na wiele stron w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Załadowanie dokumentu i pobranie tabeli
Aby rozpocząć przetwarzanie tekstu z tabelą, musimy załadować dokument i pobrać tabelę, którą chcemy zachować razem. Wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Odzyskaj stół
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 3: Włącz opcję „KeepWithNext”.
Aby zachować tabelę w całości i zapobiec jej dzieleniu na wiele stron, musimy włączyć opcję „KeepWithNext” dla każdego akapitu w tabeli z wyjątkiem ostatnich akapitów ostatniego wiersza tabeli. Użyj następującego kodu:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Tutaj przeglądamy każdą komórkę w tabeli i włączamy opcję „KeepWithNext” dla każdego akapitu w komórce z wyjątkiem ostatnich akapitów ostatniego wiersza w tabeli.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać zmodyfikowany dokument, trzymając razem tabelę. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy narzędzia Keep Table Together przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Musimy włączyć opcję KeepWithNext dla każdego akapitu w tabeli, aby zapobiec przedostawaniu się go na stronę,
	// z wyjątkiem ostatnich akapitów w ostatnim wierszu tabeli.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak łączyć tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz zachować tabelę w stanie nienaruszonym i zapobiec jej podziałowi na wiele stron w dokumentach. Ta funkcja zapewnia większą kontrolę nad wyglądem i układem tabel w dokumentach.