---
title: Uzyskaj odległość między tekstem otaczającym tabelę
linktitle: Uzyskaj odległość między tekstem otaczającym tabelę
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku, jak uzyskać odległość między tekstem a tabelą w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

tym samouczku przeprowadzimy Cię krok po kroku przez proces obliczania odległości pomiędzy otaczającym tekstem w tabeli za pomocą Aspose.Words dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak uzyskać dostęp do różnych odległości między tabelą a otaczającym tekstem w dokumentach programu Word za pomocą Aspose.Words dla .NET.

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

## Krok 3: Uzyskaj odległość między tabelą a otaczającym ją tekstem
 Aby uzyskać odległość między tabelą a otaczającym ją tekstem, musimy uzyskać dostęp do tabeli w dokumencie za pomocą`GetChild()` metoda i`NodeType.Table` nieruchomość. Możemy następnie wyświetlić różne odległości, korzystając z właściwości tablicy`DistanceTop`, `DistanceBottom`, `DistanceRight`I`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Przykładowy kod źródłowy funkcji Uzyskaj odległość między tekstem otaczającym tabelę przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Wniosek
tym samouczku nauczyliśmy się, jak uzyskać odległość pomiędzy otaczającym tekstem w tabeli za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz łatwo uzyskać dostęp do różnych odległości między tabelą a otaczającym ją tekstem w dokumentach programu Word. Aspose.Words oferuje potężny i elastyczny interfejs API do manipulowania i formatowania tabel w dokumentach. Dzięki tej wiedzy możesz analizować układ swoich tabel w odniesieniu do tekstu i spełniać konkretne potrzeby.