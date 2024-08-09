---
title: Włącz opcję Wyłącz zastępowanie czcionek
linktitle: Włącz opcję Wyłącz zastępowanie czcionek
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak włączyć lub wyłączyć zastępowanie czcionek w dokumentach programu Word za pomocą Aspose.Words dla .NET. Upewnij się, że Twoje dokumenty wyglądają spójnie na wszystkich platformach.
type: docs
weight: 10
url: /pl/net/working-with-fonts/enable-disable-font-substitution/
---
## Wstęp

Czy kiedykolwiek znalazłeś się w sytuacji, w której starannie wybrane czcionki w dokumencie programu Word są zastępowane podczas przeglądania na innym komputerze? Irytujące, prawda? Dzieje się tak na skutek zastępowania czcionek – procesu, podczas którego system zastępuje brakującą czcionkę dostępną. Ale nie martw się! Dzięki Aspose.Words dla .NET możesz łatwo zarządzać i kontrolować podstawianie czcionek. W tym samouczku przeprowadzimy Cię przez kroki umożliwiające włączenie lub wyłączenie zastępowania czcionek w dokumentach programu Word, dzięki czemu Twoje dokumenty zawsze będą wyglądać dokładnie tak, jak chcesz.

## Warunki wstępne

Zanim przejdziesz do kolejnych kroków, upewnij się, że masz wszystko, czego potrzebujesz:

-  Aspose.Words dla .NET: Pobierz najnowszą wersję[Tutaj](https://releases.aspose.com/words/net/).
- Visual Studio: dowolna wersja obsługująca platformę .NET.
- Podstawowa znajomość języka C#: Pomoże Ci to w podążaniu za przykładami kodowania.

## Importuj przestrzenie nazw

Aby rozpocząć, upewnij się, że w projekcie zaimportowano niezbędne przestrzenie nazw. Dodaj je na górze pliku C#:

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Podzielmy teraz proces na proste, łatwe do wykonania kroki.

## Krok 1: Skonfiguruj swój projekt

Najpierw skonfiguruj nowy projekt w Visual Studio i dodaj odwołanie do biblioteki Aspose.Words for .NET. Jeśli jeszcze tego nie zrobiłeś, pobierz go z[Strona Aspose](https://releases.aspose.com/words/net/).

## Krok 2: Załaduj swój dokument

Następnie załaduj dokument, z którym chcesz pracować. Oto jak to zrobić:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów. Ten kod ładuje dokument do pamięci, dzięki czemu można nim manipulować.

## Krok 3: Skonfiguruj ustawienia czcionek

 Teraz utwórzmy`FontSettings` obiekt do zarządzania ustawieniami zastępowania czcionek:

```csharp
FontSettings fontSettings = new FontSettings();
```

## Krok 4: Ustaw domyślne zastępowanie czcionek

Ustaw domyślną zamianę czcionki na wybraną czcionkę. Ta czcionka zostanie użyta, jeśli oryginalna czcionka nie jest dostępna:

```csharp
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

W tym przykładzie używamy czcionki Arial jako domyślnej czcionki.

## Krok 5: Wyłącz zastępowanie informacji o czcionkach

Aby wyłączyć podstawianie informacji o czcionkach, co uniemożliwia systemowi zastępowanie brakujących czcionek dostępnymi, użyj następującego kodu:

```csharp
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
```

## Krok 6: Zastosuj ustawienia czcionki do dokumentu

Teraz zastosuj te ustawienia do swojego dokumentu:

```csharp
doc.FontSettings = fontSettings;
```

## Krok 7: Zapisz swój dokument

Na koniec zapisz zmodyfikowany dokument. Możesz zapisać go w dowolnym formacie. Na potrzeby tego samouczka zapiszemy go w formacie PDF:

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```

## Wniosek

I masz to! Wykonując poniższe kroki, możesz łatwo kontrolować zastępowanie czcionek w dokumentach programu Word za pomocą Aspose.Words dla .NET. Dzięki temu Twoje dokumenty zachowają zamierzony wygląd i styl, niezależnie od tego, gdzie są przeglądane.

## Często zadawane pytania

### Czy w zamian mogę użyć czcionek innych niż Arial?

 Absolutnie! Możesz określić dowolną czcionkę dostępną w systemie, zmieniając nazwę czcionki w pliku`DefaultFontName` nieruchomość.

### Co się stanie, jeśli określona domyślna czcionka nie będzie dostępna?

Jeśli domyślna czcionka nie jest dostępna, Aspose.Words użyje systemowego mechanizmu awaryjnego, aby znaleźć odpowiedni zamiennik.

### Czy mogę ponownie włączyć funkcję zastępowania czcionek po jej wyłączeniu?

 Tak, możesz przełączyć`Enabled` własność`FontInfoSubstitution` z powrotem do`true` jeśli chcesz ponownie włączyć podstawianie czcionek.

### Czy istnieje sposób sprawdzenia, które czcionki są zastępowane?

Tak, Aspose.Words udostępnia metody rejestrowania i śledzenia zastępowań czcionek, dzięki czemu możesz zobaczyć, które czcionki są zastępowane.

### Czy mogę użyć tej metody do innych formatów dokumentów niż DOCX?

Zdecydowanie! Aspose.Words obsługuje różne formaty i możesz zastosować te ustawienia czcionek do dowolnego obsługiwanego formatu.