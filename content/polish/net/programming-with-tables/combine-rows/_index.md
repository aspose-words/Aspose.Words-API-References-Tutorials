---
title: Połącz rzędy
linktitle: Połącz rzędy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak łączyć wiersze tabeli w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/combine-rows/
---

W tym samouczku dowiemy się, jak używać Aspose.Words dla .NET do łączenia wierszy tabel w dokumencie programu Word. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo manipulować i łączyć wiersze tabeli w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Ładowanie dokumentu i uzyskiwanie dostępu do tabel
Aby rozpocząć przetwarzanie tekstu z tabelami, musimy załadować dokument, który je zawiera i uzyskać do nich dostęp. Wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "Tables.docx");

// Dostęp do tabel
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 3: Łączenie wierszy tabeli
Następnie połączymy wiersze drugiej tabeli z końcem pierwszej tabeli. Użyj następującego kodu:

```csharp
// Kombinacja wierszy tabeli
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Tutaj używamy a`while` pętla, aby iterować po wszystkich wierszach drugiej tablicy i dodać je na końcu pierwszej tablicy za pomocą`Add` metoda. Następnie usuwamy drugą tabelę z dokumentu za pomocą`Remove` metoda.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać zmodyfikowany dokument z połączonymi wierszami tabeli. Użyj następującego kodu:

```csharp
// Zapisz zmodyfikowany dokument
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy dla Combine Rows przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Wiersze z drugiej tabeli zostaną dodane na końcu pierwszej tabeli.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Dołącz wszystkie wiersze z bieżącej tabeli do następnych tabel
	// o różnej liczbie komórek i szerokościach można połączyć w jedną tabelę.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Wniosek
tym samouczku nauczyliśmy się łączyć wiersze tabel w dokumencie programu Word za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz programowo manipulować wierszami tabeli w dokumentach programu Word. Ta funkcja umożliwia efektywne scalanie i porządkowanie danych w tabeli.