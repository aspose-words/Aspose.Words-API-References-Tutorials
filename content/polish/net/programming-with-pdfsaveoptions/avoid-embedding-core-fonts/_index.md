---
title: Zmniejsz rozmiar pliku PDF, nie osadzając podstawowych czcionek
linktitle: Zmniejsz rozmiar pliku PDF, nie osadzając podstawowych czcionek
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zmniejszyć rozmiar pliku PDF, nie osadzając podstawowych czcionek podczas konwersji dokumentów programu Word do formatu PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

W tym samouczku przeprowadzimy Cię przez kroki, jak zmniejszyć rozmiar pliku PDF, nie osadzając podstawowych czcionek w Aspose.Words dla .NET. Ta funkcja pozwala kontrolować, czy podstawowe czcionki, takie jak Arial, Times New Roman itp. muszą być osadzone w pliku PDF podczas konwersji dokumentu Word. Wykonaj poniższe kroki:

## Krok 1: Ładowanie dokumentu

Zacznij od przesłania dokumentu programu Word, który chcesz przekonwertować do formatu PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Pamiętaj, aby podać poprawną ścieżkę do dokumentu programu Word.

## Krok 2: Ustaw opcje konwersji PDF

Utwórz instancję klasy PdfSaveOptions i włącz podstawowe unikanie osadzania czcionek:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Ta opcja określa, czy czcionki podstawowe powinny być osadzone w pliku PDF, czy nie.

## Krok 3: Konwertuj dokument na format PDF

 Użyj`Save` metoda konwersji dokumentu Word do formatu PDF poprzez określenie opcji konwersji:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Upewnij się, że podałeś poprawną ścieżkę do zapisania przekonwertowanego pliku PDF.

### Przykładowy kod źródłowy dla opcji Unikaj osadzania podstawowych czcionek przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy umożliwiający użycie tej funkcji w celu uniknięcia osadzania podstawowych czcionek w Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Wyjściowy plik PDF nie będzie osadzony w podstawowych czcionkach, takich jak Arial, Times New Roman itp.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Wykonując te kroki, możesz łatwo kontrolować, czy czcionki podstawowe powinny być osadzane w pliku PDF podczas konwertowania dokumentu Word za pomocą Aspose.Words dla .NET.


## Wniosek

tym samouczku wyjaśniliśmy, jak zmniejszyć rozmiar pliku PDF, nie osadzając podstawowych czcionek w Aspose.Words dla .NET. Ta funkcja pozwala kontrolować, czy czcionki podstawowe powinny być osadzane w pliku PDF podczas konwertowania dokumentu programu Word. Wykonując opisane czynności, możesz łatwo kontrolować osadzanie lub brak osadzania podstawowych czcionek, co może pomóc zmniejszyć rozmiar pliku PDF i zapewnić lepszą kompatybilność oraz spójny wygląd dokumentu na różnych urządzeniach i platformach. Nie zapomnij wziąć pod uwagę konsekwencji nieosadzenia czcionek podstawowych i poeksperymentować, aby upewnić się, że dokument będzie renderowany zgodnie z oczekiwaniami.

### Często Zadawane Pytania

#### P: Jaka jest opcja, aby nie osadzać podstawowych czcionek w pliku PDF i dlaczego jest to ważne?
O: Opcja nieosadzania czcionek podstawowych w pliku PDF określa, czy czcionki podstawowe, takie jak Arial, Times New Roman itp. muszą być osadzone w pliku PDF podczas konwersji dokumentu programu Word. Może to być ważne, aby zmniejszyć rozmiar pliku PDF poprzez unikanie dołączania czcionek powszechnie dostępnych w systemach czytników plików PDF. Może również pomóc zapewnić lepszą kompatybilność i spójny wygląd dokumentu PDF na różnych urządzeniach i platformach.

#### P: Jak mogę skonfigurować Aspose.Words dla .NET tak, aby nie osadzał podstawowych czcionek w pliku PDF?
O: Aby skonfigurować Aspose.Words dla .NET tak, aby nie osadzał podstawowych czcionek w pliku PDF, wykonaj następujące kroki:

 Ustaw ścieżkę katalogu, w którym znajdują się Twoje dokumenty, zastępując`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

 Załaduj dokument programu Word, który chcesz przekonwertować do formatu PDF, za pomocą`Document` class i określoną ścieżkę dokumentu.

 Utwórz instancję`PdfSaveOptions` klasę i ustaw`UseCoreFonts`własność do`true`. Pozwoli to uniknąć osadzania czcionek podstawowych w wygenerowanym pliku PDF.

 Użyj`Save` metoda`Document` obiekt, aby zapisać dokument w formacie PDF, określając skonfigurowane wcześniej opcje konwersji.

#### P: Jakie są korzyści z nieosadzania czcionek podstawowych w pliku PDF?
O: Korzyści z nieosadzania czcionek podstawowych w pliku PDF są następujące:

Zmniejszanie rozmiaru pliku PDF: Unikając osadzania powszechnie dostępnych czcionek, takich jak Arial, Times New Roman itp., można zmniejszyć rozmiar pliku PDF, co ułatwia przechowywanie, udostępnianie i przesyłanie plików.

Lepsza kompatybilność: używając podstawowych czcionek powszechnie dostępnych w systemach czytników plików PDF, zapewniasz lepszą kompatybilność i wygląd dokumentów na różnych urządzeniach i platformach.

#### P: Jakie są konsekwencje nieosadzenia czcionek podstawowych w pliku PDF?
O: Konsekwencje nieosadzenia czcionek podstawowych w pliku PDF są następujące:

Inny wygląd: Jeśli czcionki podstawowe nie są dostępne w systemie, w którym otwierany jest plik PDF, zostaną użyte czcionki zastępcze, co może skutkować wyglądem innym niż zamierzony.

Problemy z czytelnością: użyte czcionki zastępcze mogą nie być tak czytelne jak czcionki oryginalne, co może mieć wpływ na czytelność dokumentu.