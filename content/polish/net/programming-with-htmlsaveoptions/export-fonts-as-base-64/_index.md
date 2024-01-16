---
title: Eksportuj czcionki jako Base 64
linktitle: Eksportuj czcionki jako Base 64
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący eksportowania czcionek bazowych 64 podczas zapisywania dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby wyeksportować czcionki Base 64 za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia eksport czcionek jako dane Base 64 podczas zapisywania dokumentu w formacie HTML.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument do eksportu. Użyj poniższego kodu, aby załadować dokument z określonego katalogu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Ten kod tworzy instancję`Document` poprzez załadowanie dokumentu z określonego katalogu.

## Krok 3: Konfiguracja opcji tworzenia kopii zapasowych HTML

Teraz skonfigurujemy opcje zapisywania HTML, aby eksportować czcionki podstawowe 64. Użyj następującego kodu:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Ten kod tworzy instancję`HtmlSaveOptions` i zestawy`ExportFontsAsBase64` Do`true` aby określić, że czcionki powinny być eksportowane jako dane Base 64 podczas zapisywania jako HTML.

## Krok 4: Konwertowanie i zapisywanie dokumentu do formatu HTML

Na koniec skonwertujemy dokument do formatu HTML, korzystając ze skonfigurowanych wcześniej opcji zapisywania HTML. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Ten kod konwertuje dokument do formatu HTML i zapisuje go w pliku z czcionkami wyeksportowanymi jako dane Base 64.

### Przykładowy kod źródłowy dla eksportu czcionek jako Base 64 przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Pamiętaj, aby podać poprawną ścieżkę do katalogu dokumentów w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak eksportować czcionki Base 64 podczas zapisywania dokumentu jako HTML przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo bezpiecznie eksportować czcionki i osadzać je w dokumentach HTML.