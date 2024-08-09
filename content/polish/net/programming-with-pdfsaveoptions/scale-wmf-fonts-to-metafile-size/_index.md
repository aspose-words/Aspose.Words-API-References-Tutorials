---
title: Zmniejsz rozmiar pliku PDF za pomocą skalowania czcionek Wmf do rozmiaru metapliku
linktitle: Zmniejsz rozmiar pliku PDF za pomocą skalowania czcionek Wmf do rozmiaru metapliku
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący zmniejszania rozmiaru pliku PDF za pomocą skalowania czcionek wmf do rozmiaru metapliku podczas konwersji do formatu PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---
## Wstęp

Podczas pracy z plikami PDF, szczególnie tymi wygenerowanymi z dokumentów programu Word zawierających grafikę WMF (metaplik systemu Windows), zarządzanie rozmiarem może stać się kluczowym aspektem obsługi dokumentów. Jednym ze sposobów kontrolowania rozmiaru pliku PDF jest dostosowanie sposobu renderowania czcionek WMF w dokumencie. W tym samouczku przyjrzymy się, jak zmniejszyć rozmiar pliku PDF poprzez skalowanie czcionek WMF do rozmiaru metapliku za pomocą Aspose.Words dla .NET.

## Warunki wstępne

Zanim przejdziesz do kolejnych kroków, upewnij się, że masz następujące elementy:

1. Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words. Jeśli nie, możesz[pobierz go tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: w tym samouczku założono, że masz skonfigurowane środowisko programistyczne .NET (takie jak Visual Studio), w którym możesz pisać i wykonywać kod C#.
3. Podstawowa znajomość programowania .NET: Pomocna będzie znajomość podstawowych koncepcji programowania .NET i składni języka C#.
4. Dokument Word z grafiką WMF: Będziesz potrzebował dokumentu Word zawierającego grafikę WMF. Możesz użyć własnego dokumentu lub utworzyć go do testów.

## Importuj przestrzenie nazw

Najpierw musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#. Dzięki temu uzyskasz dostęp do klas i metod wymaganych do pracy z Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Krok 1: Załaduj dokument Word

 Aby rozpocząć, załaduj dokument Word zawierający grafikę WMF. Odbywa się to za pomocą`Document` klasa z Aspose.Words.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "WMF with text.docx");
```

 Tutaj,`dataDir` jest symbolem zastępczym ścieżki katalogu dokumentów. Tworzymy instancję`Document` class, przekazując ścieżkę do pliku Word. Spowoduje to załadowanie dokumentu do pamięci i przygotowanie go do dalszego przetwarzania.

## Krok 2: Skonfiguruj opcje renderowania metaplików

 Następnie musisz skonfigurować opcje renderowania metapliku. Konkretnie ustaw`ScaleWmfFontsToMetafileSize`własność do`false`. Kontroluje, czy czcionki WMF są skalowane w celu dopasowania do rozmiaru metapliku.

```csharp
// Utwórz nową instancję MetafileRenderingOptions
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
    ScaleWmfFontsToMetafileSize = false
};
```

 The`MetafileRenderingOptions` class udostępnia opcje renderowania metaplików (takich jak WMF). Ustawiając`ScaleWmfFontsToMetafileSize` Do`false`, instruujesz Aspose.Words, aby nie skalował czcionek zgodnie z rozmiarem metapliku, co może pomóc w zmniejszeniu ogólnego rozmiaru pliku PDF.

## Krok 3: Ustaw opcje zapisywania plików PDF

Teraz skonfiguruj opcje zapisywania plików PDF, aby korzystać z właśnie ustawionych opcji renderowania metaplików. Mówi to Aspose.Words, jak postępować z metaplikami podczas zapisywania dokumentu w formacie PDF.

```csharp
// Utwórz nową instancję PdfSaveOptions
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    MetafileRenderingOptions = metafileRenderingOptions
};
```

 The`PdfSaveOptions` class umożliwia określenie różnych ustawień zapisywania dokumentu w formacie PDF. Przypisując wcześniej skonfigurowane`MetafileRenderingOptions` do`MetafileRenderingOptions` własność`PdfSaveOptions`, upewnij się, że dokument został zapisany zgodnie z żądanymi ustawieniami renderowania metapliku.

## Krok 4: Zapisz dokument w formacie PDF

Na koniec zapisz dokument programu Word jako plik PDF, korzystając ze skonfigurowanych opcji zapisywania. Spowoduje to zastosowanie wszystkich ustawień, w tym opcji renderowania metapliku, do wyjściowego pliku PDF.


```csharp
// Zapisz dokument w formacie PDF
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

 Na tym etapie`Save` metoda`Document` class służy do eksportowania dokumentu do pliku PDF. Określana jest ścieżka, w której plik PDF zostanie zapisany, wraz z rozszerzeniem`PdfSaveOptions` które obejmują ustawienia renderowania metapliku.

## Wniosek

Skalując czcionki WMF do rozmiaru metapliku, możesz znacznie zmniejszyć rozmiar plików PDF generowanych z dokumentów programu Word. Technika ta pomaga zoptymalizować przechowywanie i dystrybucję dokumentów bez pogarszania jakości treści wizualnych. Wykonanie czynności opisanych powyżej sprawi, że pliki PDF będą łatwiejsze w zarządzaniu i mniejsze.

## Często zadawane pytania

### Co to jest WMF i dlaczego jest ważny dla rozmiaru pliku PDF?

WMF (Windows Metafile) to format graficzny używany w systemie Microsoft Windows. Może zawierać zarówno dane wektorowe, jak i bitmapowe. Ponieważ dane wektorowe można skalować i manipulować nimi, ważne jest, aby obchodzić się z nimi właściwie, aby uniknąć niepotrzebnie dużych plików PDF.

### W jaki sposób skalowanie czcionek WMF do rozmiaru metapliku wpływa na plik PDF?

Skalowanie czcionek WMF do rozmiaru metapliku może pomóc w zmniejszeniu całkowitego rozmiaru pliku PDF poprzez uniknięcie renderowania czcionek w wysokiej rozdzielczości, które mogłoby zwiększyć rozmiar pliku.

### Czy mogę używać innych formatów metaplików z Aspose.Words?

Tak, Aspose.Words obsługuje różne formaty metaplików, w tym EMF (Enhanced Metafile) oprócz WMF.

### Czy tę technikę można zastosować do wszystkich typów dokumentów programu Word?

Tak, tę technikę można zastosować do dowolnego dokumentu programu Word zawierającego grafikę WMF, pomagając w optymalizacji rozmiaru generowanego pliku PDF.

### Gdzie mogę znaleźć więcej informacji o Aspose.Words?

 Możesz dowiedzieć się więcej o Aspose.Words w[Dokumentacja Aspose.Words](https://reference.aspose.com/words/net/) . Aby zapoznać się z plikami do pobrania, wersjami próbnymi i pomocą techniczną, odwiedź stronę[Strona pobierania Aspose.Words](https://releases.aspose.com/words/net/), [Kup Aspose.Words](https://purchase.aspose.com/buy), [Bezpłatny okres próbny](https://releases.aspose.com/), [Licencja tymczasowa](https://purchase.aspose.com/temporary-license/) , I[Wsparcie](https://forum.aspose.com/c/words/8).