---
title: Pobierz zakres stron JPEG
linktitle: Pobierz zakres stron JPEG
second_title: Aspose.Words API do przetwarzania dokumentów
description: Konwertuj określone strony dokumentów programu Word do formatu JPEG z niestandardowymi ustawieniami za pomocą Aspose.Words dla .NET. Dowiedz się, jak krok po kroku regulować jasność, kontrast i rozdzielczość.
type: docs
weight: 10
url: /pl/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---
## Wstęp

Konwertowanie dokumentów programu Word na obrazy może być niezwykle przydatne niezależnie od tego, czy tworzysz miniatury, przeglądasz dokumenty online, czy udostępniasz zawartość w bardziej przystępnym formacie. Dzięki Aspose.Words dla .NET możesz łatwo konwertować określone strony dokumentów Word do formatu JPEG, dostosowując różne ustawienia, takie jak jasność, kontrast i rozdzielczość. Przyjrzyjmy się, jak osiągnąć ten cel krok po kroku!

## Warunki wstępne

Zanim zaczniemy, będziesz potrzebować kilku rzeczy:

-  Aspose.Words dla .NET: Upewnij się, że masz zainstalowany Aspose.Words dla .NET. Możesz[pobierz go tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: środowisko programistyczne AC#, takie jak Visual Studio.
- Przykładowy dokument: Dokument programu Word do pracy. W tym samouczku możesz użyć dowolnego pliku .docx.
- Podstawowa znajomość języka C#: Znajomość programowania w języku C#.

Gdy już będziesz mieć je gotowe, zaczynajmy!

## Importuj przestrzenie nazw

Aby używać Aspose.Words dla .NET, musisz zaimportować niezbędne przestrzenie nazw na początku swojego kodu. Dzięki temu masz dostęp do wszystkich klas i metod wymaganych do manipulacji dokumentami.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Krok 1: Załaduj swój dokument

Najpierw musimy załadować dokument Word, który chcemy przekonwertować. Załóżmy, że nasz dokument ma nazwę`Rendering.docx` i znajduje się w katalogu określonym przez symbol zastępczy`YOUR DOCUMENT DIRECTORY`.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Ten kod inicjuje ścieżkę do dokumentu i ładuje ją do pliku Aspose.Words`Document` obiekt.

## Krok 2: Skonfiguruj opcje ImageSave

 Następnie skonfigurujemy`ImageSaveOptions` aby określić, w jaki sposób chcemy wygenerować nasz plik JPEG. Obejmuje to ustawienie zakresu stron, jasności, kontrastu i rozdzielczości obrazu.

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options.PageSet = new PageSet(0); // Konwertuj tylko pierwszą stronę
options.ImageBrightness = 0.3f;   // Ustaw jasność
options.ImageContrast = 0.7f;     // Ustaw kontrast
options.HorizontalResolution = 72f; // Ustaw rozdzielczość
```

## Krok 3: Zapisz dokument jako JPEG

Na koniec zapisujemy dokument jako plik JPEG, korzystając ze zdefiniowanych przez nas ustawień.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 Ten kod zapisuje pierwszą stronę`Rendering.docx` jako obraz JPEG z określonymi ustawieniami jasności, kontrastu i rozdzielczości.

## Wniosek

masz to! Pomyślnie przekonwertowałeś określoną stronę dokumentu programu Word na obraz JPEG z dostosowanymi ustawieniami przy użyciu Aspose.Words dla .NET. Proces ten można dostosować do różnych potrzeb, niezależnie od tego, czy przygotowujesz obrazy na stronę internetową, tworzysz podglądy dokumentów itp.

## Często zadawane pytania

### Czy mogę przekonwertować wiele stron jednocześnie?
 Tak, możesz określić zakres stron za pomocą`PageSet` nieruchomość w`ImageSaveOptions`.

### Jak dostosować jakość obrazu?
 Jakość pliku JPEG można dostosować za pomocą opcji`JpegQuality` nieruchomość w`ImageSaveOptions`.

### Czy mogę zapisywać obrazy w innych formatach?
 Tak, Aspose.Words obsługuje różne formaty obrazów, takie jak PNG, BMP i TIFF. Zmień`SaveFormat` W`ImageSaveOptions` odpowiednio.

### Czy istnieje sposób na podgląd obrazu przed zapisaniem?
Będziesz musiał osobno zaimplementować mechanizm podglądu, ponieważ Aspose.Words nie zapewnia wbudowanej funkcji podglądu.

### Jak uzyskać tymczasową licencję na Aspose.Words?
 Możesz poprosić o[licencja tymczasowa tutaj](https://purchase.aspose.com/temporary-license/).