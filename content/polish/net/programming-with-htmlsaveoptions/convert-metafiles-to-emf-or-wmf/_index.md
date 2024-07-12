---
title: Konwertuj metapliki na format EMF lub WMF
linktitle: Konwertuj metapliki na format EMF lub WMF
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący konwersji metaplików do formatów EMF lub WMF podczas konwersji dokumentu do formatu HTML za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby przekonwertować metapliki do formatu EMF lub WMF za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia konwersję obrazów w formacie metapliku do bardziej zgodnych formatów, takich jak EMF lub WMF podczas konwersji dokumentu do formatu HTML.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Wstawianie obrazu do dokumentu

Na tym etapie wstawimy obraz do dokumentu, który ma zostać przekonwertowany. Użyj poniższego kodu, aby wstawić obraz ze źródła danych za pomocą tagu HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Ten kod tworzy instancję`Document`I`DocumentBuilder` do zbudowania dokumentu. Wstawia`<img>` w dokumencie z obrazem zakodowanym w standardzie base64.

## Krok 3: Ustaw opcje zapisywania HTML

Teraz ustawimy opcje zapisywania HTML, w tym format metapliku używany dla obrazów. Użyj następującego kodu:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Ten kod tworzy instancję`HtmlSaveOptions` i zestawy`MetafileFormat` Do`HtmlMetafileFormat.EmfOrWmf` aby określić, że metapliki powinny być konwertowane do formatu EMF lub WMF podczas konwersji do HTML.

## Krok 4: Konwertowanie i zapisywanie dokumentu do formatu HTML

Na koniec skonwertujemy dokument do formatu HTML, korzystając z wcześniej zdefiniowanych opcji zapisywania HTML. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Ten kod konwertuje dokument do formatu HTML i zapisuje go do pliku z przekonwertowanymi metaplikami w formacie EMF lub WMF, w zależności od ustawionych opcji zapisu.

### Przykładowy kod źródłowy konwersji metaplików na format Emf lub Wmf przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Pamiętaj, aby podać poprawną ścieżkę do katalogu dokumentów w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak konwertować metapliki do formatów EMF lub WMF podczas konwersji dokumentu do HTML za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo zarządzać metaplikami w przekonwertowanych dokumentach HTML.