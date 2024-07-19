---
title: Wstaw tabelę z HTML
linktitle: Wstaw tabelę z HTML
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić tabelę z HTML do dokumentu programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/insert-table-from-html/
---

tym samouczku nauczymy się, jak wstawić tabelę do dokumentu Word z HTML za pomocą Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo wstawiać tabele z HTML do dokumentów programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Tworzenie dokumentu i inicjalizacja generatora dokumentów
Aby rozpocząć przetwarzanie tekstu za pomocą dokumentu i generatora dokumentów, wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tworzenie dokumentów
Document doc = new Document();

// Zainicjuj generator dokumentów
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 3: Wstawianie tabeli z HTML
Następnie wstawimy tabelę do dokumentu za pomocą kodu HTML. Użyj następującego kodu:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Tutaj używamy`InsertHtml` metoda konstruktora dokumentów polegająca na wstawieniu kodu HTML zawierającego tabelę. Określony kod HTML tworzy tabelę zawierającą dwa wiersze i dwie komórki w każdym wierszu. Możesz dostosować zawartość tabeli, modyfikując kod HTML zgodnie ze swoimi potrzebami.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać zmodyfikowany dokument z tabelą wstawioną z HTML. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy dla Wstaw tabelę z HTML przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Należy pamiętać, że ustawienie AutoFitSettings nie ma zastosowania do tabel wstawionych z formatu HTML.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak wstawić tabelę do dokumentu Word z HTML przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz programowo wstawiać tabele z HTML do dokumentów programu Word. Ta funkcja umożliwia konwersję i importowanie danych tabelarycznych ze źródeł HTML do dokumentów programu Word.
