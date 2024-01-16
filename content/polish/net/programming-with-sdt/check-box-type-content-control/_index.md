---
title: Pole wyboru Kontrola zawartości typu
linktitle: Pole wyboru Kontrola zawartości typu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć kontrolę zawartości typu pola wyboru w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/check-box-type-content-control/
---

W tym samouczku wyjaśniono, jak utworzyć kontrolę zawartości typu pola wyboru w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Elementy sterujące zawartością pola wyboru umożliwiają użytkownikom zaznaczanie lub czyszczenie pola wyboru w dokumencie.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Zacznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz dokument i narzędzie do tworzenia dokumentów
 Utwórz nową instancję`Document` klasa i A`DocumentBuilder` do zbudowania treści dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Dodaj kontrolę zawartości typu pola wyboru
 Stwórz`StructuredDocumentTag` z`SdtType.Checkbox` reprezentujący kontrolę zawartości pola wyboru. Sprecyzować`MarkupLevel.Inline` umieścić go w tekście.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Krok 4: Zapisz dokument
 Zapisz dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithSdt.CheckBoxTypeContentControl.docx”.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Przykładowy kod źródłowy kontroli zawartości typu pola wyboru przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Otóż to! Pomyślnie utworzyłeś kontrolę zawartości typu pola wyboru w dokumencie programu Word przy użyciu Aspose.Words dla .NET.