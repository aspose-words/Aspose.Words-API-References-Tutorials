---
title: Wiele sekcji
linktitle: Wiele sekcji
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak pobierać i przetwarzać wielosekcyjne, strukturalne znaczniki dokumentów w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/multi-section/
---

W tym samouczku wyjaśniono, jak pracować z wielosekcyjnymi znacznikami dokumentów o strukturze strukturalnej w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Możesz pobrać i przetworzyć znaczniki sekcji obecne w dokumencie.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Rozpocznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym znajduje się dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument i pobierz znaczniki wielosekcyjne
 Załaduj dokument Word za pomocą`Document` konstruktor, przekazując ścieżkę do dokumentu jako parametr. Pobierz wszystkie węzły początkowe zakresu znaczników dokumentu strukturalnego w dokumencie za pomocą metody`GetChildNodes` metoda.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Krok 3: Przetwórz znaczniki wielosekcyjne
Wykonaj iterację po kolekcji węzłów początkowych zakresu znaczników dokumentu strukturalnego. W tym przykładzie po prostu drukujemy tytuł każdego tagu na konsoli. Możesz przeprowadzić dalsze przetwarzanie w zależności od swoich wymagań.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Przykładowy kod źródłowy dla wielu sekcji przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Otóż to! Pomyślnie pobrałeś i przetworzyłeś wielosekcyjne znaczniki dokumentu strukturalnego w dokumencie programu Word przy użyciu Aspose.Words dla .NET.