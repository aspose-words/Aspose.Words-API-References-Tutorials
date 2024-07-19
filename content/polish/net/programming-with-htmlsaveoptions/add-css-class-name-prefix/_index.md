---
title: Dodaj przedrostek nazwy klasy CSS
linktitle: Dodaj przedrostek nazwy klasy CSS
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący dodawania przedrostka nazwy klasy CSS podczas konwersji dokumentu do formatu HTML za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby dodać przedrostek nazwy klasy CSS za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia dodanie niestandardowego przedrostka do wygenerowanych nazw klas CSS podczas konwersji dokumentu do formatu HTML.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument Word, który chcemy przekonwertować na HTML. Aby załadować dokument, użyj poniższego kodu:

```csharp
//Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu, w którym znajduje się dokument.

## Krok 3: Ustaw opcje zapisywania HTML

Teraz ustawmy opcje zapisywania HTML, w tym typ arkusza stylów CSS i przedrostek nazwy klasy CSS. Użyj następującego kodu:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Ten kod tworzy instancję`HtmlSaveOptions` i zestawy`CssStyleSheetType` Do`CssStyleSheetType.External` wygenerować zewnętrzny arkusz stylów CSS i`CssClassNamePrefix` Do`"pfx_"` prefiksować`"pfx_"` nadawać nazwy klasom CSS.

## Krok 4: Konwertowanie i zapisywanie dokumentu do formatu HTML

Na koniec przekonwertujemy dokument na format HTML, korzystając z zdefiniowanych wcześniej opcji zapisywania HTML. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Ten kod konwertuje dokument do formatu HTML i zapisuje go w pliku z dodanym przedrostkiem nazwy klasy CSS.

### Przykładowy kod źródłowy dla dodania prefiksu nazwy klasy Css przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Pamiętaj, aby określić poprawną ścieżkę dokumentu w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak dodać przedrostek nazwy klasy CSS podczas konwersji dokumentu do HTML przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowymi instrukcjami zawartymi w tym samouczku, możesz dostosować nazwy klas CSS w przekonwertowanych dokumentach HTML.