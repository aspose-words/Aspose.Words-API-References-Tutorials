---
title: Skopiuj nagłówki i stopki z poprzedniej sekcji
linktitle: Skopiuj nagłówki i stopki z poprzedniej sekcji
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak kopiować nagłówki i stopki z poprzedniej sekcji dokumentów programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

W tym samouczku krok po kroku poprowadzimy Cię, jak skopiować nagłówki i stopki z poprzedniej sekcji do dokumentu programu Word za pomocą Aspose.Words dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach.

 Aby rozpocząć, upewnij się, że masz zainstalowany i skonfigurowany Aspose.Words for .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj bibliotekę z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Dostęp do poprzedniej sekcji

 Najpierw pobierz poprzednią sekcję, uzyskując dostęp do pliku`PreviousSibling` właściwość bieżącej sekcji:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## Krok 2: Sprawdzanie poprzedniej sekcji

Następnie sprawdź, czy istnieje poprzednia sekcja. Jeśli nie ma poprzedniej sekcji, po prostu zwracamy:

```csharp
if (previousSection == null)
    return;
```

## Krok 3: Czyszczenie i kopiowanie nagłówków i stopek

Aby skopiować nagłówki i stopki z poprzedniej sekcji do bieżącej sekcji, usuwamy istniejące nagłówki i stopki w bieżącej sekcji, a następnie przeglądamy nagłówki i stopki z poprzedniej sekcji, aby dodać sklonowane kopie do bieżącej sekcji:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## Krok 4: Zapisywanie dokumentu

Na koniec zapisz zmodyfikowany dokument:

```csharp
doc.Save("OutputDocument.docx");
```

Otóż to! Pomyślnie skopiowałeś nagłówki i stopki z poprzedniej sekcji do bieżącej sekcji w dokumencie programu Word przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy kopiowania nagłówków stopek z poprzedniej sekcji przy użyciu Aspose.Words dla .NET

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

Możesz swobodnie używać tego kodu we własnych projektach i modyfikować go zgodnie ze swoimi specyficznymi wymaganiami.

### Często zadawane pytania

#### P: Jak mogę skopiować nagłówki i stopki z poprzedniej sekcji do Aspose.Words?

 O: Aby skopiować nagłówki i stopki z poprzedniej sekcji do Aspose.Words, możesz użyć metody`CopyHeadersFootersFromPreviousSection()` metoda na prąd`Section`obiekt. Spowoduje to skopiowanie nagłówków i stopek z poprzedniej sekcji do bieżącej sekcji.

#### P: Czy można skopiować tylko nagłówek lub stopkę z poprzedniej sekcji w Aspose.Words?

 O: Tak, możliwe jest skopiowanie tylko nagłówka lub stopki z poprzedniej sekcji w Aspose.Words. W tym celu możesz skorzystać z`CopyHeaderFromPreviousSection()` I`CopyFooterFromPreviousSection()` metody na prąd`Section` obiekt, aby specjalnie skopiować nagłówek lub stopkę z poprzedniej sekcji do bieżącej sekcji.

#### P: Czy kopiowanie nagłówków i stopek z poprzedniej sekcji zastępuje istniejące nagłówki i stopki w bieżącej sekcji?

Odpowiedź: Tak, kopiowanie nagłówków i stopek z poprzedniej sekcji zastępuje istniejące nagłówki i stopki w bieżącej sekcji. Jeśli chcesz zachować istniejące nagłówki i stopki i dodać je do skopiowanych nagłówków i stopek, będziesz musiał wykonać dodatkową operację, aby scalić zawartość.

#### P: Jak mogę sprawdzić, czy sekcja ma nagłówek lub stopkę z poprzedniej sekcji w Aspose.Words?

O: Aby sprawdzić, czy sekcja ma nagłówek lub stopkę z poprzedniej sekcji w Aspose.Words, możesz użyć`HasHeader` I`HasFooter` właściwości na`Section` obiekt, aby określić, czy istnieje nagłówek lub stopka nagłówka. Jeśli`HasHeader` Lub`HasFooter` zwroty`false`, oznacza to, że w tej sekcji nie ma nagłówka ani stopki z poprzedniej sekcji.