---
title: Kontrola zawartości pola kombi
linktitle: Kontrola zawartości pola kombi
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć kontrolę zawartości pola kombi w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/combo-box-content-control/
---

W tym samouczku wyjaśniono, jak utworzyć kontrolkę zawartości pola kombi w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Elementy sterujące zawartością pola kombi umożliwiają użytkownikom wybranie elementu z listy rozwijanej.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Rozpocznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz dokument i tag StructuredDocumentTag
 Utwórz nową instancję`Document` klasa i A`StructuredDocumentTag` reprezentujący kontrolę zawartości pola kombi. Sprecyzować`SdtType.ComboBox` jako typ i`MarkupLevel.Block` jako poziom znaczników, aby utworzyć pole kombi na poziomie bloku.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Krok 3: Dodaj elementy do pola kombi
 Dodaj elementy do pola kombi za pomocą`ListItems` własność`StructuredDocumentTag` . Każdy element jest reprezentowany przez`SdtListItem` obiekt, który pobiera wyświetlany tekst i wartość. W tym przykładzie dodajemy trzy elementy do pola kombi.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Krok 4: Dołącz tag StructuredDocumentTag do dokumentu
 Dołącz kontrolę zawartości pola kombi do treści dokumentu za pomocą`AppendChild` metoda treści pierwszej sekcji dokumentu.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Krok 5: Zapisz dokument
 Zapisz dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithSdt.ComboBoxContentControl.docx”.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Przykładowy kod źródłowy kontroli zawartości Combo Box przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

Otóż to! Pomyślnie utworzyłeś kontrolę zawartości pola kombi w dokumencie programu Word przy użyciu Aspose.Words dla .NET.