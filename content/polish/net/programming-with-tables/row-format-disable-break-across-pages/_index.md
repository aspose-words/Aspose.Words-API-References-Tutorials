---
title: Format wiersza Wyłącz podział stron
linktitle: Format wiersza Wyłącz podział stron
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wyłączyć podział wiersza w tabeli na wielu stronach w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/row-format-disable-break-across-pages/
---

tym samouczku nauczymy się, jak wyłączyć łamanie wierszy wielostronicowej tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł wyłączyć łamanie linii dla wszystkich wierszy tabeli w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Załaduj dokument
Aby rozpocząć przetwarzanie tekstu w dokumencie, wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów i podać poprawną nazwę pliku.

## Krok 3: Wyłącz podział wierszy tabeli
Następnie wyłączymy dzielenie wierszy dla wszystkich wierszy w tabeli. Użyj następującego kodu:

```csharp
// Odzyskaj stół
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Wyłącz podział wierszy dla wszystkich wierszy w tabeli
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 W tym przypadku używamy dokumentu do pobrania pierwszej tabeli, a następnie iterujemy po wszystkich wierszach tabeli za pomocą pętli foreach. Wewnątrz pętli wyłączamy dzielenie wierszy dla każdego wiersza, ustawiając opcję`RowFormat.AllowBreakAcrossPages`własność do`false`.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać zmodyfikowany dokument z wyłączonym podziałem wierszy tabeli. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy dla formatu wierszy Wyłącz podział na stronach przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Wyłącz dzielenie stron dla wszystkich wierszy w tabeli.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Wniosek
tym samouczku dowiedzieliśmy się, jak wyłączyć podział wiersza wielostronicowej tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz zastosować to wyłączenie do tabel w dokumentach programu Word.