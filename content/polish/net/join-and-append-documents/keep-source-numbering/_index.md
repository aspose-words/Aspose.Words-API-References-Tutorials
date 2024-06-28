---
title: Zachowaj numerację źródłową
linktitle: Zachowaj numerację źródłową
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dołączyć dokument, zachowując formatowanie numeracji źródłowej w Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/keep-source-numbering/
---

tym samouczku wyjaśniono, jak dołączyć dokument źródłowy do dokumentu docelowego, zachowując oryginalne formatowanie numeracji ponumerowanych akapitów za pomocą Aspose.Words dla .NET.

## Krok 1: Skonfiguruj projekt

Upewnij się, że masz następujące wymagania wstępne:

-  Zainstalowana biblioteka Aspose.Words dla .NET. Można go pobrać z[Aspose.Releases]https://releases.aspose.com/words/net/ lub użyj menedżera pakietów NuGet, aby go zainstalować.
- Ścieżka katalogu dokumentów, w którym zostaną zapisane dokumenty źródłowe i docelowe.

## Krok 2: Utwórz dokumenty docelowe i źródłowe

 Utwórz instancje`Document` dla dokumentów docelowych i źródłowych.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Krok 3: Zachowaj numerację źródłową podczas importowania

 Aby zachować formatowanie numeracji ponumerowanych akapitów z dokumentu źródłowego, utwórz instancję`ImportFormatOptions` i nastaw`KeepSourceNumbering` Do`true` . Użyć`NodeImporter` aby zaimportować węzły z dokumentu źródłowego do dokumentu docelowego, określając`ImportFormatMode.KeepSourceFormatting` i`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Krok 4: Importuj i dodawaj akapity

 Wykonaj iterację po akapitach w dokumencie źródłowym i zaimportuj każdy akapit do dokumentu docelowego za pomocą`importer`. Dołącz zaimportowane węzły do treści dokumentu docelowego.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Krok 5: Zapisz zmodyfikowany dokument

 Zapisz zmodyfikowany dokument za pomocą`Save` metoda`Document` obiekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

To kończy implementację dołączania dokumentu źródłowego do dokumentu docelowego przy zachowaniu oryginalnego formatowania numeracji przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy funkcji Zachowaj numerację źródłową przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Zachowaj formatowanie listy źródłowej podczas importowania numerowanych akapitów.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```