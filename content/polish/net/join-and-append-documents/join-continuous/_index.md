---
title: Dołącz do ciągłego
linktitle: Dołącz do ciągłego
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak w sposób ciągły łączyć dwa dokumenty, zachowując formatowanie, używając Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/join-continuous/
---

W tym samouczku wyjaśniono, jak w sposób ciągły łączyć dwa dokumenty za pomocą Aspose.Words dla .NET. Dostarczony kod źródłowy pokazuje, jak dołączyć dokument na końcu innego dokumentu, zachowując oryginalne formatowanie.

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

## Krok 3: Skonfiguruj ciągły start sekcji

Aby dokument źródłowy pojawił się zaraz po treści dokumentu docelowego, ustaw opcję`SectionStart` właściwość pierwszej sekcji dokumentu źródłowego do`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Krok 4: Dołącz dokument źródłowy

 Dołącz dokument źródłowy do dokumentu docelowego za pomocą`AppendDocument` metoda`Document` klasa. Ustaw tryb formatu importu na`ImportFormatMode.KeepSourceFormatting` aby zachować oryginalne style z dokumentu źródłowego.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Zapisz zmodyfikowany dokument

Na koniec zapisz zmodyfikowany dokument docelowy za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

To kończy implementację łączenia dwóch dokumentów w sposób ciągły przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy Join Continuous przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Spraw, aby dokument pojawił się bezpośrednio po treści dokumentu docelowego.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Dołącz dokument źródłowy, używając oryginalnych stylów znalezionych w dokumencie źródłowym.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```