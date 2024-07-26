---
title: Kontrola zawartości sformatowanego pola tekstowego
linktitle: Kontrola zawartości sformatowanego pola tekstowego
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć kontrolkę zawartości pola tekstowego w dokumencie programu Word przy użyciu Aspose.Words dla .NET, umożliwiającego formatowanie i stylizację tekstu.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/rich-text-box-content-control/
---

W tym samouczku pokazano, jak utworzyć kontrolkę zawartości pola tekstowego w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Elementy sterujące zawartością sformatowanych pól tekstowych umożliwiają użytkownikom wprowadzanie i formatowanie tekstu przy użyciu różnych stylów i opcji formatowania.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Zacznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz dokument i tag StructuredDocumentTag
 Utwórz nową instancję`Document` klasa i A`StructuredDocumentTag` reprezentujący kontrolę zawartości pola tekstu sformatowanego. Sprecyzować`SdtType.RichText` jako typ i`MarkupLevel.Block` jako poziom znaczników, aby utworzyć pole tekstu sformatowanego na poziomie bloku.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Krok 3: Utwórz i sformatuj treść w formacie Rich Text
Utwórz akapit i uruchom, aby przedstawić treść tekstu sformatowanego. Ustaw opcje tekstu i formatowania, takie jak kolor, czcionka itp.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Krok 4: Dodaj zawartość tekstu sformatowanego do kontroli zawartości
 Dodaj akapit z zawartością tekstu sformatowanego do pliku`ChildNodes` kolekcja kontrolki zawartości pola tekstu sformatowanego.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Krok 5: Dołącz kontrolę zawartości do dokumentu
 Dołącz formant zawartości pola tekstu sformatowanego do treści dokumentu za pomocą`AppendChild` metoda treści pierwszej sekcji dokumentu.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Krok 6: Zapisz dokument
 Zapisz dokument w określonym katalogu za pomocą`Save`metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithSdt.RichTextBoxContentControl.docx”.

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Przykładowy kod źródłowy kontroli zawartości sformatowanych pól tekstowych przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

Otóż to! Pomyślnie utworzyłeś kontrolkę zawartości pola tekstu sformatowanego w dokumencie programu Word przy użyciu Aspose.Words dla .NET.