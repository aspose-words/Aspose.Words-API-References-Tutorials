---
title: Ustaw ustawienia strony i formatowanie sekcji
linktitle: Ustaw ustawienia strony i formatowanie sekcji
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący konfigurowania układu dokumentu i formatowania sekcji za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby skonfigurować układ i formatowanie sekcji za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia ustawienie orientacji strony, marginesów i rozmiaru papieru.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Tworzenie dokumentu

Na tym etapie utworzymy nowy dokument. Użyj poniższego kodu, aby utworzyć dokument i zainicjować konstruktor:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu, w którym chcesz zapisać dokument.

## Krok 3: Konfiguracja układu i zapisanie dokumentu

Teraz skonfigurujmy układ dokumentu. Użyj poniższego kodu, aby ustawić orientację, marginesy i rozmiar papieru:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Ten kod ustawi orientację strony na poziomą, lewy margines na 50, a rozmiar papieru na 10x14.

### Przykładowy kod źródłowy dla ustawiania ustawień strony i formatowania sekcji przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

 Pamiętaj o podaniu prawidłowej ścieżki do katalogu, w którym chcesz zapisać dokument w formacie`dataDir` zmienny.

Nauczyłeś się teraz, jak skonfigurować układ i formatowanie sekcji dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo dostosować układ i formatowanie własnych dokumentów.