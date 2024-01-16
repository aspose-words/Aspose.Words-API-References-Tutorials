---
title: Kompresja obrazu w dokumencie PDF
linktitle: Kompresja obrazu w dokumencie PDF
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący kompresji obrazów w dokumencie PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/image-compression/
---

Ten artykuł zawiera przewodnik krok po kroku dotyczący korzystania z funkcji kompresji obrazu w dokumencie PDF w Aspose.Words dla .NET. Szczegółowo wyjaśnimy każdą część kodu. Pod koniec tego samouczka będziesz w stanie zrozumieć, jak kompresować obrazy w dokumencie i generować plik PDF z odpowiednią kompresją obrazu.

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

## Krok 3: Skonfiguruj opcje zapisywania jako PDF z kompresją obrazu

 Aby skompresować obrazy podczas konwersji do formatu PDF, musimy skonfigurować plik`PdfSaveOptions` obiekt. W razie potrzeby możemy ustawić typ kompresji obrazu, jakość JPEG i inne opcje zgodności z PDF.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Krok 4: Zapisz dokument jako plik PDF z kompresją obrazu

Wreszcie możemy zapisać dokument w formacie PDF, korzystając z wcześniej skonfigurowanych opcji zapisywania.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Krok 5: Skonfiguruj opcje zapisywania w formacie PDF/A-2u z kompresją obrazu

Jeśli chcesz wygenerować plik PDF zgodny z formatem PDF/A-2u z kompresją obrazu, możesz skonfigurować dodatkowe opcje zapisywania.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Użyj kompresji JPEG z jakością 50%, aby zmniejszyć rozmiar pliku.
};
```

## Krok 6: Zapisz dokument jako PDF/A-2u z kompresją obrazu

Zapisz dokument w formacie PDF/A-2u korzystając z dodatkowych opcji zapisu skonfigurowanych wcześniej.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



To wszystko ! Pomyślnie skompresowałeś obrazy w dokumencie i wygenerowałeś plik PDF z odpowiednią kompresją obrazu przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy do kompresji obrazów za pomocą Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Użyj kompresji JPEG przy jakości 50%, aby zmniejszyć rozmiar pliku.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Wniosek

W tym samouczku wyjaśniliśmy, jak kompresować obrazy w dokumencie PDF za pomocą Aspose.Words dla .NET. Wykonując opisane kroki, możesz łatwo zmniejszyć rozmiar obrazów w dokumencie PDF i wygenerować plik PDF z odpowiednią kompresją obrazu. Użyj funkcji kompresji obrazu Aspose.Words dla .NET, aby zoptymalizować rozmiar dokumentów PDF, zachowując jednocześnie jakość obrazu.

### Często Zadawane Pytania

#### P: Co to jest kompresja obrazu w dokumencie PDF?
Odp.: Kompresja obrazów w dokumencie PDF polega na zmniejszeniu rozmiaru obrazów zawartych w dokumencie PDF w celu zmniejszenia całkowitego rozmiaru pliku PDF. Zmniejsza to potrzebną przestrzeń dyskową i poprawia wydajność podczas ładowania i przeglądania pliku PDF.

#### P: Jak mogę skompresować obrazy w dokumencie PDF za pomocą Aspose.Words dla .NET?
Odp.: Aby skompresować obrazy w dokumencie PDF za pomocą Aspose.Words dla .NET, wykonaj następujące kroki:

 Utwórz instancję`Document` class określająca ścieżkę do dokumentu programu Word.

 Utwórz instancję`PdfSaveOptions` klasę i ustaw`ImageCompression`własność do`PdfImageCompression.Jpeg` używać kompresji JPEG.

W zależności od potrzeb możesz także ustawić inne opcje kompresji obrazu, takie jak jakość JPEG.

 Użyj`Save` metoda`Document`class, aby zapisać dokument w formacie PDF, określając opcje zapisywania.

#### P: Jaka jest różnica między standardową kompresją obrazu a kompresją obrazu PDF/A-2u?
Odp.: Standardowa kompresja obrazu zmniejsza rozmiar obrazów w dokumencie PDF, zachowując jednocześnie pola formularzy. Zmniejsza to całkowity rozmiar pliku PDF bez pogarszania funkcjonalności pól formularza.

Kompresja obrazu za pomocą formatu PDF/A-2u to dodatkowa opcja, która umożliwia wygenerowanie pliku PDF zgodnego ze standardem PDF/A-2u przy zastosowaniu kompresji obrazu. PDF/A-2u to standard ISO dla archiwalnych dokumentów PDF, gwarantujący długoterminową ochronę dokumentów.
