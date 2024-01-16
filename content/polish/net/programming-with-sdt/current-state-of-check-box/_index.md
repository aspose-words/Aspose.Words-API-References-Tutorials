---
title: Bieżący stan pola wyboru
linktitle: Bieżący stan pola wyboru
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak pobrać i ustawić bieżący stan kontroli zawartości pola wyboru w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/current-state-of-check-box/
---

W tym samouczku wyjaśniono, jak pobrać i ustawić bieżący stan kontroli zawartości pola wyboru w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Możesz zaznaczyć lub odznaczyć pole wyboru w zależności od jego bieżącego stanu.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Zacznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym znajduje się dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument i pobierz kontrolę zawartości pola wyboru
 Załaduj dokument Word za pomocą`Document` konstruktor, przekazując ścieżkę do dokumentu jako parametr. Następnie pobierz żądaną kontrolę zawartości pola wyboru z dokumentu. W tym przykładzie zakładamy, że pole wyboru jest pierwszym znacznikiem dokumentu strukturalnego w dokumencie.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Krok 3: Zaznacz lub odznacz pole wyboru w zależności od jego bieżącego stanu
 Sprawdź, czy pobrany znacznik dokumentu strukturalnego jest typu`SdtType.Checkbox` . Jeśli tak, ustaw`Checked` właściwość kontroli zawartości do`true` aby zaznaczyć pole. W przeciwnym razie możesz pozostawić to niezaznaczone.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Krok 4: Zapisz dokument
 Zapisz zmodyfikowany dokument w określonym katalogu za pomocą`Save`metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithSdt.CurrentStateOfCheckBox.docx”.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Przykładowy kod źródłowy bieżącego stanu pola wyboru przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Pobierz pierwszą kontrolę zawartości z dokumentu.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Otóż to! Pomyślnie pobrałeś i ustawiłeś bieżący stan kontroli zawartości pola wyboru w dokumencie programu Word przy użyciu Aspose.Words dla .NET.