---
title: Załaduj zakres stron pliku PDF
linktitle: Załaduj zakres stron pliku PDF
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący ładowania określonego zakresu stron PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

W tym samouczku przeprowadzimy Cię przez proces ładowania określonego zakresu stron z dokumentu PDF przy użyciu Aspose.Words dla .NET. Wykonaj poniższe kroki:

## Krok 1: Ładowanie zakresu stron PDF

Użyj poniższego kodu, aby załadować określony zakres stron z dokumentu PDF:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 W tym przykładzie ładujemy pierwszą stronę dokumentu PDF. Możesz zmienić wartości`PageIndex` I`PageCount` do żądanego zakresu stron.

## Krok 2: Zapisanie dokumentu

 Na koniec możesz zapisać dokument zawierający określony zakres stron za pomocą`Save` metoda:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Pamiętaj, aby podać poprawną ścieżkę do zapisania edytowanego dokumentu.

To wszystko ! Załadowałeś teraz określony zakres stron z dokumentu PDF przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Załaduj zakres stron pliku PDF przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Pamiętaj, aby podać poprawną ścieżkę do katalogu swoich dokumentów PDF.



