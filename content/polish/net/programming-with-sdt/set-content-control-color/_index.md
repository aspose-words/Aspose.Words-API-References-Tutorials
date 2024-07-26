---
title: Ustaw kolor kontroli zawartości
linktitle: Ustaw kolor kontroli zawartości
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić kolor kontrolki treści w dokumencie programu Word za pomocą Aspose.Words dla .NET, dostosowując jej wygląd.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/set-content-control-color/
---

W tym samouczku wyjaśniono, jak ustawić kolor kontrolki zawartości w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Możesz dostosować wygląd elementów sterujących zawartością, zmieniając ich kolor.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Zacznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym znajduje się dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument i odzyskaj kontrolę zawartości
 Załaduj dokument Word za pomocą`Document`konstruktor, przekazując ścieżkę do dokumentu jako parametr. Pobierz żądaną kontrolę zawartości z dokumentu. W tym przykładzie zakładamy, że kontrola treści jest pierwszym strukturalnym znacznikiem dokumentu w dokumencie.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Krok 3: Ustaw kolor kontroli zawartości
 Ustaw kolor kontrolki zawartości, przypisując a`Color` wartość do`Color` właściwość znacznika dokumentu strukturalnego. W tym przykładzie ustawiliśmy kolor na czerwony.

```csharp
sdt.Color = Color.Red;
```

## Krok 4: Zapisz dokument
 Zapisz zmodyfikowany dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithSdt.SetContentControlColor.docx”.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Przykładowy kod źródłowy dla Ustaw kolor kontroli zawartości przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Otóż to! Pomyślnie ustawiłeś kolor kontrolki treści w dokumencie programu Word przy użyciu Aspose.Words dla .NET.