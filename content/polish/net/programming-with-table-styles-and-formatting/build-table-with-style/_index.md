---
title: Zbuduj stół ze stylem
linktitle: Zbuduj stół ze stylem
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący tworzenia tabeli o niestandardowym stylu przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

tym samouczku przeprowadzimy Cię krok po kroku przez proces tworzenia stylizowanej tabeli przy użyciu Aspose.Words dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak utworzyć tabelę z niestandardowym stylem w dokumentach programu Word przy użyciu Aspose.Words dla .NET.

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. To jest lokalizacja, w której chcesz zapisać edytowany dokument programu Word. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Utwórz nowy dokument i narzędzie do tworzenia dokumentów
 Następnie musisz utworzyć nową instancję pliku`Document` class i konstruktor dokumentu dla tego dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Rozpocznij nową tabelę i wstaw komórkę
 Aby rozpocząć budowanie stołu, używamy`StartTable()` metodą konstruktora dokumentów, następnie wstawiamy komórkę do tabeli za pomocą`InsertCell()` metoda.

```csharp
Table table = builder. StartTable();
builder.InsertCell();
```

## Krok 4: Zdefiniuj styl stołu
 Teraz możemy ustawić styl tabeli za pomocą`StyleIdentifier` nieruchomość. W tym przykładzie używamy stylu „MediumShading1Accent1”.

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Krok 5: Zastosuj opcje stylu do tabeli
 Możemy określić, które cechy powinny być sformatowane przez styl za pomocą`StyleOptions`właściwość tablicy. W tym przykładzie zastosowaliśmy następujące opcje: „FirstColumn”, „RowBands” i „FirstRow”.

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Krok 6: Automatycznie dostosuj rozmiar tabeli
 Aby automatycznie dostosować rozmiar tablicy na podstawie jej zawartości, używamy metody`AutoFit()` metoda z`AutoFitBehavior.AutoFitToContents` zachowanie.

```csharp
table.AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Krok 7: Dodaj zawartość do komórek
 Teraz możemy dodawać zawartość do komórek za pomocą metody`Writeln()`I`InsertCell()` metody konstruktora dokumentów. W tym przykładzie dodajemy nagłówki „Item” i „Ilość (

kg)” i odpowiednie dane.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writen("Quantity (kg)");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writen("40");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();
```

## Krok 8: Zapisz zmodyfikowany dokument
Na koniec zapisujemy zmodyfikowany dokument do pliku. Możesz wybrać odpowiednią nazwę i lokalizację dokumentu wyjściowego.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Gratulacje! Utworzyłeś teraz niestandardową tabelę przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla kompilacji tabeli ze stylem przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
// Przed ustawieniem formatowania tabeli musimy najpierw wstawić co najmniej jeden wiersz.
builder.InsertCell();
// Ustaw używany styl tabeli w oparciu o unikalny identyfikator stylu.
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
// Zastosuj, które elementy powinny być sformatowane według stylu.
table.StyleOptions =
	TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
table.AutoFit(AutoFitBehavior.AutoFitToContents);
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writeln("Quantity (kg)");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writeln("40");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Wniosek
tym samouczku nauczyliśmy się, jak budować stylizowaną tabelę za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz łatwo dostosować styl tabel w dokumentach programu Word. Aspose.Words oferuje potężny i elastyczny interfejs API do manipulowania i formatowania tabel w dokumentach. Dzięki tej wiedzy możesz ulepszyć wizualną prezentację dokumentów Word i spełnić określone potrzeby.