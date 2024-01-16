---
title: Zapisz wszystkie reguły CSS w jednym pliku
linktitle: Zapisz wszystkie reguły CSS w jednym pliku
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak przekonwertować dokument Word na stały kod HTML, zapisując wszystkie reguły CSS w jednym pliku za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Konwertując dokument programu Word na stały kod HTML w aplikacji C#, możesz chcieć skonsolidować wszystkie reguły CSS w jednym pliku, aby zapewnić lepszą organizację i przenośność. Dzięki bibliotece Aspose.Words dla .NET możesz łatwo określić tę funkcjonalność za pomocą opcji zapisywania HtmlFixedSaveOptions. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces użycia kodu źródłowego Aspose.Words for .NET C# do konwersji dokumentu Word na stały kod HTML poprzez zapisanie wszystkich reguł CSS w jednym pliku przy użyciu opcji zapisywania HtmlFixedSaveOptions.

## Zrozumienie biblioteki Aspose.Words

Przed zagłębieniem się w kod ważne jest zapoznanie się z biblioteką Aspose.Words dla platformy .NET. Aspose.Words to potężna biblioteka do tworzenia, edytowania, konwertowania i ochrony dokumentów programu Word na różnych platformach, w tym .NET. Oferuje wiele funkcji do manipulowania dokumentami, takich jak wstawianie tekstu, zmiana formatowania, dodawanie sekcji i wiele więcej.

## Ładowanie dokumentu Word

Pierwszym krokiem jest załadowanie dokumentu Word, który chcesz przekonwertować na stały kod HTML. Użyj klasy Document, aby załadować dokument z pliku źródłowego. Oto przykład :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

W tym przykładzie ładujemy dokument „Document.docx” znajdujący się w katalogu dokumentów.

## Konfigurowanie opcji tworzenia kopii zapasowych

Następnym krokiem jest skonfigurowanie opcji zapisu konwersji do stałego formatu HTML. Użyj klasy HtmlFixedSaveOptions i ustaw właściwość SaveFontFaceCssSeparately na false, aby zapisać wszystkie reguły CSS w jednym pliku. Oto jak to zrobić:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Tworzymy nowy obiekt HtmlFixedSaveOptions i ustawiamy właściwość SaveFontFaceCssSeparately na false, aby zapisać wszystkie reguły CSS w jednym pliku.

## Naprawiono konwersję dokumentu HTML

Teraz, gdy skonfigurowaliśmy opcje zapisywania, możemy przystąpić do konwersji dokumentu do stałego formatu HTML. Użyj metody Save klasy Document, aby zapisać przekonwertowany dokument w ustalonym formacie HTML, określając opcje zapisywania. Oto przykład :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

tym przykładzie zapisujemy przekonwertowany dokument jako „WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html”, korzystając z określonych opcji zapisywania.

### Przykładowy kod źródłowy dla HtmlFixedSaveOptions z funkcją „Zapisz wszystkie reguły CSS w jednym pliku” przy użyciu Aspose.Words dla .NET

```csharp
// Ścieżka dostępu do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument programu Word
Document doc = new Document(dataDir + "Document.docx");

// Skonfiguruj opcje tworzenia kopii zapasowych za pomocą funkcji „Zapisz wszystkie reguły CSS w jednym pliku”.
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Konwertuj dokument na stały kod HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Wniosek

W tym przewodniku omówiliśmy, jak przekonwertować dokument Word na stały kod HTML, zapisując wszystkie reguły CSS w jednym pliku przy użyciu HtmlFixedSaveOptions z biblioteką Aspose.Words dla .NET. Wykonując podane kroki i korzystając z dostarczonego kodu źródłowego C#, możesz łatwo zastosować tę funkcjonalność w swojej aplikacji C#. Zapisanie wszystkich reguł CSS w jednym pliku ułatwia organizację i zarządzanie kodem HTML wygenerowanym podczas konwersji dokumentu.