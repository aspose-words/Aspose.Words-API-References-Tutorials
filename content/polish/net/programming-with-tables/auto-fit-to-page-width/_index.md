---
title: Automatyczne dopasowanie do szerokości strony
linktitle: Automatyczne dopasowanie do szerokości strony
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak automatycznie dopasować tabelę do szerokości strony w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/auto-fit-to-page-width/
---

W tym samouczku nauczymy się, jak używać Aspose.Words dla .NET do automatycznego dopasowania tabeli do szerokości strony w dokumencie Word. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo manipulować tabelami w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Tworzenie i konfiguracja dokumentu
Aby rozpocząć przetwarzanie tekstu z tabelą, musimy utworzyć dokument i skonfigurować generator dokumentów. Wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz dokument i generator dokumentów
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 3: Wstawianie i konfiguracja tabeli
Następnie wstawimy do dokumentu tabelę o szerokości odpowiadającej połowie szerokości strony. Użyj następującego kodu:

```csharp
// Wstaw tabelę i skonfiguruj jej szerokość
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Tutaj używamy narzędzia do tworzenia dokumentów, aby rozpocząć tworzenie tabeli, wstawić komórki i ustawić preferowaną szerokość tabeli na 50% szerokości strony. Następnie dodajemy tekst w każdej komórce.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać zmodyfikowany dokument z tabelą dostosowaną do szerokości strony. Użyj następującego kodu:

```csharp
// Zapisz zmodyfikowany dokument
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.
  
### Przykładowy kod źródłowy funkcji automatycznego dopasowania do szerokości strony przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Wstaw tabelę o szerokości odpowiadającej połowie szerokości strony.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Wniosek
tym samouczku nauczyliśmy się, jak automatycznie dopasować tabelę do szerokości strony w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz programowo manipulować tabelami w dokumentach programu Word. Ta funkcja pozwala na dynamiczne dostosowywanie szerokości tabeli do strony, oferując w ten sposób profesjonalny i atrakcyjny wizualnie dokument.