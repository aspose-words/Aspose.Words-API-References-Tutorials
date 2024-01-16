---
title: Dołącz dokument
linktitle: Dołącz dokument
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dołączyć zawartość jednego dokumentu do drugiego za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/append-document/
---

W tym samouczku wyjaśniono, jak używać Aspose.Words dla .NET do dołączania zawartości jednego dokumentu do drugiego. Dostarczony kod źródłowy pokazuje, jak otwierać dokumenty źródłowe i docelowe, importować i dołączać sekcje z dokumentu źródłowego do dokumentu docelowego.

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

## Krok 3: Dołącz sekcje z dokumentu źródłowego do dokumentu docelowego

 Przejdź przez wszystkie sekcje w dokumencie źródłowym i zaimportuj każdą sekcję do dokumentu docelowego za pomocą`ImportNode` metoda. Następnie dołącz zaimportowaną sekcję do dokumentu docelowego.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Krok 4: Zapisz dokument docelowy

 Na koniec zapisz zmodyfikowany dokument docelowy za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

To kończy implementację dołączania dokumentu przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Dołącz dokument przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Przejdź przez wszystkie sekcje dokumentu źródłowego.
	//Węzły sekcji są bezpośrednimi dziećmi węzła Dokument, więc możemy po prostu wyliczyć Dokument.
	foreach (Section srcSection in srcDoc)
	{
		// Ponieważ kopiujemy sekcję z jednego dokumentu do drugiego,
		// wymagane jest zaimportowanie węzła Sekcja do dokumentu docelowego.
		// Dostosowuje to wszelkie odniesienia specyficzne dla dokumentu do stylów, list itp.
		//
		// Importowanie węzła powoduje utworzenie kopii oryginalnego węzła, ale kopię
		// ss jest gotowy do wstawienia do dokumentu docelowego.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Teraz można dołączyć nowy węzeł sekcji do dokumentu docelowego.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```