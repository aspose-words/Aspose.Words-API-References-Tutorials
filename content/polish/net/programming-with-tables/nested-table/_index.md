---
title: Zagnieżdżony stół
linktitle: Zagnieżdżony stół
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć zagnieżdżoną tabelę w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/nested-table/
---

W tym samouczku dowiemy się, jak utworzyć zagnieżdżoną tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo tworzyć zagnieżdżone tabele w dokumentach programu Word.

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

## Krok 3: Tworzenie tabeli zagnieżdżonej
Następnie zbudujemy zagnieżdżoną tabelę, wstawiając komórki do tabeli zewnętrznej i tworząc nową tabelę w pierwszej komórce. Użyj następującego kodu:

```csharp
// Wstaw pierwszą komórkę tabeli zewnętrznej
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Wstaw drugą komórkę tabeli zewnętrznej
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Zakończenie stołu zewnętrznego
builder. EndTable();

// Przejdź do pierwszej komórki tabeli zewnętrznej
builder.MoveTo(cell.FirstParagraph);

// Zbuduj wewnętrzny stół
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Koniec stołu wewnętrznego
builder. EndTable();
```

Tutaj używamy narzędzia do tworzenia dokumentów, aby wstawić komórki i zawartość do tabeli zewnętrznej. Następnie przesuwamy kursor konstruktora dokumentów do pierwszej komórki tabeli zewnętrznej i budujemy wewnątrz nową tabelę, wstawiając komórki i treść.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać zmodyfikowany dokument z zagnieżdżoną tabelą. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy tabeli zagnieżdżonej przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// To wywołanie jest ważne, aby utworzyć zagnieżdżoną tabelę w pierwszej tabeli.
	// Bez tego wywołania komórki wstawione poniżej zostaną dołączone do tabeli zewnętrznej.
	builder.EndTable();
	// Przejdź do pierwszej komórki tabeli zewnętrznej.
	builder.MoveTo(cell.FirstParagraph);
	// Zbuduj wewnętrzny stół.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak utworzyć zagnieżdżoną tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i implementując dostarczony kod C#, możesz programowo tworzyć w dokumentach programu Word zagnieżdżone tabele zgodnie ze swoimi konkretnymi potrzebami.
