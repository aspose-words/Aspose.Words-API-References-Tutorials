---
title: Ustaw ustawienia zastępczej czcionki
linktitle: Ustaw ustawienia zastępczej czcionki
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak skonfigurować ustawienia zastępczych czcionek w Aspose.Words dla .NET. Dzięki temu obszernemu przewodnikowi wszystkie znaki w dokumentach będą wyświetlane poprawnie.
type: docs
weight: 10
url: /pl/net/working-with-fonts/set-font-fallback-settings/
---

Podczas pracy z dokumentami zawierającymi różnorodne elementy tekstowe, takie jak różne języki czy znaki specjalne, niezwykle istotne jest zapewnienie prawidłowego wyświetlania tych elementów. Aspose.Words dla .NET oferuje zaawansowaną funkcję zwaną Ustawieniami zastępczych czcionek, która pomaga w definiowaniu reguł zastępowania czcionek, gdy oryginalna czcionka nie obsługuje niektórych znaków. W tym przewodniku omówimy krok po kroku, jak skonfigurować ustawienia zastępczej czcionki przy użyciu Aspose.Words dla .NET.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość C#: Znajomość języka programowania C# i frameworku .NET.
-  Aspose.Words dla .NET: Pobierz i zainstaluj z[link do pobrania](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: konfiguracja taka jak Visual Studio do pisania i uruchamiania kodu.
-  Przykładowy dokument: Przygotuj przykładowy dokument (np.`Rendering.docx`) gotowy do testów.
- Reguły zastępowania czcionek XML: Przygotuj plik XML definiujący zasady zastępowania czcionek.

## Importuj przestrzenie nazw

Aby korzystać z Aspose.Words, musisz zaimportować niezbędne przestrzenie nazw. Umożliwia to dostęp do różnych klas i metod niezbędnych do przetwarzania dokumentów.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## Krok 1: Zdefiniuj katalog dokumentów

Najpierw zdefiniuj katalog, w którym przechowywany jest dokument. Jest to niezbędne do zlokalizowania i przetworzenia dokumentu.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument

 Załaduj swój dokument do Aspose.Words`Document` obiekt. Ten krok umożliwia programową pracę z dokumentem.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Skonfiguruj ustawienia czcionek

 Stwórz nowy`FontSettings` obiekt i załaduj ustawienia zastępczej czcionki z pliku XML. Ten plik XML zawiera reguły dotyczące zastępczych czcionek.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## Krok 4: Zastosuj ustawienia czcionki do dokumentu

 Przypisz skonfigurowane`FontSettings` do dokumentu. Dzięki temu podczas renderowania dokumentu zostaną zastosowane reguły dotyczące czcionek zastępczych.

```csharp
doc.FontSettings = fontSettings;
```

## Krok 5: Zapisz dokument

Na koniec zapisz dokument. Ustawienia zastępczej czcionki zostaną użyte podczas operacji zapisywania, aby zapewnić prawidłowe podstawienie czcionek.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Plik XML: Reguły zastępowania czcionek

Oto przykład tego, jak powinien wyglądać plik XML definiujący reguły zastępczych czcionek:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## Wniosek

Wykonując poniższe kroki, możesz skutecznie skonfigurować i używać ustawień zastępczych czcionek w Aspose.Words dla .NET. Dzięki temu wszystkie znaki będą poprawnie wyświetlane w dokumentach, nawet jeśli oryginalna czcionka nie obsługuje niektórych znaków. Wdrożenie tych ustawień znacznie poprawi jakość i czytelność dokumentów.

## Często zadawane pytania

### P1: Co to jest funkcja zastępowania czcionek?

Font Fallback to funkcja umożliwiająca podmianę czcionek, gdy oryginalna czcionka nie obsługuje niektórych znaków, zapewniając prawidłowe wyświetlanie wszystkich elementów tekstu.

### P2: Czy mogę określić wiele czcionek zastępczych?

Tak, możesz określić wiele czcionek zastępczych w regułach XML. Aspose.Words sprawdzi każdą czcionkę w określonej kolejności, aż znajdzie taką, która obsługuje dany znak.

### P3: Gdzie mogę pobrać Aspose.Words dla .NET?

 Można go pobrać z[Strona pobierania Aspose](https://releases.aspose.com/words/net/).

### P4: Jak utworzyć plik XML dla reguł zastępczych czcionek?

Plik XML można utworzyć za pomocą dowolnego edytora tekstu. Powinien mieć strukturę pokazaną w przykładzie podanym w tym samouczku.

### P5: Czy dostępna jest obsługa Aspose.Words?

 Tak, możesz znaleźć pomoc na stronie[Forum wsparcia Aspose.Words](https://forum.aspose.com/c/words/8).