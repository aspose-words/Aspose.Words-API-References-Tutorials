---
title: Powtórz wiersze na kolejnych stronach
linktitle: Powtórz wiersze na kolejnych stronach
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak powtarzać wiersze tabeli na kolejnych stronach dokumentu programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

tym samouczku nauczymy się, jak powtarzać wiersze tabeli na kolejnych stronach dokumentu Worda za pomocą Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł określić wiersze, które mają się powtarzać na kolejnych stronach tabeli w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Tworzenie dokumentu i inicjowanie generatora dokumentów
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

## Krok 3: Budowanie tabeli z powtarzającymi się wierszami
Następnie zbudujemy tabelę z powtarzającymi się wierszami na kolejnych stronach. Użyj następującego kodu:

```csharp
// Początek stołu
builder. StartTable();

// Konfiguracja parametrów pierwszej linii (linii nagłówka)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Wstaw pierwszą komórkę pierwszego wiersza
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Wstaw drugą komórkę pierwszego wiersza
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Skonfiguruj parametry poniższych linii
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Pętla, aby wstawić komórki w kolejnych wierszach
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Koniec stołu
builder. EndTable();
```

 Tutaj używamy narzędzia do tworzenia dokumentów, aby zbudować tabelę z dwoma wierszami nagłówków i wieloma wierszami danych. The`RowFormat.HeadingFormat` Parametry służą do oznaczania wierszy nagłówka, które należy powtórzyć na kolejnych stronach.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Wreszcie USA

  należy zapisać zmodyfikowany dokument z powtarzającymi się wierszami nagłówka na kolejnych stronach tabeli. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy dla powtarzania wierszy na kolejnych stronach przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak powtarzać wiersze tabeli na kolejnych stronach dokumentu programu Word za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz określić, które wiersze mają się powtarzać zgodnie z Twoimi konkretnymi potrzebami w dokumentach programu Word.