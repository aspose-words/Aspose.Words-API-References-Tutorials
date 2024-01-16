---
title: Zmniejsz rozmiar pliku PDF, wyłączając osadzone czcionki
linktitle: Zmniejsz rozmiar pliku PDF, wyłączając osadzone czcionki
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zmniejszyć rozmiar pliku PDF, wyłączając osadzanie czcionek systemu Windows podczas konwersji dokumentów do formatu PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

W tym samouczku przeprowadzimy Cię przez etapy zmniejszania rozmiaru pliku PDF poprzez wyłączenie osadzania czcionek Windows w dokumencie PDF za pomocą Aspose.Words dla .NET. Wyłączając osadzanie czcionek, możesz zmniejszyć rozmiar generowanego pliku PDF. Wykonaj poniższe kroki:

## Krok 1: Ładowanie dokumentu

Zacznij od przesłania dokumentu, który chcesz przekonwertować do formatu PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Pamiętaj, aby podać poprawną ścieżkę do swojego dokumentu.

## Krok 2: Ustaw opcje zapisywania plików PDF

Utwórz instancję klasy PdfSaveOptions i określ sposób osadzania czcionek:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Ta opcja umożliwia dezaktywację integracji czcionek Windows w generowanym pliku PDF.

## Krok 3: Konwertuj dokument na format PDF

 Użyj`Save` metoda konwersji dokumentu do formatu PDF określająca opcje konwersji:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Upewnij się, że podałeś poprawną ścieżkę do zapisania przekonwertowanego pliku PDF.

### Przykładowy kod źródłowy dla opcji Wyłącz osadzanie czcionek Windows przy użyciu Aspose.Words dla .NET

Oto pełny kod źródłowy wyłączający osadzanie czcionek Windows w dokumencie PDF za pomocą Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Wyjściowy plik PDF zostanie zapisany bez osadzania standardowych czcionek systemu Windows.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Wykonując te kroki, możesz łatwo wyłączyć osadzanie czcionek Windows w dokumencie PDF za pomocą Aspose.Words dla .NET.


## Wniosek

tym samouczku nauczyliśmy się, jak zmniejszyć rozmiar pliku PDF, wyłączając osadzanie czcionek Windows za pomocą Aspose.Words dla .NET. Wyłączając osadzanie czcionek, można zmniejszyć rozmiar wygenerowanego pliku PDF, co ułatwia przechowywanie, udostępnianie i przesyłanie plików. Należy jednak pamiętać, że wyłączenie osadzania czcionek systemu Windows może spowodować zmiany w wyglądzie i formatowaniu końcowego dokumentu PDF. Korzystając z tej funkcji, należy wziąć pod uwagę te konsekwencje. Zachęcamy do poznania większej liczby funkcji Aspose.Words dla .NET, aby zoptymalizować generowanie plików PDF.

### Często Zadawane Pytania

#### P: Co powoduje wyłączenie osadzania czcionek systemu Windows w dokumencie PDF i dlaczego jest to ważne?
Odp.: Wyłączenie osadzania czcionek systemu Windows w dokumencie PDF to proces uniemożliwiający dołączenie czcionek systemu Windows do wygenerowanego pliku PDF. Zmniejsza to rozmiar pliku PDF poprzez usunięcie osadzonych danych czcionek systemu Windows. Może to być ważne przy zmniejszaniu rozmiaru plików PDF, co może ułatwić ich przechowywanie, udostępnianie i szybsze przesyłanie.

#### P: Jak mogę wyłączyć osadzanie czcionek Windows w dokumencie PDF przy użyciu Aspose.Words dla .NET?
O: Aby wyłączyć osadzanie czcionek Windows w dokumencie PDF za pomocą Aspose.Words dla .NET, wykonaj następujące kroki:

 Załaduj dokument, który chcesz przekonwertować do formatu PDF za pomocą`Document` ścieżka klasy i dokumentu.

 Utwórz instancję`PdfSaveOptions` klasę i ustaw`FontEmbeddingMode`własność do`PdfFontEmbeddingMode.EmbedNone`. Wyłącza to osadzanie czcionek systemu Windows w wygenerowanym pliku PDF.

 Użyj`Save` metoda`Document` obiekt, aby przekonwertować dokument do formatu PDF, określając wcześniej skonfigurowane opcje konwersji.

#### P: Jakie są korzyści z wyłączenia osadzania czcionek systemu Windows w dokumencie PDF?
O: Korzyści z wyłączenia osadzania czcionek systemu Windows w dokumencie PDF są następujące:

Zmniejszony rozmiar pliku PDF: wyłączenie osadzania czcionek systemu Windows powoduje usunięcie osadzonych danych czcionek systemu Windows, zmniejszając rozmiar wygenerowanego pliku PDF.

Łatwiejsze przechowywanie: mniejsze pliki PDF są łatwiejsze do przechowywania, zapisywania i przesyłania.

Szybsze udostępnianie i przesyłanie: mniejsze pliki PDF można udostępniać i przesyłać szybciej, oszczędzając czas i zasoby.

#### P: Jakie są konsekwencje wyłączenia osadzania czcionek systemu Windows w dokumencie PDF?
O: Wyłączenie osadzania czcionek systemu Windows w dokumencie PDF może prowadzić do następujących konsekwencji:

Utrata wyglądu i formatowania: Jeżeli czcionki Windows określone w dokumencie nie są dostępne w systemie, w którym otwierany jest plik PDF, zostaną użyte czcionki zastępcze, co może skutkować nieprawidłowym wyglądem i formatowaniem. w kształcie odbiegającym od oczekiwanego.

Problemy z czytelnością: Jeśli użyte czcionki zastępcze nie są tak czytelne jak czcionki oryginalne, może to mieć wpływ na czytelność tekstu w dokumencie PDF.