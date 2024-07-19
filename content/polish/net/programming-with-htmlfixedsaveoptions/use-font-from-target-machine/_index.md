---
title: Użyj czcionki z komputera docelowego
linktitle: Użyj czcionki z komputera docelowego
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak przekonwertować dokument programu Word na stały kod HTML przy użyciu czcionek komputera docelowego za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Konwertując dokument programu Word na stały kod HTML w aplikacji C#, możesz chcieć użyć czcionek komputera docelowego, aby mieć pewność, że renderowany kod HTML zachowa oryginalny wygląd i styl dokumentu. Dzięki bibliotece Aspose.Words dla .NET możesz łatwo określić tę funkcjonalność za pomocą opcji zapisywania HtmlFixedSaveOptions. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces używania kodu źródłowego C# Aspose.Words dla .NET do konwersji dokumentu programu Word na stały kod HTML przy użyciu czcionek komputera docelowego przy użyciu opcji HtmlFixedSaveOptions.

## Zrozumienie biblioteki Aspose.Words

Przed zagłębieniem się w kod ważne jest zapoznanie się z biblioteką Aspose.Words dla platformy .NET. Aspose.Words to potężna biblioteka do tworzenia, edytowania, konwertowania i ochrony dokumentów programu Word na różnych platformach, w tym .NET. Oferuje wiele funkcji do manipulowania dokumentami, takich jak wstawianie tekstu, zmiana formatowania, dodawanie sekcji i wiele więcej.

## Ładowanie dokumentu Word

Pierwszym krokiem jest załadowanie dokumentu Word, który chcesz przekonwertować na stały kod HTML. Użyj klasy Document, aby załadować dokument z pliku źródłowego. Oto przykład :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

W tym przykładzie ładujemy dokument „Punkty z alternatywną czcionką.docx” znajdujący się w katalogu dokumentów.

## Konfigurowanie opcji tworzenia kopii zapasowych

Następnym krokiem jest skonfigurowanie opcji zapisu konwersji do stałego formatu HTML. Użyj klasy HtmlFixedSaveOptions i ustaw właściwość UseTargetMachineFonts na true, aby poinformować Aspose.Words, aby używał czcionek z komputera docelowego. Oto jak to zrobić:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Tworzymy nowy obiekt HtmlFixedSaveOptions i ustawiamy właściwość UseTargetMachineFonts na true, aby podczas konwersji używać czcionek komputera docelowego.

## Naprawiono konwersję dokumentu HTML

Teraz, gdy skonfigurowaliśmy opcje zapisywania, możemy przystąpić do konwersji dokumentu do stałego formatu HTML. Użyj metody Save klasy Document, aby zapisać przekonwertowany dokument w ustalonym formacie HTML, określając opcje zapisywania. Oto przykład :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

W tym przykładzie zapisujemy przekonwertowany dokument jako „WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html”, korzystając z określonych opcji zapisywania.

### Przykładowy kod źródłowy dla HtmlFixedSaveOptions z funkcją „Użyj czcionek z komputera docelowego” przy użyciu Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument programu Word
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

// Skonfiguruj opcje tworzenia kopii zapasowych za pomocą funkcji „Użyj czcionek z komputera docelowego”.
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Konwertuj dokument na stały kod HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Wniosek

tym przewodniku wyjaśniliśmy, jak przekonwertować dokument Word na stały kod HTML przy użyciu czcionek komputera docelowego za pomocą biblioteki Aspose.Words dla .NET. Wykonując podane kroki i korzystając z dostarczonego kodu źródłowego C#, możesz łatwo zastosować tę funkcjonalność w swojej aplikacji C#. Konwersja do stałego HTML z czcionkami maszyny docelowej gwarantuje wierne i spójne renderowanie dokumentu w formacie HTML.
