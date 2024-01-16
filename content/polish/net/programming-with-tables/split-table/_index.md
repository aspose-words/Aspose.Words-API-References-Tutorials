---
title: Podziel tabelę
linktitle: Podziel tabelę
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak podzielić tabelę w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/split-table/
---

W tym samouczku nauczymy się, jak podzielić tabelę w dokumencie programu Word za pomocą Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł oddzielić tabelę od określonego wiersza w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Załaduj dokument
Aby rozpocząć przetwarzanie tekstu w dokumencie, wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "Tables.docx");
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów i podać poprawną nazwę pliku.

## Krok 3: Podział stołu
Następnie oddzielimy tabelę od określonego wiersza. Użyj następującego kodu:

```csharp
// Odzyskaj pierwszy stół
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Wyznaczenie linii, od której należy podzielić tabelę
Row row = firstTable.Rows[2];

// Utwórz nowy kontener dla podzielonej tabeli
Table table = (Table)firstTable.Clone(false);

// Wstaw pojemnik po oryginalnym stole
firstTable.ParentNode.InsertAfter(table, firstTable);

// Dodaj akapit buforowy, aby zachować odległość między tabelami
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Przenieś wiersze z tabeli oryginalnej do tabeli podzielonej
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Tutaj używamy dokumentu do pobrania pierwszej tabeli z węzła dokumentu. Następnie określamy wiersz, od którego chcemy podzielić tabelę, w tym przykładzie jest to wiersz trzeci (indeks 2). Następnie tworzymy nowy kontener, klonując oryginalną tabelę, a następnie wstawiamy go po oryginalnej tabeli. Dodajemy także akapit buforowy, aby zachować odległość między dwiema tabelami. Następnie przenosimy wiersze z tabeli oryginalnej do tabeli podzielonej za pomocą pętli „do-while”, aż dotrzemy do określonego wiersza.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać plik

  dokument zmodyfikowany za pomocą podzielonej tabeli. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy dla podzielonej tabeli przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Podzielimy tabelę w trzecim rzędzie (włącznie).
Row row = firstTable.Rows[2];
// Utwórz nowy kontener dla podzielonej tabeli.
Table table = (Table) firstTable.Clone(false);
// Włóż pojemnik po oryginale.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Dodaj akapit buforowy, aby tabele pozostały od siebie oddzielone.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Wniosek
tym samouczku nauczyliśmy się, jak podzielić tabelę w dokumencie programu Word za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz łatwo dzielić tabele od określonej linii w dokumentach Word.