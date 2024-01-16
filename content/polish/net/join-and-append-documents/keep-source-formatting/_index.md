---
title: Zachowaj formatowanie źródłowe
linktitle: Zachowaj formatowanie źródłowe
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dołączyć dokument źródłowy do dokumentu docelowego, zachowując oryginalne formatowanie, używając Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/keep-source-formatting/
---

W tym samouczku pokazano, jak dołączyć dokument źródłowy do dokumentu docelowego, zachowując oryginalne formatowanie dokumentu źródłowego za pomocą Aspose.Words dla .NET.

## Krok 1: Skonfiguruj projekt

Upewnij się, że masz następujące wymagania wstępne:

-  Zainstalowana biblioteka Aspose.Words dla .NET. Można go pobrać z[Aspose.Releases]https://releases.aspose.com/words/net/ lub użyj menedżera pakietów NuGet, aby go zainstalować.
- Ścieżka katalogu dokumentów, w którym zostaną zapisane dokumenty źródłowe i docelowe.

## Krok 2: Utwórz dokumenty docelowe i źródłowe

 Utwórz instancje`Document` dla dokumentów docelowych i źródłowych.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Krok 3: Dołącz dokument źródłowy do dokumentu docelowego

 Użyj`AppendDocument` metoda dokumentu docelowego w celu dołączenia dokumentu źródłowego. Przechodzić`ImportFormatMode.KeepSourceFormatting` jako tryb formatu importu, aby zachować oryginalne formatowanie dokumentu źródłowego.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 4: Zapisz zmodyfikowany dokument

 Zapisz zmodyfikowany dokument za pomocą`Save` metoda`Document` obiekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

To kończy implementację dołączania dokumentu źródłowego do dokumentu docelowego przy zachowaniu oryginalnego formatowania przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Zachowaj formatowanie źródła przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Dołącz dokument źródłowy do dokumentu docelowego.
	// Tryb formatu przejścia, aby zachować oryginalne formatowanie dokumentu źródłowego podczas jego importu.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```