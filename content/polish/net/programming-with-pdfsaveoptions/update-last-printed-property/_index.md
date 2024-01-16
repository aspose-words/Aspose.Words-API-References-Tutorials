---
title: Zaktualizuj ostatnio wydrukowaną właściwość w dokumencie PDF
linktitle: Zaktualizuj ostatnio wydrukowaną właściwość w dokumencie PDF
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący aktualizacji właściwości „Ostatni wydruk” podczas konwersji do formatu PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Ten artykuł zawiera przewodnik krok po kroku dotyczący korzystania z właściwości „Ostatni wydruk” w funkcji aktualizacji dokumentu PDF w Aspose.Words dla .NET. Szczegółowo wyjaśnimy każdą część kodu. Pod koniec tego samouczka będziesz mógł zrozumieć, jak skonfigurować opcję aktualizacji właściwości „Ostatni wydruk” podczas konwersji do formatu PDF.

Zanim zaczniesz, upewnij się, że w swoim projekcie zainstalowałeś i skonfigurowałeś bibliotekę Aspose.Words for .NET. Bibliotekę i instrukcje instalacji można znaleźć na stronie internetowej Aspose.

## Krok 1: Zdefiniuj katalog dokumentów

 Na początek musisz zdefiniować ścieżkę do katalogu, w którym znajdują się Twoje dokumenty. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Prześlij dokument

Następnie musimy załadować dokument, który chcemy przetworzyć. W tym przykładzie zakładamy, że dokument nazywa się „Rendering.docx” i znajduje się w określonym katalogu dokumentów.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Skonfiguruj opcje zapisu jako PDF ze zaktualizowaną właściwością „Ostatni wydruk”.

 Aby umożliwić aktualizację właściwości „Ostatni wydruk” podczas konwersji do formatu PDF, musimy skonfigurować plik`PdfSaveOptions` obiekt i ustaw`UpdateLastPrintedProperty`własność do`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Krok 4: Zapisz dokument jako plik PDF z aktualizacją właściwości „Ostatni wydruk”.

Wreszcie możemy zapisać dokument w formacie PDF, korzystając z wcześniej skonfigurowanych opcji zapisywania.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

To wszystko ! Pomyślnie włączyłeś aktualizację właściwości „Ostatni wydruk” podczas konwersji dokumentu do formatu PDF przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy aktualizacji właściwości „Ostatni wydruk” za pomocą Aspose.Words dla .NET


```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Wniosek

W tym samouczku wyjaśniliśmy, jak zaktualizować właściwość „Ostatni wydruk” w dokumencie PDF przy użyciu Aspose.Words dla .NET. Wykonując podane kroki, możesz łatwo skonfigurować opcję aktualizacji właściwości „Ostatni wydruk” podczas konwersji dokumentu do formatu PDF. Użyj tej funkcji, aby śledzić wykorzystanie dokumentów i powiązane informacje.

### Często Zadawane Pytania

#### P: Jaka jest właściwość „Ostatni wydruk” w dokumencie PDF?
Odp.: Właściwość „Ostatni wydruk” w dokumencie PDF odnosi się do daty i godziny ostatniego wydrukowania dokumentu. Ta właściwość może być przydatna do śledzenia informacji o użyciu dokumentów i zarządzaniu nimi.

#### P: Jak mogę zaktualizować właściwość „Ostatni wydruk” w dokumencie PDF za pomocą Aspose.Words dla .NET?
Odp.: Aby zaktualizować właściwość „Ostatni wydruk” w dokumencie PDF za pomocą Aspose.Words dla .NET, wykonaj następujące kroki:

 Utwórz instancję`Document` class określająca ścieżkę do dokumentu programu Word.

 Utwórz instancję`PdfSaveOptions` klasę i ustaw`UpdateLastPrintedProperty`własność do`true` aby włączyć aktualizację właściwości „Ostatni wydruk”.

 Użyj`Save` metoda`Document`class, aby zapisać dokument w formacie PDF, określając opcje zapisywania.

#### P: Jak mogę sprawdzić, czy właściwość „Ostatni wydruk” została zaktualizowana w wygenerowanym dokumencie PDF?
O: Możesz sprawdzić, czy właściwość „Ostatni wydruk” w wygenerowanym dokumencie PDF została zaktualizowana, otwierając plik PDF w kompatybilnej przeglądarce plików PDF, takiej jak Adobe Acrobat Reader, i przeglądając informacje o dokumencie. Data i godzina ostatniego wydruku powinna odpowiadać dacie i godzinie wygenerowania dokumentu PDF.
