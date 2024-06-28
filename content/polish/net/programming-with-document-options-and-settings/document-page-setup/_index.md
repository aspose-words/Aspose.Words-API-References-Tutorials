---
title: Konfiguracja strony dokumentu
linktitle: Konfiguracja strony dokumentu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący konfigurowania układu dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-options-and-settings/document-page-setup/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby skonfigurować układ dokumentu za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia ustawienie trybu układu, liczby znaków w wierszu i liczby wierszy na stronie.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument Word, który chcemy skonfigurować. Aby załadować dokument, użyj poniższego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu, w którym znajduje się dokument.

## Krok 3: Konfiguracja układu

Teraz skonfigurujmy układ dokumentu. Użyj poniższego kodu, aby ustawić tryb układu, liczbę znaków w wierszu i liczbę wierszy na stronie:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Ten kod ustawia tryb układu na „Siatka”, a następnie określa liczbę znaków w wierszu i liczbę wierszy na stronie.

### Przykładowy kod źródłowy dla konfiguracji strony dokumentu przy użyciu Aspose.Words dla .NET


```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Ustaw tryb układu sekcji, pozwalający na zdefiniowanie zachowania siatki dokumentu.
	// Należy pamiętać, że zakładka Siatka dokumentu staje się widoczna w oknie dialogowym Ustawienia strony programu MS Word.
	// jeśli jakikolwiek język azjatycki jest zdefiniowany jako język edycji.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Pamiętaj, aby określić poprawną ścieżkę dokumentu w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak skonfigurować układ dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo dostosować układ własnych dokumentów.