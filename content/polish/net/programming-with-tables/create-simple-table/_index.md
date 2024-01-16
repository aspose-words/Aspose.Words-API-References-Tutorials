---
title: Utwórz prostą tabelę
linktitle: Utwórz prostą tabelę
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć prostą tabelę w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/create-simple-table/
---

W tym samouczku nauczymy się, jak utworzyć prostą tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo tworzyć niestandardowe tabele w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Tworzenie dokumentu i inicjalizacja generatora dokumentów
Aby rozpocząć budowanie tabeli, musimy utworzyć nowy dokument i zainicjować kreator dokumentów. Wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz dokument i zainicjuj generator dokumentów
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 3: Budowanie tablicy
Następnie zbudujemy tabelę, korzystając z metod dostarczonych przez narzędzie do tworzenia dokumentów. Użyj następującego kodu:

```csharp
// Rozpocznij budowę tablicy
builder. StartTable();

// Budowa pierwszej komórki pierwszego rzędu
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Budowa drugiej celi pierwszego rzędu
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//Wywołaj następującą metodę, aby zakończyć pierwszą linię i rozpocząć nową
builder. EndRow();

// Budowa pierwszej komórki drugiego rzędu
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Budowa drugiej celi drugiego rzędu
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Wywołaj następną metodę, aby zakończyć drugą linię
builder. EndRow();

// Wskazanie, że konstrukcja stołu została ukończona
builder. EndTable();
```

 Tutaj używamy narzędzia do tworzenia dokumentów, aby krok po kroku zbudować tabelę. Zaczynamy od dzwonienia`StartTable()` aby zainicjować tabelę, a następnie użyj`InsertCell()` aby wstawić komórki i`Write()` aby dodać zawartość do każdej komórki. Używamy również`EndRow()` aby zakończyć wiersz i rozpocząć nowy. Wreszcie dzwonimy`EndTable()` aby wskazać, że konstrukcja stołu została ukończona.

## Krok 4: Zapisz dokument
Na koniec musimy oszczędzać

  dokument z utworzoną tabelą. Użyj następującego kodu:

```csharp
// Zapisz dokument
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy narzędzia Utwórz prostą tabelę przy użyciu Aspose.Words dla platformy .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Zacznij budować stół.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Zbuduj drugą komórkę.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Wywołaj następującą metodę, aby zakończyć wiersz i rozpocząć nowy wiersz.
	builder.EndRow();
	// Zbuduj pierwszą komórkę drugiego rzędu.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Zbuduj drugą komórkę.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//Sygnał, że zakończyliśmy budowę stołu.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak utworzyć prostą tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz programowo tworzyć niestandardowe tabele w dokumentach programu Word. Ta funkcja umożliwia formatowanie i organizowanie danych w uporządkowany i przejrzysty sposób.