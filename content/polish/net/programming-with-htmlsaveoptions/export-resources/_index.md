---
title: Eksportuj zasoby
linktitle: Eksportuj zasoby
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący eksportowania zasobów dokumentów podczas zapisywania jako HTML za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/export-resources/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C# umożliwiający eksport zasobów dokumentów za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia eksport zasobów, takich jak czcionki, jako pliki zewnętrzne podczas zapisywania dokumentu w formacie HTML.

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

Teraz skonfigurujemy opcje zapisywania HTML, aby wyeksportować zasoby dokumentu. Użyj następującego kodu:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://przykład.com/zasoby”
};
```

 Ten kod tworzy instancję`HtmlSaveOptions` i ustawia następujące opcje:

- `CssStyleSheetType` jest ustawione na`CssStyleSheetType.External` aby wyeksportować arkusz stylów CSS do pliku zewnętrznego.
- `ExportFontResources` jest ustawione na`true` aby wyeksportować zasoby czcionek.
- `ResourceFolder` określa katalog docelowy, w którym zostaną zapisane zasoby.
- `ResourceFolderAlias`określa alias adresu URL, który będzie używany w celu uzyskania dostępu do zasobów.

## Krok 4: Konwertowanie i zapisywanie dokumentu do formatu HTML

Na koniec skonwertujemy dokument do formatu HTML, korzystając ze skonfigurowanych wcześniej opcji zapisywania HTML. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Ten kod konwertuje dokument do formatu HTML i zapisuje zasoby w określonym katalogu przy użyciu określonego aliasu adresu URL.

### Przykładowy kod źródłowy dla zasobów eksportowych przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://przykład.com/zasoby”
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Pamiętaj, aby podać poprawną ścieżkę do katalogu dokumentów w pliku`dataDir` zmienny.