---
title: Ignoruj pola tekstowe
linktitle: Ignoruj pola tekstowe
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dołączyć dokument, ignorując formatowanie pola tekstowego, używając Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/ignore-text-boxes/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do dołączania dokumentu przy jednoczesnym zachowaniu formatowania pól tekstowych. Dostarczony kod źródłowy pokazuje, jak skonfigurować opcje formatu importu, aby uwzględnić pola tekstowe podczas procesu dołączania.

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

## Krok 3: Skonfiguruj opcje formatu importu

 Utwórz instancję`ImportFormatOptions` klasę i ustaw`IgnoreTextBoxes`własność do`false`. Dzięki temu pola tekstowe zostaną uwzględnione podczas procesu dołączania, zachowując jednocześnie ich formatowanie.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Krok 4: Dołącz zawartość pola tekstowego

 Stwórz`NodeImporter` obiekt i użyj go do zaimportowania węzłów pól tekstowych z dokumentu źródłowego do dokumentu docelowego. Wykonaj iterację po każdym akapicie w dokumencie źródłowym i zaimportuj go do dokumentu docelowego.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Krok 5: Zapisz dokument docelowy

 Na koniec zapisz zmodyfikowany dokument docelowy za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

To kończy implementację dołączania dokumentu, zachowując formatowanie pola tekstowego przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Ignoruj pola tekstowe przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Podczas importowania zachowaj formatowanie źródłowych pól tekstowych.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```