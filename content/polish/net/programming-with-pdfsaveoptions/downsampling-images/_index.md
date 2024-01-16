---
title: Zmniejsz rozmiar dokumentu PDF za pomocą próbkowania obrazów w dół
linktitle: Zmniejsz rozmiar dokumentu PDF za pomocą próbkowania obrazów w dół
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zmniejszyć rozmiar dokumentu PDF poprzez próbkowanie obrazów w dół podczas konwersji do formatu PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/downsampling-images/
---

W tym samouczku przeprowadzimy Cię przez kolejne kroki, aby zmniejszyć rozmiar dokumentu PDF za pomocą próbkowania obrazów w dół podczas konwersji do formatu PDF za pomocą Aspose.Words dla .NET. Zmniejsza to rozmiar wygenerowanego pliku PDF. Wykonaj poniższe kroki:

## Krok 1: Ładowanie dokumentu

Zacznij od przesłania dokumentu, który chcesz przekonwertować do formatu PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Pamiętaj, aby podać poprawną ścieżkę do swojego dokumentu.

## Krok 2: Skonfiguruj opcje zapisywania plików PDF

Utwórz instancję klasy PdfSaveOptions i ustaw opcje zmniejszania obrazu:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 The`Resolution` Właściwość określa docelową rozdzielczość obrazów i`ResolutionThreshold`Właściwość określa minimalną rozdzielczość, poniżej której obrazy nie będą zmniejszane.

## Krok 3: Konwertuj dokument na format PDF

 Użyj`Save` metoda konwersji dokumentu do formatu PDF określająca opcje zapisu:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Upewnij się, że podałeś poprawną ścieżkę do zapisania przekonwertowanego pliku PDF.

### Przykładowy kod źródłowy do próbkowania obrazów przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Możemy ustawić minimalny próg próbkowania w dół.
	// Ta wartość zapobiegnie próbkowaniu drugiego obrazu w dokumencie wejściowym.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Wykonując poniższe kroki, możesz łatwo zmniejszyć rozdzielczość obrazu podczas konwersji do formatu PDF za pomocą Aspose.Words dla .NET.

## Wniosek

tym samouczku wyjaśniliśmy, jak zmniejszyć rozmiar dokumentu PDF za pomocą próbkowania obrazu podczas konwersji do formatu PDF za pomocą Aspose.Words dla .NET. Wykonując opisane kroki, możesz łatwo zmniejszyć rozdzielczość obrazów i rozmiar generowanego pliku PDF. Pamiętaj, aby określić poprawną ścieżkę do dokumentu i odpowiednio skonfigurować opcje próbkowania obrazu. Zmniejszenie rozmiaru pliku PDF ułatwia udostępnianie, przechowywanie i szybkie ładowanie pliku na różnych platformach. Ciesz się korzyściami płynącymi ze zmniejszania rozmiaru dokumentu PDF poprzez próbkowanie obrazu przy użyciu Aspose.Words dla .NET.

### Często Zadawane Pytania

#### P: Na czym polega zmniejszenie rozmiaru dokumentu PDF przy próbkowaniu obrazu?
Odp.: Zmniejszanie rozmiaru dokumentu PDF za pomocą próbkowania obrazu polega na zmniejszeniu rozmiaru wygenerowanego pliku PDF poprzez zmniejszenie rozdzielczości obrazów podczas konwersji do formatu PDF. Optymalizuje to wykorzystanie przestrzeni dyskowej i ułatwia udostępnianie i przesyłanie pliku PDF.

#### P: Jak mogę zmniejszyć rozmiar dokumentu PDF za pomocą próbkowania obrazu przy użyciu Aspose.Words dla .NET?
Odp.: Aby zmniejszyć rozmiar dokumentu PDF za pomocą próbkowania obrazu przy użyciu Aspose.Words dla .NET, wykonaj następujące kroki:

 Ustaw ścieżkę katalogu, w którym znajdują się Twoje dokumenty, zastępując`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

 Załaduj dokument, który chcesz przekonwertować do formatu PDF za pomocą`Document` class i określ ścieżkę do dokumentu w określonym katalogu dokumentów.

 Skonfiguruj opcje zapisywania jako PDF, tworząc instancję pliku`PdfSaveOptions` class i ustawienie opcji próbkowania obrazu za pomocą`DownsampleOptions` nieruchomość. Możesz określić docelową rozdzielczość obrazów za pomocą`Resolution` i ustaw minimalny próg rozdzielczości, powyżej którego obrazy nie będą zmniejszane przy użyciu opcji`ResolutionThreshold` nieruchomość.

 Zapisz dokument w formacie PDF za pomocą`Save` metoda`Document` class określając ścieżkę i opcje zapisu.

#### P: Jakie są korzyści ze zmniejszenia rozmiaru dokumentu PDF za pomocą próbkowania obrazu?
Odp.: Korzyści ze zmniejszenia rozmiaru dokumentu PDF za pomocą próbkowania obrazu są następujące:

Zmniejszony rozmiar pliku PDF: Próbkowanie obrazu zmniejsza rozdzielczość obrazów w dokumencie PDF, co powoduje znaczne zmniejszenie rozmiaru pliku PDF. Ułatwia to udostępnianie i przesyłanie pliku, zwłaszcza pocztą elektroniczną lub online.

Optymalizacja przestrzeni dyskowej: Zmniejszenie rozmiaru pliku PDF pomaga zoptymalizować wykorzystanie przestrzeni dyskowej, zwłaszcza gdy masz wiele plików PDF zawierających obrazy o wysokiej rozdzielczości.

Ulepszenia wydajności: mniejsze pliki PDF ładują się szybciej i można je szybciej otwierać i przeglądać na różnych urządzeniach.