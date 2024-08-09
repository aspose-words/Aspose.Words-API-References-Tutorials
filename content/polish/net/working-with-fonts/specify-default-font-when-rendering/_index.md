---
title: Określ domyślną czcionkę podczas renderowania
linktitle: Określ domyślną czcionkę podczas renderowania
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak określić domyślną czcionkę podczas renderowania dokumentów programu Word przy użyciu Aspose.Words dla .NET. Zapewnij spójny wygląd dokumentów na różnych platformach.
type: docs
weight: 10
url: /pl/net/working-with-fonts/specify-default-font-when-rendering/
---
## Wstęp

Zapewnienie prawidłowego renderowania dokumentów programu Word na różnych platformach może stanowić wyzwanie, szczególnie w przypadku zgodności czcionek. Jednym ze sposobów zachowania spójnego wyglądu jest określenie domyślnej czcionki podczas renderowania dokumentów do formatu PDF lub innych formatów. W tym samouczku omówimy, jak ustawić domyślną czcionkę za pomocą Aspose.Words dla .NET, aby Twoje dokumenty wyglądały świetnie bez względu na to, gdzie są przeglądane.

## Warunki wstępne

Zanim zagłębisz się w kod, omówmy w tym samouczku, czego musisz przestrzegać:

- Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną najnowszą wersję. Możesz go pobrać[Tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: Visual Studio lub dowolne inne środowisko programistyczne .NET.
- Podstawowa znajomość języka C#: W tym samouczku założono, że znasz się na programowaniu w języku C#.

## Importuj przestrzenie nazw

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw. Umożliwią one dostęp do klas i metod wymaganych do pracy z Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Podzielmy teraz proces określania domyślnej czcionki na łatwe do wykonania kroki.

## Krok 1: Skonfiguruj katalog dokumentów

Najpierw zdefiniuj ścieżkę do katalogu dokumentów. W tym miejscu będą przechowywane pliki wejściowe i wyjściowe.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj swój dokument

Następnie załaduj dokument, który chcesz wyrenderować. W tym przykładzie użyjemy pliku o nazwie „Rendering.docx”.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Skonfiguruj ustawienia czcionek

 Utwórz instancję`FontSettings` i określ domyślną czcionkę. Jeśli podczas renderowania nie można znaleźć zdefiniowanej czcionki, Aspose.Words użyje najbliższej dostępnej czcionki na komputerze.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
```

## Krok 4: Zastosuj ustawienia czcionki do dokumentu

Przypisz skonfigurowane ustawienia czcionki do swojego dokumentu.

```csharp
doc.FontSettings = fontSettings;
```

## Krok 5: Zapisz dokument

Na koniec zapisz dokument w żądanym formacie. W takim przypadku zapiszemy go w formacie PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Wniosek

Wykonując poniższe kroki, możesz mieć pewność, że dokumenty programu Word będą renderowane przy użyciu określonej czcionki domyślnej, zachowując spójność na różnych platformach. Może to być szczególnie przydatne w przypadku dokumentów powszechnie udostępnianych lub przeglądanych w systemach o różnej dostępności czcionek.


## Często zadawane pytania

### Po co określać domyślną czcionkę w Aspose.Words?
Określenie czcionki domyślnej gwarantuje, że dokument będzie wyglądał spójnie na różnych platformach, nawet jeśli oryginalne czcionki są niedostępne.

### Co się stanie, jeśli podczas renderowania nie zostanie znaleziona domyślna czcionka?
Aspose.Words użyje najbliższej dostępnej czcionki na komputerze, aby jak najlepiej zachować wygląd dokumentu.

### Czy mogę określić wiele domyślnych czcionek?
 Nie, możesz określić tylko jedną czcionkę domyślną. Można jednak obsługiwać zastępowanie czcionek w określonych przypadkach za pomocą metody`FontSettings` klasa.

### Czy Aspose.Words dla .NET jest kompatybilny ze wszystkimi wersjami dokumentów Word?
Tak, Aspose.Words dla .NET obsługuje szeroką gamę formatów dokumentów Word, w tym DOC, DOCX, RTF i inne.

### Gdzie mogę uzyskać pomoc, jeśli napotkam problemy?
 Możesz uzyskać wsparcie od społeczności Aspose i programistów na stronie[Forum wsparcia Aspose.Words](https://forum.aspose.com/c/words/8).