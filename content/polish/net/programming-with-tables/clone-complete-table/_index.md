---
title: Klonuj kompletny stół
linktitle: Klonuj kompletny stół
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak sklonować całą tabelę do dokumentu programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/clone-complete-table/
---

W tym samouczku dowiemy się, jak używać Aspose.Words dla .NET do klonowania całej tabeli do dokumentu programu Word. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo klonować tabele do dokumentów programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Załadowanie dokumentu i dostęp do tabeli
Aby rozpocząć przetwarzanie tekstu z tabelą, musimy załadować dokument, który ją zawiera i uzyskać do niej dostęp. Wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "Tables.docx");

// Dostęp do tablicy
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 3: Klon pełnej macierzy
Następnie sklonujemy całą tabelę i wstawimy ją do dokumentu po oryginale. Użyj następującego kodu:

```csharp
// Sklonuj tablicę
Table tableClone = (Table)table.Clone(true);

// Wstaw sklonowaną tabelę do dokumentu po oryginale
table.ParentNode.InsertAfter(tableClone, table);

// Wstaw pusty akapit pomiędzy dwiema tabelami
// W przeciwnym razie zostaną one połączone w jeden przy zapisie (wynika to z walidacji dokumentu)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Tutaj używamy`Clone` metoda tworzenia pełnej kopii tablicy. Następnie używamy`InsertAfter` aby wstawić sklonowaną tabelę do dokumentu po oryginalnej tabeli. Dodajemy również pusty akapit pomiędzy dwiema tabelami, aby zapobiec ich łączeniu podczas zapisywania.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać zmodyfikowany dokument ze sklonowaną tabelą. Użyj następującego kodu:

```csharp
// Zapisz zmodyfikowany dokument
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.
  
### Przykładowy kod źródłowy Clone Complete Table przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Sklonuj tabelę i wstaw ją do dokumentu po oryginale.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Wstaw pusty akapit pomiędzy dwiema tabelami,
	// w przeciwnym razie po zapisaniu zostaną połączone w jeden. Ma to związek z walidacją dokumentu.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak sklonować całą tabelę do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz programowo klonować tabele w dokumentach programu Word. Ta funkcja umożliwia wykonywanie zaawansowanych manipulacji na tablicach w celu dostosowania ich do konkretnych potrzeb.