---
title: Optymalizuj rozmiar pliku PDF, pomijając osadzone czcionki Arial i Times Roman
linktitle: Optymalizuj rozmiar pliku PDF, pomijając osadzone czcionki Arial i Times Roman
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący generowania zoptymalizowanego pliku PDF bez osadzania czcionek Arial i Times Roman za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

tym artykule znajduje się przewodnik krok po kroku dotyczący korzystania z tej funkcji w celu optymalizacji rozmiaru pliku PDF poprzez pominięcie osadzonych czcionek Arial i Times Roman na rzecz rozmiaru metapliku w Aspose.Words dla .NET. Szczegółowo wyjaśnimy każdą część kodu. Pod koniec tego samouczka będziesz mógł zrozumieć, jak skonfigurować opcję trybu osadzania czcionek w dokumencie i wygenerować plik PDF bez osadzania czcionek Arial i Times Roman.

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

## Krok 3: Skonfiguruj opcje zapisywania jako PDF z osadzaniem czcionek

 Aby pominąć osadzanie czcionek Arial i Times Roman w wygenerowanym pliku PDF, musimy skonfigurować`PdfSaveOptions` obiekt i ustaw`FontEmbeddingMode`własność do`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Krok 4: Zapisz dokument w formacie PDF bez osadzonych czcionek

Wreszcie możemy zapisać dokument w formacie PDF, korzystając z wcześniej skonfigurowanych opcji zapisywania.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

To wszystko ! Pomyślnie wygenerowałeś plik PDF bez osadzania czcionek Arial i Times Roman przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy umożliwiający pominięcie osadzonych czcionek Arial i Times Roman przy rozmiarze metapliku za pomocą Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Wniosek

tym samouczku wyjaśniliśmy, jak wyłączyć osadzanie czcionek Arial i Times Roman w dokumencie PDF przy użyciu Aspose.Words dla .NET. Wykonując opisane czynności, możesz wygenerować plik PDF bez osadzania tych konkretnych czcionek, co może pomóc zmniejszyć rozmiar pliku i zapewnić lepszą zgodność dokumentów na różnych platformach. Podczas korzystania z tej funkcji należy wziąć pod uwagę konsekwencje wyłączenia osadzania czcionek. Zachęcamy do poznania większej liczby funkcji Aspose.Words dla .NET, aby zoptymalizować generowanie plików PDF.

### Często Zadawane Pytania

#### P: Co uniemożliwia osadzanie czcionek Arial i Times Roman w dokumencie PDF i dlaczego jest to ważne?
Odp.: Wyłączenie osadzania czcionek Arial i Times Roman w dokumencie PDF polega na nieuwzględnianiu tych czcionek w wygenerowanym pliku PDF. Może to być ważne, aby zmniejszyć rozmiar pliku PDF poprzez unikanie dołączania czcionek, które są już powszechnie dostępne w systemach czytników plików PDF. Może również pomóc zapewnić lepszą kompatybilność i spójny wygląd dokumentu PDF na różnych urządzeniach i platformach.

#### P: Jak mogę skonfigurować Aspose.Words dla .NET tak, aby nie osadzał czcionek Arial i Times Roman w dokumencie PDF?
O: Aby skonfigurować Aspose.Words dla .NET tak, aby nie osadzał czcionek Arial i Times Roman w dokumencie PDF, wykonaj następujące kroki:

 Ustaw ścieżkę katalogu, w którym znajdują się Twoje dokumenty, zastępując`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

 Załaduj dokument, który chcesz przetworzyć za pomocą`Document` class i określoną ścieżkę dokumentu.

 Utwórz instancję`PdfSaveOptions` klasę i ustaw`FontEmbeddingMode`własność do`PdfFontEmbeddingMode.EmbedAll`. Spowoduje to osadzenie w wygenerowanym pliku PDF wszystkich czcionek z wyjątkiem Arial i Times Roman.

 Użyj`Save` metoda`Document` obiekt, aby zapisać dokument w formacie PDF, określając skonfigurowane wcześniej opcje zapisu.

#### P: Jakie są korzyści z wyłączenia osadzania czcionek Arial i Times Roman w dokumencie PDF?
O: Korzyści z wyłączenia osadzania czcionek Arial i Times Roman w dokumencie PDF są następujące:

Zmniejszanie rozmiaru pliku PDF: Unikając osadzania powszechnie dostępnych czcionek, takich jak Arial i Times Roman, można zmniejszyć rozmiar pliku PDF, co ułatwia przechowywanie, udostępnianie i przesyłanie plików.

Lepsza kompatybilność: Używając czcionek powszechnie dostępnych w systemach czytników plików PDF, zapewniasz lepszą kompatybilność i wygląd dokumentu na różnych urządzeniach i platformach.

#### P: Jakie są konsekwencje wyłączenia osadzania czcionek Arial i Times Roman w dokumencie PDF?
O: Konsekwencje wyłączenia osadzania czcionek Arial i Times Roman w dokumencie PDF są następujące:

Inny wygląd: Jeżeli w systemie, w którym otwierany jest plik PDF, nie są dostępne czcionki Arial i Times Roman, zostaną użyte czcionki zastępcze, co może skutkować wyglądem innym niż zamierzony.

Problemy z czytelnością: użyte czcionki zastępcze mogą nie być tak czytelne jak czcionki oryginalne, co może mieć wpływ na czytelność dokumentu.