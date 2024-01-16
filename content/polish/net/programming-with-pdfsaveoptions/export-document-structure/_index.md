---
title: Eksportuj strukturę dokumentu Word do dokumentu PDF
linktitle: Eksportuj strukturę dokumentu Word do dokumentu PDF
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący eksportowania struktury dokumentu Word do dokumentu PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/export-document-structure/
---

Ten artykuł zawiera przewodnik krok po kroku dotyczący korzystania z funkcji Eksportuj strukturę dokumentu programu Word do dokumentu PDF w Aspose.Words dla .NET. Szczegółowo wyjaśnimy każdą część kodu. Pod koniec tego samouczka będziesz w stanie zrozumieć, jak wyeksportować strukturę dokumentu i wygenerować plik PDF z widoczną strukturą dokumentu.

Zanim zaczniesz, upewnij się, że w swoim projekcie zainstalowałeś i skonfigurowałeś bibliotekę Aspose.Words for .NET. Bibliotekę i instrukcje instalacji można znaleźć na stronie internetowej Aspose.

## Krok 1: Zdefiniuj katalog dokumentów

 Na początek musisz zdefiniować ścieżkę do katalogu, w którym znajdują się Twoje dokumenty. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Prześlij dokument

Następnie musimy załadować dokument, który chcemy przetworzyć. W tym przykładzie zakładamy, że dokument nazywa się „Paragraphs.docx” i znajduje się w określonym katalogu dokumentów.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Krok 3: Skonfiguruj opcje zapisywania jako PDF

 Aby wyeksportować strukturę dokumentu i wyświetlić ją w panelu nawigacyjnym „Zawartość” programu Adobe Acrobat Pro podczas edycji pliku PDF, musimy skonfigurować`PdfSaveOptions` obiekt z`ExportDocumentStructure` właściwość ustawiona na`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Krok 4: Zapisz dokument jako plik PDF ze strukturą dokumentu

Wreszcie możemy zapisać dokument w formacie PDF, korzystając z wcześniej skonfigurowanych opcji zapisywania.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

To wszystko ! Pomyślnie wyeksportowałeś strukturę dokumentu i wygenerowałeś plik PDF z widoczną strukturą dokumentu za pomocą Aspose.Words dla .NET.

### Przykładowy kod źródłowy do eksportowania struktury dokumentu za pomocą Aspose.Words dla .NET


```csharp

            // Ścieżka do katalogu dokumentów.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // Rozmiar pliku zostanie zwiększony, a struktura będzie widoczna w panelu nawigacyjnym „Zawartość”.
            // programu Adobe Acrobat Pro podczas edycji pliku .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## Wniosek

W tym samouczku wyjaśniliśmy, jak wyeksportować strukturę dokumentu Word do dokumentu PDF za pomocą Aspose.Words dla .NET. Wykonując opisane czynności, możesz łatwo wygenerować plik PDF z widoczną strukturą dokumentu, co ułatwi nawigację i przeszukiwanie dokumentu. Skorzystaj z funkcji Aspose.Words dla .NET, aby wyeksportować strukturę dokumentów programu Word i utworzyć dobrze zorganizowane pliki PDF.

### Często Zadawane Pytania

#### P: Na czym polega eksport struktury dokumentu Word do dokumentu PDF?
Odp.: Eksportowanie struktury dokumentu Word do dokumentu PDF powoduje utworzenie pliku PDF z widoczną strukturą dokumentu. Struktura dokumentu zwykle obejmuje takie elementy, jak nagłówki, sekcje, akapity i inne uporządkowane elementy dokumentu. Struktura ta może być przydatna do nawigacji i wyszukiwania w dokumencie PDF.

#### P: Jak mogę wyeksportować strukturę dokumentu Word do dokumentu PDF przy użyciu Aspose.Words dla .NET?
Odp.: Aby wyeksportować strukturę dokumentu Word do dokumentu PDF przy użyciu Aspose.Words dla .NET, wykonaj następujące kroki:

 Utwórz instancję`Document` class określająca ścieżkę do dokumentu programu Word.

 Utwórz instancję`PdfSaveOptions` klasę i ustaw`ExportDocumentStructure`własność do`true`. Spowoduje to wyeksportowanie struktury dokumentu i uczyni ją widoczną w panelu nawigacyjnym „Zawartość” programu Adobe Acrobat Pro podczas edycji pliku PDF.

 Użyj`Save` metoda`Document`class, aby zapisać dokument w formacie PDF, określając opcje zapisywania.

#### P: Jak mogę wyświetlić strukturę dokumentu PDF za pomocą programu Adobe Acrobat Pro?
Odp.: Aby wyświetlić strukturę dokumentu PDF w programie Adobe Acrobat Pro, wykonaj następujące kroki:

Otwórz dokument PDF w programie Adobe Acrobat Pro.

Na lewym pasku nawigacyjnym kliknij ikonę „Treść”, aby wyświetlić panel nawigacyjny „Treść”.

W panelu nawigacyjnym „Treść” zobaczysz strukturę dokumentu z nagłówkami, sekcjami i innymi elementami strukturalnymi.