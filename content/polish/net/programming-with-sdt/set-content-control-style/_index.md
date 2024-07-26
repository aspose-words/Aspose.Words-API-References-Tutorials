---
title: Ustaw styl kontroli treści
linktitle: Ustaw styl kontroli treści
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić styl kontroli treści w dokumencie programu Word przy użyciu Aspose.Words dla .NET, stosując spójne formatowanie.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/set-content-control-style/
---

tym samouczku wyjaśniono, jak ustawić styl kontrolki treści w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Do kontrolek zawartości można zastosować wstępnie zdefiniowane lub niestandardowe style, aby zapewnić spójne formatowanie.

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

## Krok 3: Pobierz styl i zastosuj go do kontroli treści
 Pobierz żądany styl z kolekcji stylów dokumentu. W tym przykładzie pobieramy styl „Cytuj” za pomocą`StyleIdentifier.Quote` . Następnie przypisz pobrany styl do pliku`Style` właściwość znacznika dokumentu strukturalnego.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Krok 4: Zapisz dokument
 Zapisz zmodyfikowany dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithSdt.SetContentControlStyle.docx”.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Przykładowy kod źródłowy dla Ustaw styl kontroli treści przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Otóż to! Pomyślnie ustawiłeś styl kontroli treści w dokumencie programu Word przy użyciu Aspose.Words dla .NET.