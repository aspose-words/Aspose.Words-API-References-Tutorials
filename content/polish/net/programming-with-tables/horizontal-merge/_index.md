---
title: Połączenie poziome
linktitle: Połączenie poziome
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak poziomo scalać komórki w tabeli programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/horizontal-merge/
---

W tym samouczku nauczymy się, jak poziomo scalać komórki tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo łączyć komórki w poziomie w tabelach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Tworzenie dokumentu i inicjowanie generatora dokumentów
Aby rozpocząć przetwarzanie tekstu z tabelą i komórkami, musimy utworzyć nowy dokument i zainicjować generator dokumentów. Wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Utwórz dokument i zainicjuj generator dokumentów
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 3: Budowa tabeli z poziomym łączeniem komórek
Następnie zbudujemy tabelę i zastosujemy poziome scalanie komórek, korzystając z właściwości dostarczonych przez Aspose.Words dla .NET. Użyj następującego kodu:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Ta komórka jest scalona z poprzednią i powinna być pusta.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Tutaj używamy narzędzia do tworzenia dokumentów, aby zbudować tabelę i ustawić właściwości scalania poziomego komórek. Używamy`HorizontalMerge` własność`CellFormat` obiekt, aby określić typ scalania poziomego, który ma zostać zastosowany do każdej komórki. Za pomocą`CellMerge.First` podczas używania łączymy pierwszą komórkę z następną`CellMerge.Previous` łączymy bieżącą komórkę z poprzednią komórką.`CellMerge.None` wskazuje, że komórki nie należy łączyć.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać zmodyfikowany dokument z komórkami scalonymi w poziomie. Użyj następującego kodu:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy dla łączenia poziomego przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Ta komórka jest scalona z poprzednią i powinna być pusta.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Wniosek
tym samouczku nauczyliśmy się, jak poziomo scalać komórki w tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i implementując dostarczony kod C#, można programowo zastosować poziome łączenie komórek w tabelach programu Word. Ta funkcja umożliwia tworzenie bardziej złożonych układów tabel i lepszą organizację danych.