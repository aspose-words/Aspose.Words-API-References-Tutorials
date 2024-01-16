---
title: Eksportuj zakładki nagłówka stopki dokumentu Word do dokumentu PDF
linktitle: Eksportuj zakładki nagłówka stopki dokumentu Word do dokumentu PDF
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący eksportowania zakładek nagłówka dokumentu Word do zakładek dokumentu PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Ten artykuł zawiera przewodnik krok po kroku dotyczący eksportowania zakładek nagłówka dokumentu Word do funkcji dokumentu PDF za pomocą Aspose.Words dla .NET. Szczegółowo wyjaśnimy każdą część kodu. Pod koniec tego samouczka będziesz w stanie zrozumieć, jak wyeksportować zakładki z nagłówków i stopek dokumentu oraz wygenerować plik PDF z odpowiednimi zakładkami.

Zanim zaczniesz, upewnij się, że w swoim projekcie zainstalowałeś i skonfigurowałeś bibliotekę Aspose.Words for .NET. Bibliotekę i instrukcje instalacji można znaleźć na stronie internetowej Aspose.

## Krok 1: Zdefiniuj katalog dokumentów

 Na początek musisz zdefiniować ścieżkę do katalogu, w którym znajdują się Twoje dokumenty. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Prześlij dokument

Następnie musimy załadować dokument, który chcemy przetworzyć. W tym przykładzie zakładamy, że dokument nosi nazwę „Zakładki w nagłówkach i stopkach.docx” i znajduje się w określonym katalogu dokumentów.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Krok 3: Skonfiguruj opcje zapisywania jako PDF

 Aby wyeksportować zakładki nagłówków i stopek, musimy skonfigurować plik`PdfSaveOptions` obiekt. W tym przykładzie ustawiliśmy domyślny poziom konspektu zakładki na 1, a tryb eksportu zakładek nagłówka i stopki na „Pierwszy”.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Krok 4: Zapisz dokument w formacie PDF z zakładkami nagłówków i stopek

Wreszcie możemy zapisać dokument w formacie PDF, korzystając z wcześniej skonfigurowanych opcji zapisywania.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

To wszystko ! Pomyślnie wyeksportowałeś zakładki nagłówka i stopki z dokumentu i wygenerowałeś plik PDF z odpowiednimi zakładkami przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy do eksportowania zakładek nagłówków i stopek za pomocą Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Wniosek

tym samouczku wyjaśniliśmy, jak eksportować zakładki nagłówków i stopek z dokumentu Word do dokumentu PDF za pomocą Aspose.Words dla .NET. Wyeksportowane zakładki umożliwiają łatwą nawigację i szybkie odwoływanie się do odpowiednich nagłówków i stopek w wygenerowanym dokumencie PDF. Wykonaj opisane kroki, aby wyeksportować zakładki nagłówka i stopki z dokumentu i wygenerować plik PDF z odpowiednimi zakładkami przy użyciu Aspose.Words dla .NET. Pamiętaj, aby określić poprawną ścieżkę do dokumentów i skonfigurować opcje zapisywania, jeśli to konieczne.

### Często Zadawane Pytania

### P: Na czym polega eksport zakładek nagłówków i stopek z dokumentu programu Word do dokumentu PDF?
Odp.: Eksportowanie zakładek nagłówków i stopek z dokumentu Word do dokumentu PDF to funkcja umożliwiająca przechowywanie i generowanie zakładek w dokumencie PDF na podstawie nagłówków i stopek. stopki oryginalnego dokumentu programu Word. Dzięki temu użytkownicy mogą szybko i łatwo poruszać się po dokumencie PDF, korzystając z zakładek odpowiadających nagłówkom i stopkom.

### P: Jak mogę używać Aspose.Words dla .NET do eksportowania zakładek nagłówków i stopek z dokumentu Word do dokumentu PDF?
O: Aby wyeksportować zakładki nagłówków i stopek z dokumentu Word do dokumentu PDF przy użyciu Aspose.Words dla .NET, wykonaj następujące kroki:

 Ustaw ścieżkę katalogu, w którym znajdują się Twoje dokumenty, zastępując`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

 Załaduj dokument, który chcesz przetworzyć za pomocą`Document` class i określ ścieżkę do dokumentu programu Word w określonym katalogu dokumentów.

 Skonfiguruj opcje zapisywania jako PDF, tworząc instancję pliku`PdfSaveOptions` class i ustawienie odpowiednich opcji zakładek nagłówka i stopki.

 Zapisz dokument w formacie PDF za pomocą`Save` metoda`Document` class określając ścieżkę i opcje zapisu.

### P: Jakie są korzyści z eksportowania zakładek nagłówków i stopek do dokumentu PDF?
O: Zalety eksportowania zakładek nagłówków i stopek do dokumentu PDF są następujące:

Łatwa nawigacja: Zakładki pozwalają użytkownikom łatwo poruszać się po dokumencie PDF, odwołując się do określonych nagłówków i stopek.

Skrócona instrukcja: Zakładki pozwalają użytkownikom szybko znaleźć odpowiednie sekcje dokumentu PDF na podstawie nagłówków i stopek.