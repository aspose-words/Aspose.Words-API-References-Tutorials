---
title: Ustaw foldery czcionek z priorytetem
linktitle: Ustaw foldery czcionek z priorytetem
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić foldery czcionek z priorytetem w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Dzięki naszemu przewodnikowi Twoje dokumenty będą wyświetlane perfekcyjnie za każdym razem.
type: docs
weight: 10
url: /pl/net/working-with-fonts/set-fonts-folders-with-priority/
---
## Wstęp

W świecie manipulacji dokumentami ustawienie niestandardowych folderów czcionek może mieć ogromne znaczenie, zapewniając idealne renderowanie dokumentów, niezależnie od tego, gdzie są przeglądane. Dzisiaj zajmiemy się tym, jak ustawić foldery czcionek z priorytetem w dokumentach programu Word za pomocą Aspose.Words dla .NET. Ten obszerny przewodnik przeprowadzi Cię przez każdy krok, dzięki czemu proces będzie możliwie najbardziej płynny.

## Warunki wstępne

Zanim zaczniemy, upewnijmy się, że mamy wszystko, czego potrzebujemy. Oto krótka lista kontrolna:

-  Aspose.Words dla .NET: Musisz mieć zainstalowaną tę bibliotekę. Jeśli jeszcze tego nie masz, możesz[pobierz go tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: upewnij się, że masz działające środowisko programistyczne .NET, takie jak Visual Studio.
-  Katalog dokumentów: Upewnij się, że masz katalog na swoje dokumenty. W naszych przykładach użyjemy`"YOUR DOCUMENT DIRECTORY"` jako symbol zastępczy tej ścieżki.

## Importuj przestrzenie nazw

Po pierwsze, musimy zaimportować niezbędne przestrzenie nazw. Te przestrzenie nazw są niezbędne do uzyskania dostępu do klas i metod udostępnianych przez Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Teraz podzielmy każdy krok, aby ustawić priorytet folderów czcionek.

## Krok 1: Skonfiguruj źródła czcionek

Na początek zdefiniuj źródła czcionek. W tym miejscu możesz powiedzieć Aspose.Words, gdzie szukać czcionek. Możesz określić wiele folderów czcionek, a nawet ustawić ich priorytet.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
    new SystemFontSource(), 
    new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

W tym przykładzie ustawiamy dwa źródła czcionek:
- SystemFontSource: Jest to domyślne źródło czcionek, które zawiera wszystkie czcionki zainstalowane w systemie.
-  FolderFontSource: Jest to folder niestandardowych czcionek znajdujący się pod adresem`C:\\MyFonts\\` . The`true` parametr określa, że ten folder powinien być skanowany rekurencyjnie, oraz`1` ustala swój priorytet.

## Krok 2: Załaduj swój dokument

Następnie załaduj dokument, z którym chcesz pracować. Upewnij się, że dokument znajduje się w określonym katalogu.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Ta linia kodu ładuje dokument o nazwie`Rendering.docx` z katalogu dokumentów.

## Krok 3: Zapisz swój dokument z nowymi ustawieniami czcionki

Na koniec zapisz dokument. Kiedy zapiszesz dokument, Aspose.Words użyje określonych ustawień czcionki.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

 Spowoduje to zapisanie dokumentu jako pliku PDF w katalogu dokumentów pod nazwą`WorkingWithFonts.SetFontsFoldersWithPriority.pdf`.

## Wniosek

I masz to! Pomyślnie skonfigurowałeś foldery czcionek z priorytetem przy użyciu Aspose.Words dla .NET. Określając niestandardowe foldery i priorytety czcionek, możesz mieć pewność, że Twoje dokumenty będą renderowane spójnie, niezależnie od tego, gdzie są przeglądane. Jest to szczególnie przydatne w środowiskach, w których określone czcionki nie są domyślnie instalowane.

## Często zadawane pytania

### Dlaczego miałbym ustawić niestandardowe foldery czcionek?
Ustawienie niestandardowych folderów czcionek zapewnia prawidłowe renderowanie dokumentów, nawet jeśli używają czcionek niezainstalowanych w systemie, w którym są przeglądane.

### Czy mogę ustawić wiele niestandardowych folderów czcionek?
Tak, możesz określić wiele folderów czcionek. Aspose.Words pozwala ustawić priorytet dla każdego folderu, zapewniając, że najważniejsze czcionki zostaną znalezione jako pierwsze.

### Co się stanie, jeśli we wszystkich określonych źródłach brakuje czcionki?
Jeśli brakuje czcionki ze wszystkich określonych źródeł, Aspose.Words użyje czcionki zastępczej, aby upewnić się, że dokument jest nadal czytelny.

### Czy mogę zmienić priorytet czcionek systemowych?
Czcionki systemowe są zawsze domyślnie dołączane, ale możesz ustawić ich priorytet w stosunku do niestandardowych folderów czcionek.

### Czy można używać ścieżek sieciowych dla niestandardowych folderów czcionek?
Tak, możesz określić ścieżki sieciowe jako niestandardowe foldery czcionek, co umożliwi centralizację zasobów czcionek w lokalizacji sieciowej.