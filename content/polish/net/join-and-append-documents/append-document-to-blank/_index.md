---
title: Dołącz dokument do pustego miejsca
linktitle: Dołącz dokument do pustego miejsca
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dołączyć dokument do pustego dokumentu docelowego w Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/append-document-to-blank/
---

tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do dołączania zawartości jednego dokumentu do pustego dokumentu docelowego. Dostarczony kod źródłowy pokazuje, jak utworzyć nowy dokument, usunąć jego zawartość, a następnie dołączyć do niego dokument źródłowy.

## Krok 1: Skonfiguruj projekt

Upewnij się, że masz następujące wymagania wstępne:

-  Zainstalowana biblioteka Aspose.Words dla .NET. Można go pobrać z[Aspose.Releases]https://releases.aspose.com/words/net/ lub użyj menedżera pakietów NuGet, aby go zainstalować.
- Ścieżka katalogu dokumentów, w którym znajdują się dokumenty źródłowe i docelowe.

## Krok 2: Utwórz nowy dokument docelowy

 Stwórz nowy`Document` obiekt dla dokumentu docelowego.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Krok 3: Usuń istniejącą treść z dokumentu docelowego

 Aby zapewnić czysty dokument docelowy, usuń całą istniejącą zawartość z dokumentu za pomocą`RemoveAllChildren` metoda.

```csharp
dstDoc.RemoveAllChildren();
```

## Krok 4: Dołącz dokument źródłowy do dokumentu docelowego

 Dołącz zawartość dokumentu źródłowego do dokumentu docelowego za pomocą`AppendDocument` metoda z`ImportFormatMode.KeepSourceFormatting` opcja.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Zapisz dokument docelowy

Na koniec zapisz zmodyfikowany dokument docelowy za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

To kończy implementację dołączania dokumentu do pustego dokumentu docelowego przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy funkcji Dołącz dokument do pustego przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// Dokument docelowy nie jest pusty, co często powoduje pojawienie się pustej strony przed dołączonym dokumentem.
	// Dzieje się tak dlatego, że dokument bazowy ma pustą sekcję, a nowy dokument rozpoczyna się na następnej stronie.
	// Przed dołączeniem usuń całą zawartość z dokumentu docelowego.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```