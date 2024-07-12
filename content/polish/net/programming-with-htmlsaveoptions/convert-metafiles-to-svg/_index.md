---
title: Konwertuj metapliki na format Svg
linktitle: Konwertuj metapliki na format Svg
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący konwersji metaplików do formatu SVG podczas konwersji dokumentu do HTML za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby przekonwertować metapliki do formatu SVG za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia konwersję metaplików do formatu SVG podczas konwersji dokumentu do HTML.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Wstawianie obrazu SVG do dokumentu

Na tym etapie wstawimy obraz SVG do dokumentu, który ma zostać przekonwertowany. Użyj poniższego kodu, aby wstawić obraz SVG za pomocą tagu HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Ten kod tworzy instancję`Document`I`DocumentBuilder` do zbudowania dokumentu. Wstawia A`<svg>` znacznik zawierający a`<polygon>` element z atrybutami definiującymi kształt i styl obrazu SVG.

## Krok 3: Ustaw opcje zapisywania HTML

Teraz ustawimy opcje zapisywania HTML, określając, że metapliki powinny zostać skonwertowane do formatu SVG. Użyj następującego kodu:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Ten kod tworzy instancję`HtmlSaveOptions` i zestawy`MetafileFormat` Do`HtmlMetafileFormat.Svg` aby określić, że metapliki powinny być konwertowane do formatu SVG podczas konwersji do HTML.

## Krok 4: Konwertowanie i zapisywanie dokumentu do formatu HTML

Na koniec przekonwertujemy dokument na format HTML, korzystając z zdefiniowanych wcześniej opcji zapisywania HTML. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Ten kod konwertuje dokument do formatu HTML i zapisuje go w pliku z metaplikami konwertowanymi do formatu SVG.

### Przykładowy kod źródłowy konwersji metaplików na Svg przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
