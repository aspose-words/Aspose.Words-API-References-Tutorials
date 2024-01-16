---
title: Eksportuj właściwości niestandardowe do dokumentu PDF
linktitle: Eksportuj właściwości niestandardowe do dokumentu PDF
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak eksportować niestandardowe właściwości podczas konwersji dokumentów do formatu PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/custom-properties-export/
---

tym samouczku przeprowadzimy Cię przez kroki eksportowania niestandardowych właściwości dokumentu do dokumentu PDF przy użyciu Aspose.Words dla .NET. Eksportowanie niestandardowych właściwości umożliwia dołączenie dodatkowych informacji do wygenerowanego dokumentu PDF. Wykonaj poniższe kroki:

## Krok 1: Tworzenie dokumentu i dodawanie właściwości niestandardowych

Zacznij od utworzenia instancji klasy Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Krok 2: Dodaj właściwości niestandardowe
 Następnie dodaj żądane właściwości niestandardowe. Na przykład, aby dodać właściwość „Firma” o wartości „Aspose”, użyj metody`Add` metoda kolekcji CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Możesz dodać tyle właściwości niestandardowych, ile potrzeba.

## Krok 3: Ustaw opcje eksportu PDF

Utwórz instancję klasy PdfSaveOptions i określ sposób eksportowania właściwości niestandardowych:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Ta opcja kontroluje eksport niestandardowych właściwości podczas konwersji do formatu PDF.

## Krok 4: Konwertuj dokument na format PDF

 Użyj`Save` metoda konwersji dokumentu do formatu PDF określająca opcje konwersji:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Upewnij się, że podałeś poprawną ścieżkę do zapisania przekonwertowanego pliku PDF.

### Przykładowy kod źródłowy eksportu właściwości niestandardowych przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy do eksportowania niestandardowych właściwości z dokumentu przy użyciu Aspose.Words dla .NET:


```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Wykonując te kroki, możesz łatwo wyeksportować niestandardowe właściwości dokumentu podczas konwersji do formatu PDF za pomocą Aspose.Words dla .NET.


## Wniosek

W tym samouczku wyjaśniliśmy, jak eksportować niestandardowe właściwości z dokumentu do dokumentu PDF za pomocą Aspose.Words dla .NET. Wykonując opisane kroki, możesz łatwo dołączyć dodatkowe informacje do wygenerowanego dokumentu PDF, eksportując niestandardowe właściwości dokumentu. Skorzystaj z funkcji Aspose.Words dla .NET, aby personalizować i wzbogacać swoje dokumenty PDF poprzez eksport niestandardowych właściwości.

### Często Zadawane Pytania

#### P: Na czym polega eksportowanie niestandardowych właściwości do dokumentu PDF?
Odp.: Eksportowanie niestandardowych właściwości do dokumentu PDF umożliwia dodanie dodatkowych informacji do wygenerowanego dokumentu PDF. Właściwości niestandardowe to metadane specyficzne dla Twojego dokumentu, takie jak znaczniki, słowa kluczowe lub poświadczenia. Eksportując te niestandardowe właściwości, możesz udostępnić je użytkownikom podczas przeglądania dokumentu PDF.

#### P: Jak mogę wyeksportować niestandardowe właściwości dokumentu do dokumentu PDF przy użyciu Aspose.Words dla .NET?
O: Aby wyeksportować niestandardowe właściwości dokumentu do dokumentu PDF przy użyciu Aspose.Words dla .NET, wykonaj następujące kroki:

 Utwórz instancję`Document` klasa.

 Dodaj żądane właściwości niestandardowe za pomocą`CustomDocumentProperties` kolekcja. Na przykład użyj`Add` metodę dodania właściwości „Firma” o wartości „Aspose”.

 Utwórz instancję`PdfSaveOptions` klasę i określ sposób eksportowania właściwości niestandardowych za pomocą pliku`CustomPropertiesExport` nieruchomość. The`PdfCustomPropertiesExport.Standard` wartość eksportuje właściwości niestandardowe zgodnie z ustawieniami domyślnymi.

 Użyj`Save` metoda`Document` class, aby przekonwertować dokument do formatu PDF, określając opcje konwersji.

#### P: Jak mogę uzyskać dostęp do niestandardowych właściwości dokumentu PDF?
O: Aby uzyskać dostęp do niestandardowych właściwości dokumentu PDF, możesz użyć kompatybilnego czytnika PDF, który obsługuje przeglądanie właściwości dokumentu. Najpopularniejsze czytniki plików PDF, takie jak Adobe Acrobat Reader, zapewniają dostęp do metadanych i właściwości dokumentu PDF. Zazwyczaj opcje te można znaleźć w menu „Plik” lub klikając dokument prawym przyciskiem myszy i wybierając „Właściwości”.