---
title: Rozwiń formatowanie komórek i wierszy ze stylu
linktitle: Rozwiń formatowanie komórek i wierszy ze stylu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący rozszerzania formatowania na komórki i wiersze ze stylu tabeli przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

W tym samouczku przeprowadzimy Cię krok po kroku przez proces rozszerzania formatowania na komórki i wiersze ze stylu przy użyciu Aspose.Words dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak zastosować formatowanie w stylu tabeli do określonych komórek i wierszy w dokumentach programu Word przy użyciu Aspose.Words dla .NET.


## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Tutaj znajduje się Twój dokument Word. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Załaduj istniejący dokument
 Następnie musisz załadować istniejący dokument Word do instancji pliku`Document` klasa.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Krok 3: Przejdź do pierwszej komórki pierwszej tabeli
 Aby rozpocząć, musimy przejść do pierwszej komórki pierwszej tabeli w dokumencie. Używamy`GetChild()`I`FirstRow.FirstCell` metody uzyskania odwołania do pierwszej komórki.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Krok 4: Pokaż początkowe formatowanie komórek
Przed rozwinięciem stylów tabeli wyświetlamy aktualny kolor tła komórki. To powinno być puste, ponieważ bieżące formatowanie jest przechowywane w stylu tabeli.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Krok 5: Rozwiń style tabeli do formatowania bezpośredniego
 Teraz rozszerzamy style tabeli o bezpośrednie formatowanie przy użyciu dokumentu`ExpandTableStylesToDirectFormatting()` metoda.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Krok 6: Pokaż formatowanie komórek po rozwinięciu stylu
Teraz wyświetlamy kolor tła komórki po rozwinięciu stylów tabeli. Ze stylu tabeli należy zastosować niebieski kolor tła.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Przykładowy kod źródłowy dla rozwijania formatowania na komórkach i wierszach ze stylu przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Pobierz pierwszą komórkę pierwszej tabeli w dokumencie.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Najpierw wydrukuj kolor cieniowania komórek.
	// Pole to powinno być puste, ponieważ bieżące cieniowanie jest przechowywane w stylu tabeli.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Teraz wydrukuj cieniowanie komórek po rozwinięciu stylów tabeli.
	// Należy zastosować niebieski kolor wzoru tła ze stylu tabeli.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Wniosek
tym samouczku nauczyliśmy się, jak rozszerzać formatowanie na komórki i wiersze ze stylu tabeli przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz łatwo zastosować formatowanie w stylu tabeli do określonych komórek i wierszy w dokumentach programu Word. Aspose.Words oferuje potężny i elastyczny interfejs API do manipulowania i formatowania tabel w dokumentach. Dzięki tej wiedzy możesz jeszcze bardziej dostosować układ i prezentację dokumentów programu Word.