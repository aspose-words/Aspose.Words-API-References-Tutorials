---
title: Wyczyść kontrolę zawartości
linktitle: Wyczyść kontrolę zawartości
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wyczyścić zawartość kontrolki w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/clear-contents-control/
---

W tym samouczku pokazano, jak wyczyścić zawartość SDT w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Wyczyszczenie zawartości zestawu SDT powoduje usunięcie dowolnego tekstu lub węzłów podrzędnych w ramach kontroli zawartości.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Zacznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym znajduje się dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument i pobierz tag StructuredDocumentTag
 Załaduj dokument Word za pomocą`Document` konstruktor, przekazując ścieżkę do dokumentu jako parametr. Następnie pobierz żądane`StructuredDocumentTag` z dokumentu. W tym przykładzie zakładamy, że SDT jest pierwszym węzłem podrzędnym w dokumencie.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Krok 3: Wyczyść zawartość StructuredDocumentTag
 Wyczyść zawartość SDT za pomocą`Clear` metoda. Spowoduje to usunięcie wszystkich węzłów tekstowych lub podrzędnych w ramach kontroli zawartości.

```csharp
sdt.Clear();
```

## Krok 4: Zapisz dokument
 Zapisz zmodyfikowany dokument za pomocą`Save`metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithSdt.ClearContentsControl.doc”.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Przykładowy kod źródłowy dla Clear Contents Control przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Otóż to! Pomyślnie wyczyściłeś zawartość StructuredDocumentTag w dokumencie programu Word przy użyciu Aspose.Words dla .NET.