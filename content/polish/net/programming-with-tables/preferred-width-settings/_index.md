---
title: Preferowane ustawienia szerokości
linktitle: Preferowane ustawienia szerokości
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić preferowaną szerokość komórek tabeli w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/preferred-width-settings/
---

W tym samouczku dowiemy się, jak ustawić preferowane ustawienia szerokości komórek tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł określić różne preferowane szerokości komórek tabeli w dokumentach programu Word.

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

## Krok 3: Budowa stołu o preferowanych szerokościach
Następnie zbudujemy tabelę z trzema komórkami o różnych preferowanych szerokościach. Użyj następującego kodu:

```csharp
// Początek stołu
builder. StartTable();

// Wstaw komórkę o rozmiarze bezwzględnym
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Wstaw komórkę o względnym rozmiarze (w procentach)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Wstaw komórkę o rozmiarze automatycznym
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Koniec stołu
builder. EndTable();
```

Tutaj używamy narzędzia do tworzenia dokumentów, aby zbudować tabelę z trzema komórkami. Pierwsza komórka ma preferowaną szerokość 40 punktów, druga komórka ma preferowaną szerokość 20% szerokości tabeli, a trzecia komórka ma automatycznie preferowaną szerokość, która dostosowuje się

  w zależności od dostępnej przestrzeni.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać zmodyfikowany dokument z preferowanymi ustawieniami szerokości zdefiniowanymi dla komórek tabeli. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy dla ustawień preferowanej szerokości przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Wstaw wiersz tabeli składający się z trzech komórek o różnych preferowanych szerokościach.
	builder.StartTable();
	// Wstaw komórkę o rozmiarze bezwzględnym.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Wstaw komórkę o względnym (procentowym) rozmiarze.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Wstaw komórkę o rozmiarze automatycznym.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak ustawić preferowane ustawienia szerokości komórek tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz dostosować szerokość komórek tabeli do swoich konkretnych potrzeb w dokumentach programu Word.