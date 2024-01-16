---
title: Dołącz z opcjami formatu importu
linktitle: Dołącz z opcjami formatu importu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dołączyć dokument z opcjami formatu importu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/append-with-import-format-options/
---

tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do dołączania zawartości jednego dokumentu do drugiego z opcjami formatu importu. Dostarczony kod źródłowy pokazuje, jak otworzyć dokumenty źródłowe i docelowe, określić opcje formatu importu i dołączyć dokument źródłowy do dokumentu docelowego.

## Krok 1: Skonfiguruj projekt

Upewnij się, że masz następujące wymagania wstępne:

-  Zainstalowana biblioteka Aspose.Words dla .NET. Można go pobrać z[Aspose.Releases]https://releases.aspose.com/words/net/ lub użyj menedżera pakietów NuGet, aby go zainstalować.
- Ścieżka katalogu dokumentów, w którym znajdują się dokumenty źródłowe i docelowe.

## Krok 2: Otwórz dokumenty źródłowe i docelowe

 Otwórz dokumenty źródłowe i docelowe za pomocą narzędzia`Document` konstruktor klasy. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Krok 3: Określ opcje formatu importu

 Utwórz instancję`ImportFormatOptions` class, aby określić opcje formatu importu. W tym przykładzie używamy`KeepSourceNumbering` aby mieć pewność, że w przypadku kolizji z dokumentem docelowym zostanie użyta numeracja z dokumentu źródłowego.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Krok 4: Dołącz dokument źródłowy do dokumentu docelowego

 Użyj`AppendDocument` metoda dokumentu docelowego w celu dołączenia dokumentu źródłowego. Przechodzić`ImportFormatMode.UseDestinationStyles` jako drugi parametr umożliwiający użycie stylów i formatowania dokumentu docelowego.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Krok 5: Zapisz dokument docelowy

 Na koniec zapisz zmodyfikowany dokument docelowy za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

To kończy implementację dołączania dokumentu z opcjami formatu importu przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy opcji Dołącz z opcjami formatu importu przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Określ, że jeśli numeracja koliduje w dokumentach źródłowych i docelowych,
	//wówczas zastosowana zostanie numeracja z dokumentu źródłowego.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```