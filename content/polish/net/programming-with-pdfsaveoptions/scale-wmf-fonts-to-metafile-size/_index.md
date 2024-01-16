---
title: Zmniejsz rozmiar pliku PDF za pomocą skalowania czcionek Wmf do rozmiaru metapliku
linktitle: Zmniejsz rozmiar pliku PDF za pomocą skalowania czcionek Wmf do rozmiaru metapliku
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący zmniejszania rozmiaru pliku PDF za pomocą skalowania czcionek wmf do rozmiaru metapliku podczas konwersji do formatu PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Ten artykuł zawiera przewodnik krok po kroku dotyczący zmniejszania rozmiaru pliku PDF za pomocą funkcji skalowania czcionek wmf do rozmiaru metapliku w Aspose.Words dla .NET. Szczegółowo wyjaśnimy każdą część kodu. Pod koniec tego samouczka będziesz mógł zrozumieć, jak włączyć lub wyłączyć skalowanie czcionek WMF podczas konwersji do formatu PDF.

Zanim zaczniesz, upewnij się, że w swoim projekcie zainstalowałeś i skonfigurowałeś bibliotekę Aspose.Words for .NET. Bibliotekę i instrukcje instalacji można znaleźć na stronie internetowej Aspose.

## Krok 1: Zdefiniuj katalog dokumentów

 Na początek musisz zdefiniować ścieżkę do katalogu, w którym znajdują się Twoje dokumenty. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Prześlij dokument

Następnie musimy załadować dokument, który chcemy przetworzyć. W tym przykładzie zakładamy, że dokument nazywa się „WMF z tekstem.docx” i znajduje się w określonym katalogu dokumentów.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Krok 3: Skonfiguruj opcje renderowania metapliku

 Aby włączyć lub wyłączyć skalowanie czcionek WMF do rozmiaru metapliku, musimy skonfigurować`MetafileRenderingOptions`obiekt. W tym przykładzie wyłączamy skalowanie czcionek, ustawiając opcję`ScaleWmfFontsToMetafileSize`własność do`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Krok 4: Skonfiguruj opcje zapisywania jako PDF z opcjami renderowania metaplików

Na koniec możemy skonfigurować opcje zapisywania do pliku PDF, korzystając z skonfigurowanych wcześniej opcji renderowania metaplików.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Krok 5: Zapisz dokument jako plik PDF z opcjami renderowania metaplików

Zapisz dokument w formacie PDF, korzystając z wcześniej skonfigurowanych opcji zapisu.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

To wszystko ! Pomyślnie włączyłeś lub wyłączyłeś skalowanie czcionek WMF do rozmiaru metapliku podczas konwersji

dokument PDF przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy do skalowania czcionek WMF do rozmiaru metapliku za pomocą Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Jeśli Aspose.Words nie może poprawnie renderować niektórych rekordów metaplików do grafiki wektorowej
	// następnie Aspose.Words renderuje ten metaplik do postaci bitmapy.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Wniosek

tym samouczku wyjaśniliśmy, jak włączyć lub wyłączyć zmianę rozmiaru czcionek WMF do rozmiaru metapliku w dokumencie PDF przy użyciu Aspose.Words dla .NET. Wykonując opisane kroki, możesz łatwo kontrolować, czy podczas konwersji do dokumentu PDF należy zmieniać rozmiar czcionek WMF, aby dopasować je do rozmiaru metapliku. Może to pomóc w zmniejszeniu rozmiaru wygenerowanego pliku PDF i poprawie wydajności renderowania. Pamiętaj, aby określić poprawną ścieżkę do dokumentów i odpowiednio skonfigurować opcje renderowania metaplików.

### Często Zadawane Pytania

#### P: Na czym polega zmiana rozmiaru czcionek WMF do rozmiaru metapliku w dokumencie PDF?
Odp.: Zmiana rozmiaru czcionek WMF do rozmiaru metapliku w dokumencie PDF to funkcja określająca, czy czcionki WMF powinny być skalowane w celu dopasowania do rozmiaru metapliku podczas konwersji do dokumentu PDF. Gdy ta funkcja jest włączona, czcionki WMF są skalowane w celu dopasowania do rozmiaru metapliku, co może zmniejszyć rozmiar wygenerowanego dokumentu PDF.

#### P: Jak mogę użyć Aspose.Words dla .NET, aby włączyć lub wyłączyć zmianę rozmiaru czcionek WMF do rozmiaru metapliku w dokumencie PDF?
O: Aby włączyć lub wyłączyć zmianę rozmiaru czcionek WMF do rozmiaru metapliku w dokumencie PDF przy użyciu Aspose.Words dla .NET, wykonaj następujące kroki:

 Ustaw ścieżkę katalogu, w którym znajdują się Twoje dokumenty, zastępując`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

 Załaduj dokument, który chcesz przetworzyć za pomocą`Document` class i określ ścieżkę do dokumentu programu Word w określonym katalogu dokumentów.

 Skonfiguruj opcje renderowania metapliku, tworząc instancję pliku`MetafileRenderingOptions` klasę i ustawienie`ScaleWmfFontsToMetafileSize`własność do`true` aby włączyć skalowanie czcionek WMF do rozmiaru metapliku lub do`false` aby wyłączyć tę funkcję.

 Skonfiguruj opcje zapisywania jako PDF, tworząc instancję pliku`PdfSaveOptions` class i przy użyciu skonfigurowanych wcześniej opcji renderowania metaplików.

 Zapisz dokument w formacie PDF za pomocą`Save` metoda`Document` class określając ścieżkę i opcje zapisu.

#### P: Jakie są korzyści ze zmiany rozmiaru czcionek WMF na rozmiar metapliku w dokumencie PDF?
Odp.: Zalety zmiany rozmiaru czcionek WMF do rozmiaru metapliku w dokumencie PDF to:

Zmniejszanie rozmiaru pliku PDF: Zmiana rozmiaru czcionek WMF do rozmiaru metapliku może zmniejszyć rozmiar wygenerowanego dokumentu PDF, dostosowując rozmiar czcionki do potrzeb metapliku.

Poprawiona wydajność: Dostosowując rozmiar czcionek WMF do wymiarów metapliku, renderowanie dokumentu PDF może być szybsze i wydajniejsze.