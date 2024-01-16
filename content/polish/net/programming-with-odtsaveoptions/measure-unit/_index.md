---
title: Jednostka miary
linktitle: Jednostka miary
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak określić jednostkę miary podczas konwersji dokumentu Word na ODT za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-odtsaveoptions/measure-unit/
---

Konwertując dokument programu Word do formatu OpenDocument Text (ODT) w aplikacji C#, możesz chcieć określić jednostkę miary używaną do mierzalnych właściwości formatowania i zawartości. Dzięki bibliotece Aspose.Words dla .NET możesz łatwo określić tę funkcjonalność za pomocą opcji zapisu OdtSaveOptions. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces używania kodu źródłowego Aspose.Words for .NET C# do konwersji dokumentu Word na ODT poprzez określenie jednostki miary za pomocą opcji OdtSaveOptions.

## Zrozumienie biblioteki Aspose.Words

Przed zagłębieniem się w kod ważne jest zapoznanie się z biblioteką Aspose.Words dla platformy .NET. Aspose.Words to potężna biblioteka do tworzenia, edytowania, konwertowania i ochrony dokumentów programu Word na różnych platformach, w tym .NET. Oferuje wiele funkcji do manipulowania dokumentami, takich jak wstawianie tekstu, zmiana formatowania, dodawanie sekcji i wiele więcej.

## Ładowanie dokumentu Word

Pierwszym krokiem jest załadowanie dokumentu Word, który chcesz przekonwertować na ODT. Użyj klasy Document, aby załadować dokument z pliku źródłowego. Oto przykład :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

W tym przykładzie ładujemy dokument „Document.docx” znajdujący się w katalogu dokumentów.

## Konfigurowanie opcji tworzenia kopii zapasowych

Następnym krokiem jest skonfigurowanie opcji tworzenia kopii zapasowych dla konwersji do ODT. Użyj klasy OdtSaveOptions i ustaw właściwość MeasureUnit na żądaną wartość. Na przykład, jeśli chcesz używać cali jako jednostki miary, ustaw MeasureUnit na OdtSaveMeasureUnit.Inches. Oto jak to zrobić:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Tworzymy nowy obiekt OdtSaveOptions i ustawiamy właściwość MeasureUnit na żądaną wartość, w naszym przypadku OdtSaveMeasureUnit.Inches, aby jako jednostkę miary używać cali.

## Konwertuj dokument na ODT

Teraz, gdy skonfigurowaliśmy opcje zapisywania, możemy przystąpić do konwersji dokumentu do ODT. Użyj metody Save klasy Document, aby zapisać przekonwertowany dokument w formacie ODT, określając opcje zapisywania. Oto przykład :

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

tym przykładzie zapisujemy przekonwertowany dokument jako „WorkingWithOdtSaveOptions.MeasureUnit.odt”, korzystając z określonych opcji zapisywania.

### Przykładowy kod źródłowy OdtSaveOptions z funkcjonalnością „Jednostka miary” przy użyciu Aspose.Words dla .NET



```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument programu Word
Document doc = new Document(dataDir + "Document.docx");

// Konfiguracja opcji tworzenia kopii zapasowych za pomocą funkcji „Jednostka miary”.
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Konwertuj dokument na ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Wniosek

W tym przewodniku wyjaśniliśmy, jak przekonwertować dokument Word na ODT, określając jednostkę miary przy użyciu opcji zapisu OdtSaveOptions w bibliotece Aspose.Words dla .NET. Wykonując podane kroki i korzystając z dostarczonego kodu źródłowego C#, możesz łatwo zastosować tę funkcjonalność w swojej aplikacji C#. Określenie jednostki miary podczas konwersji na ODT pozwala kontrolować formatowanie i wymiary powstałego dokumentu zgodnie z własnymi potrzebami.