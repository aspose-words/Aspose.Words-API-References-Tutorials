---
title: Połączenie pionowe
linktitle: Połączenie pionowe
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak łączyć pionowo komórki w tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/vertical-merge/
---

W tym samouczku nauczymy się, jak łączyć w pionie komórki tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł łączyć pionowo komórki w tabelach w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Załaduj dokument
Aby rozpocząć przetwarzanie tekstu w dokumencie, wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz nowy dokument
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 3: Łączenie komórek w pionie
Następnie połączymy komórki w tabeli pionowo. Użyj następującego kodu:

```csharp
// Wstaw komórkę
builder. InsertCell();

// Zastosuj scalanie pionowe do pierwszej komórki
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Wstaw kolejną komórkę
builder. InsertCell();

// Nie stosuj scalania pionowego do komórki
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Wstaw komórkę
builder. InsertCell();

// Zastosuj scalanie pionowe z poprzednią komórką
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Wstaw kolejną komórkę
builder. InsertCell();

// Nie stosuj scalania pionowego do komórki
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Zakończ tworzenie tabeli
builder. EndTable();
```

W tym kodzie używamy konstruktora DocumentBuilder do wstawiania komórek do tabeli. Łączenie pionowe stosujemy do komórek za pomocą właściwości CellFormat.VerticalMerge. Używamy metody CellMerge.First do pierwszego łączenia komórek, CellMerge.Previous do łączenia z poprzednią komórką i CellMerge.None do łączenia w pionie.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać zmodyfikowany dokument z połączonymi komórkami. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy dla łączenia pionowego przy użyciu Aspose.Words dla .NET 
```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Ta komórka jest pionowo scalona z komórką powyżej i powinna być pusta.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak łączyć pionowo komórki w tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz łatwo scalać komórki w pionie w swoich tabelach.