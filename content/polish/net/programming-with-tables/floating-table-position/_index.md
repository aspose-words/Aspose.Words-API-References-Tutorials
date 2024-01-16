---
title: Pozycja stołu pływającego
linktitle: Pozycja stołu pływającego
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić tabelę w pozycji pływającej w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/floating-table-position/
---

W tym samouczku nauczymy się, jak używać Aspose.Words dla .NET do ustawiania tabeli w pozycji pływającej w dokumencie programu Word. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo kontrolować położenie i wyrównanie tabel pływających w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Załadowanie dokumentu i dostęp do tabeli
Aby rozpocząć przetwarzanie tekstu z tabelą, musimy załadować dokument, który ją zawiera i uzyskać do niej dostęp. Wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Dostęp do tablicy
Table table = doc.FirstSection.Body.Tables[0];
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów. Upewnij się także, że dokument zawiera tabelę, która będzie ustawiona w pozycji pływającej.

## Krok 3: Ustawianie pływającej deski
Następnie ustawimy tabelę w pozycji pływającej, korzystając z właściwości dostarczonych przez Aspose.Words dla .NET. Użyj następującego kodu:

```csharp
// Ustawianie pływającego stołu
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Tutaj używamy`AbsoluteHorizontalDistance` właściwość ustawiająca bezwzględną poziomą odległość tabeli od lewej krawędzi strony. Używamy również`RelativeVerticalAlignment` właściwość, aby ustawić względne wyrównanie tabeli w pionie względem otaczającej zawartości.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać zmodyfikowany dokument z tabelą ustawioną w pozycji pływającej. Użyj następującego kodu:

```csharp
// Zapisz zmodyfikowany dokument
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy dla pozycji tabeli pływającej przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Wniosek
tym samouczku nauczyliśmy się, jak ustawić tabelę w pozycji pływającej w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz programowo kontrolować położenie i wyrównanie tabel pływających w dokumentach programu Word.