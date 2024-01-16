---
title: Rozwiąż nazwy czcionek
linktitle: Rozwiąż nazwy czcionek
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący rozwiązywania brakujących nazw czcionek podczas konwersji do formatu HTML za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/resolve-font-names/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby rozwiązać brakujące nazwy czcionek za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia automatyczne rozpoznanie brakujących nazw czcionek podczas konwersji dokumentu do formatu HTML.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument do przetworzenia. Użyj poniższego kodu, aby załadować dokument z określonego katalogu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Ten kod tworzy instancję`Document` poprzez załadowanie dokumentu z określonego katalogu.

## Krok 3: Konfiguracja opcji tworzenia kopii zapasowych HTML

Teraz skonfigurujemy opcje zapisywania HTML, aby rozwiązać brakujące nazwy czcionek podczas konwersji. Użyj następującego kodu:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Ten kod tworzy instancję`HtmlSaveOptions` ustawia`ResolveFontNames` opcja`true`aby rozwiązać brakujące nazwy czcionek podczas konwersji do formatu HTML. Również,`PrettyFormat` opcja jest ustawiona na`true` aby uzyskać ładnie sformatowany kod HTML.

## Krok 4: Konwertowanie i zapisywanie dokumentu do formatu HTML

Na koniec skonwertujemy dokument do formatu HTML, korzystając ze skonfigurowanych wcześniej opcji zapisywania HTML. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Ten kod konwertuje dokument do formatu HTML, automatycznie rozwiązując brakujące nazwy czcionek i zapisuje przekonwertowany plik HTML w określonym katalogu.

### Przykładowy kod źródłowy rozwiązania nazw czcionek przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Pamiętaj, aby podać poprawną ścieżkę do katalogu dokumentów w pliku`dataDir` zmienny.