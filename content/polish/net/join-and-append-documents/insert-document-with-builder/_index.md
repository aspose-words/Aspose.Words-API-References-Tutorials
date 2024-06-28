---
title: Wstaw dokument za pomocą Buildera
linktitle: Wstaw dokument za pomocą Buildera
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić dokument na końcu innego dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/insert-document-with-builder/
---

 W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do wstawiania dokumentu do innego dokumentu za pomocą`DocumentBuilder` klasa. Dostarczony kod źródłowy pokazuje, jak wstawić dokument na końcu innego dokumentu, zachowując formatowanie źródłowe.

## Krok 1: Skonfiguruj projekt

Upewnij się, że masz następujące wymagania wstępne:

-  Zainstalowana biblioteka Aspose.Words dla .NET. Można go pobrać z[Aspose.Releases]https://releases.aspose.com/words/net/ lub użyj menedżera pakietów NuGet, aby go zainstalować.
- Ścieżka katalogu dokumentów, w którym znajdują się dokumenty źródłowe i docelowe.

## Krok 2: Otwórz dokumenty źródłowe i docelowe

 Otwórz dokumenty źródłowe i docelowe za pomocą narzędzia`Document` konstruktor klasy. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Krok 3: Zainicjuj narzędzie DocumentBuilder

 Utwórz nową instancję`DocumentBuilder` class i przekazać dokument docelowy jako parametr.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Krok 4: Ustaw moduł DocumentBuilder

Przesuń`DocumentBuilder` na koniec dokumentu za pomocą`MoveToDocumentEnd` metoda. Wstaw podział strony, aby oddzielić istniejącą treść od wstawionego dokumentu.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Krok 5: Włóż dokument źródłowy

 Użyj`InsertDocument` metoda`DocumentBuilder` class, aby wstawić dokument źródłowy do dokumentu docelowego. Ustaw tryb formatu importu na`ImportFormatMode.KeepSourceFormatting` aby zachować formatowanie źródłowe.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 6: Zapisz zmodyfikowany dokument

Na koniec zapisz zmodyfikowany dokument docelowy za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

To kończy implementację wstawiania dokumentu do innego dokumentu za pomocą Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Wstaw dokument za pomocą Buildera przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```