---
title: Eksportuj adresy URL Cid do zasobów Mhtml
linktitle: Eksportuj adresy URL Cid do zasobów Mhtml
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący eksportowania adresów URL CID zasobów MHTML podczas zapisywania dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby wyeksportować adresy URL CID dla zasobów MHTML za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia eksportowanie adresów URL CID zasobów MHTML podczas zapisywania dokumentu w formacie MHTML.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument do eksportu. Użyj poniższego kodu, aby załadować dokument z określonego katalogu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Ten kod tworzy instancję`Document` poprzez załadowanie dokumentu z określonego katalogu.

## Krok 3: Konfiguracja opcji tworzenia kopii zapasowych HTML

Teraz skonfigurujemy opcje zapisywania HTML, aby eksportować adresy URL CID zasobów MHTML. Użyj następującego kodu:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Ten kod tworzy instancję`HtmlSaveOptions` z formatem zapisu ustawionym na MHTML. Umożliwia także eksport adresów URL CID zasobów MHTML poprzez ustawienie`ExportCidUrlsForMhtmlResources` Do`true`.

## Krok 4: Konwertowanie i zapisywanie dokumentu do formatu MHTML

Na koniec skonwertujemy dokument do formatu MHTML, korzystając ze skonfigurowanych wcześniej opcji zapisywania HTML. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Ten kod konwertuje dokument do formatu MHTML i zapisuje go w pliku z adresami URL CID wyeksportowanych zasobów MHTML.

### Przykładowy kod źródłowy dla eksportu adresów URL Cid dla zasobów Mhtml przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Pamiętaj, aby podać poprawną ścieżkę do katalogu dokumentów w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak eksportować adresy URL CID zasobów MHTML podczas zapisywania dokumentu w formacie MHTML przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo zarządzać adresami URL CID w eksportowanych dokumentach MHTML.

