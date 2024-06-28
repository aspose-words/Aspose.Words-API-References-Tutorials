---
title: Inna konfiguracja strony
linktitle: Inna konfiguracja strony
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dołączyć dokument z różnymi ustawieniami ustawień strony za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/different-page-setup/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do dołączania dokumentu z różnymi ustawieniami ustawień strony do innego dokumentu. Dostarczony kod źródłowy pokazuje, jak skonfigurować różne ustawienia strony dla dokumentów źródłowych i docelowych oraz zapewnić właściwą kontynuację i numerację.

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

## Krok 3: Skonfiguruj ustawienia strony dla dokumentu źródłowego

 Dostosuj ustawienia strony dokumentu źródłowego, aby zapewnić prawidłową kontynuację i numerację. W tym przykładzie ustawiliśmy początek sekcji na`SectionStart.Continuous` ponownie uruchom numerowanie stron. Dbamy również o to, aby szerokość, wysokość i orientacja strony odpowiadały ostatniej sekcji dokumentu docelowego.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Krok 4: Zmodyfikuj formatowanie akapitu

 Aby zachować prawidłowe formatowanie, przejrzyj wszystkie akapity w dokumencie źródłowym i ustaw opcję`KeepWithNext`własność do`true`. Dzięki temu akapity pozostaną razem podczas procesu dołączania.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Krok 5: Dołącz dokument źródłowy do dokumentu docelowego

 Użyj`AppendDocument` metoda dokumentu docelowego polegająca na dołączeniu zmodyfikowanego dokumentu źródłowego do dokumentu docelowego, zachowując formatowanie źródłowe.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 6: Zapisz dokument docelowy

Na koniec zapisz zmodyfikowany dokument docelowy za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

To kończy implementację dołączania dokumentu z różnymi ustawieniami ustawień strony przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla różnych ustawień strony przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ustaw dokument źródłowy tak, aby był kontynuowany bezpośrednio po zakończeniu dokumentu docelowego.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Rozpocznij ponownie numerowanie stron na początku dokumentu źródłowego.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	//Aby mieć pewność, że tak się nie stanie, gdy dokument źródłowy ma inne ustawienia ustawień strony, upewnij się, że
	// ustawienia są identyczne w ostatniej sekcji dokumentu docelowego.
	// Jeżeli w dokumencie źródłowym znajdują się dalsze ciągłe sekcje,
	// należy to powtórzyć dla tych sekcji.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Iteruj po wszystkich sekcjach dokumentu źródłowego.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```