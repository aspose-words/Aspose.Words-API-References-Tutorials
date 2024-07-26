---
title: Konwertuj na poziomo połączone komórki
linktitle: Konwertuj na poziomo połączone komórki
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak konwertować komórki tabeli na komórki scalone poziomo w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

tym samouczku dowiemy się, jak używać Aspose.Words dla .NET do konwertowania komórek tabeli na komórki scalone poziomo w dokumencie programu Word. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo manipulować komórkami tabeli w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Załadowanie dokumentu i dostęp do tabeli
Aby rozpocząć przetwarzanie tekstu z tabelą, musimy załadować dokument, który ją zawiera i uzyskać do niej dostęp. Wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Dostęp do tablicy
Table table = doc.FirstSection.Body.Tables[0];
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów. Upewnij się także, że dokument zawiera tabelę z poziomo połączonymi komórkami.

## Krok 3: Konwertuj na komórki scalone poziomo
 Następnie przekonwertujemy komórki tabeli na komórki scalone poziomo za pomocą`ConvertToHorizontallyMergedCells()` metoda. Użyj następującego kodu:

```csharp
// Konwertuj na komórki scalone poziomo
table. ConvertToHorizontallyMergedCells();
```

 Tutaj po prostu nazywamy`ConvertToHorizontallyMergedCells()` metodę w tablicy, aby przeprowadzić konwersję.

### Przykładowy kod źródłowy funkcji Konwertuj na poziomo połączone komórki przy użyciu Aspose.Words dla platformy .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Teraz scalone komórki mają odpowiednie flagi scalania.
	table.ConvertToHorizontallyMergedCells();
```

## Wniosek
tym samouczku nauczyliśmy się, jak konwertować komórki tabeli na komórki scalone poziomo w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz programowo manipulować komórkami tabeli w dokumentach programu Word. Ta funkcja pozwala zarządzać danymi i organizować je w elastyczny i spersonalizowany sposób w formie tabeli.