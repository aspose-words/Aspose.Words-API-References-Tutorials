---
title: Dołącz do nowej strony
linktitle: Dołącz do nowej strony
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak połączyć dwa dokumenty na nowej stronie, zachowując formatowanie, używając Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/join-new-page/
---

W tym samouczku wyjaśniono, jak połączyć dwa dokumenty na nowej stronie za pomocą Aspose.Words dla .NET. Dostarczony kod źródłowy pokazuje, jak dołączyć dokument na końcu innego dokumentu, rozpoczynając dołączany dokument na nowej stronie.

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

## Krok 3: Skonfiguruj nowy początek sekcji strony

 Aby rozpocząć dołączany dokument na nowej stronie, ustaw opcję`SectionStart` właściwość pierwszej sekcji dokumentu źródłowego do`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Krok 4: Dołącz dokument źródłowy

 Dołącz dokument źródłowy do dokumentu docelowego za pomocą`AppendDocument` metoda`Document` klasa. Ustaw tryb formatu importu na`ImportFormatMode.KeepSourceFormatting` aby zachować oryginalne style z dokumentu źródłowego.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Zapisz zmodyfikowany dokument

 Na koniec zapisz zmodyfikowany dokument docelowy za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

To kończy implementację łączenia dwóch dokumentów na nowej stronie za pomocą Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Dołącz do nowej strony przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Ustaw dołączony dokument tak, aby zaczynał się od nowej strony.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Dołącz dokument źródłowy, używając oryginalnych stylów znalezionych w dokumencie źródłowym.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```