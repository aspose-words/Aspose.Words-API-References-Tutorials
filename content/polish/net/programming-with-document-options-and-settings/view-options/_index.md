---
title: Wyświetl opcje
linktitle: Wyświetl opcje
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący konfigurowania opcji wyświetlania dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-options-and-settings/view-options/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby skonfigurować opcje wyświetlania w Aspose.Words dla .NET. Ta funkcja umożliwia dostosowanie trybu widoku i poziomu powiększenia dokumentu.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument Word, dla którego chcemy skonfigurować opcje wyświetlania. Aby załadować dokument, użyj poniższego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu, w którym znajduje się dokument.

## Krok 3: Konfiguracja opcji wyświetlania

Teraz skonfigurujemy opcje wyświetlania dokumentu. Użyj poniższego kodu, aby ustawić tryb wyświetlania i poziom powiększenia:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Ten kod ustawia tryb widoku na „PageLayout”, a poziom powiększenia na 50%.

### Przykładowy kod źródłowy opcji widoku przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Pamiętaj, aby określić poprawną ścieżkę dokumentu w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak konfigurować opcje wyświetlania dokumentu przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo dostosować sposób wyświetlania własnych dokumentów.