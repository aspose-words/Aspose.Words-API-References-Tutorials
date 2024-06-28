---
title: Ignoruj stopkę nagłówka
linktitle: Ignoruj stopkę nagłówka
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dołączyć dokument, ignorując zawartość nagłówka i stopki, używając Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/ignore-header-footer/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do dołączania dokumentu, ignorując zawartość nagłówka i stopki. Dostarczony kod źródłowy pokazuje, jak skonfigurować opcje formatu importu, aby wykluczyć nagłówek i stopkę podczas procesu dołączania.

## Krok 1: Skonfiguruj projekt

Upewnij się, że masz następujące wymagania wstępne:

-  Zainstalowana biblioteka Aspose.Words dla .NET. Można go pobrać z[Aspose.Releases]https://releases.aspose.com/words/net/ lub użyj menedżera pakietów NuGet, aby go zainstalować.
- Ścieżka katalogu dokumentów, w którym znajdują się dokumenty źródłowe i docelowe.

## Krok 2: Otwórz dokumenty źródłowe i docelowe

 Otwórz dokumenty źródłowe i docelowe za pomocą narzędzia`Document` konstruktor klasy. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Krok 3: Skonfiguruj opcje formatu importu

 Utwórz instancję`ImportFormatOptions` klasę i ustaw`IgnoreHeaderFooter`własność do`false`. Dzięki temu zawartość nagłówka i stopki zostanie uwzględniona podczas procesu dołączania.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Krok 4: Dołącz dokument źródłowy do dokumentu docelowego

 Użyj`AppendDocument` metoda dokumentu docelowego w celu dołączenia dokumentu źródłowego. Przechodzić`ImportFormatMode.KeepSourceFormatting`jako drugi parametr, a opcje formatu importu jako trzeci parametr.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Krok 5: Zapisz dokument docelowy

Na koniec zapisz zmodyfikowany dokument docelowy za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

To kończy implementację dołączania dokumentu, ignorując zawartość nagłówka i stopki przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy opcji Ignoruj stopkę nagłówka przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```