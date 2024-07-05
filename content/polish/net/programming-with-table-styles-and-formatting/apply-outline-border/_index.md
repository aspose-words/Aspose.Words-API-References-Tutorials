---
title: Zastosuj obramowanie konturu
linktitle: Zastosuj obramowanie konturu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący stosowania obramowania tabeli przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

tym samouczku przeprowadzimy Cię krok po kroku przez proces zastosowania obramowania konturowego do tabeli za pomocą Aspose.Words dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz dobrze rozumiał, jak manipulować obramowaniami tabel w dokumentach programu Word za pomocą Aspose.Words dla .NET.

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Tutaj przechowywany jest dokument programu Word. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Prześlij dokument
 Następnie musisz załadować dokument Word do instancji pliku`Document` klasa.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Krok 3: Uzyskaj dostęp do tabeli
 Aby zastosować obramowanie konturowe, musimy uzyskać dostęp do tabeli w dokumencie. The`Table` klasa reprezentuje tabelę w Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Krok 4: Wyrównaj tabelę do środka strony
 Teraz możemy wyrównać tabelę do środka strony za pomocą`Alignment` właściwość tabeli.

```csharp
table. Alignment = Table Alignment. Center;
```

## Krok 5: Usuń istniejące obramowania tabeli
Aby rozpocząć od nowego obramowania konturowego, musimy najpierw usunąć wszystkie istniejące obramowania z tabeli. Można tego dokonać za pomocą`ClearBorders()` metoda.

```csharp
table. ClearBorders();
```

## Krok 6: Zdefiniuj zieloną ramkę wokół stołu
 Możemy teraz ustawić zieloną ramkę wokół stołu za pomocą`SetBorder()` metoda dla każdej strony stołu. W tym przykładzie używamy ramki typu „Single” o grubości 1,5 punktu i kolorze zielonym.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Krok 7: Wypełnij komórki kolorem tła
Aby poprawić wizualną prezentację tabeli, możemy wypełnić komórki mielonym kolorem tła

pomysł. W tym przykładzie używamy jasnozielonego koloru.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Krok 8: Zapisz zmodyfikowany dokument
Na koniec zapisujemy zmodyfikowany dokument do pliku. Możesz wybrać odpowiednią nazwę i lokalizację dokumentu wyjściowego.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Gratulacje! Zastosowałeś teraz obramowanie do tabeli przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy aplikacji Apply Outline Border przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Wyrównaj tabelę do środka strony.
	table.Alignment = TableAlignment.Center;
	//Usuń wszystkie istniejące obramowania ze stołu.
	table.ClearBorders();
	// Ustaw zieloną ramkę wokół stołu, ale nie wewnątrz.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Wypełnij komórki jasnozielonym jednolitym kolorem.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak zastosować obramowanie tabeli za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz łatwo zintegrować tę funkcjonalność ze swoimi projektami C#. Manipulowanie formatowaniem tabeli jest istotnym aspektem przetwarzania dokumentów, a Aspose.Words oferuje potężny i elastyczny interfejs API, który pozwala to osiągnąć. Dzięki tej wiedzy możesz poprawić wizualną prezentację dokumentów Word i spełnić określone wymagania.