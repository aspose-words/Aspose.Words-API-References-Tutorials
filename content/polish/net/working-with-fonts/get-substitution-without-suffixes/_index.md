---
title: Uzyskaj podstawienie bez przyrostków
linktitle: Uzyskaj podstawienie bez przyrostków
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zarządzać zastępowaniem czcionek bez przyrostków w Aspose.Words dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby mieć pewność, że Twoje dokumenty będą wyglądać idealnie za każdym razem.
type: docs
weight: 10
url: /pl/net/working-with-fonts/get-substitution-without-suffixes/
---

Witamy w tym kompleksowym przewodniku na temat zarządzania zastępowaniem czcionek przy użyciu Aspose.Words dla .NET. Jeśli kiedykolwiek miałeś problem z nieprawidłowym wyświetlaniem czcionek w dokumentach, trafiłeś we właściwe miejsce. Ten samouczek przeprowadzi Cię krok po kroku przez proces skutecznego zastępowania czcionek bez przyrostków. Zacznijmy!

## Warunki wstępne

Zanim zagłębisz się w samouczek, upewnij się, że posiadasz następujące elementy:

- Podstawowa znajomość języka C#: Zrozumienie programowania w języku C# ułatwi wykonanie i wdrożenie poszczególnych kroków.
-  Aspose.Words dla biblioteki .NET: Pobierz i zainstaluj bibliotekę z[link do pobrania](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: Skonfiguruj środowisko programistyczne, takie jak Visual Studio, aby pisać i uruchamiać kod.
-  Przykładowy dokument: przykładowy dokument (np.`Rendering.docx`), z którymi będziesz pracować w tym samouczku.

## Importuj przestrzenie nazw

Najpierw musimy zaimportować niezbędne przestrzenie nazw, aby uzyskać dostęp do klas i metod dostarczonych przez Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using Aspose.Words.WarningInfo;
using System.Collections.Generic;
```

## Krok 1: Zdefiniuj katalog dokumentów

Aby rozpocząć, określ katalog, w którym znajduje się Twój dokument. Pomaga to w zlokalizowaniu dokumentu, nad którym chcesz pracować.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Skonfiguruj procedurę obsługi ostrzeżeń o podstawieniach

Następnie musimy skonfigurować procedurę obsługi ostrzeżeń, która powiadomi nas za każdym razem, gdy podczas przetwarzania dokumentu nastąpi zamiana czcionki. Ma to kluczowe znaczenie dla wychwytywania i rozwiązywania wszelkich problemów z czcionkami.

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## Krok 3: Dodaj niestandardowe źródła czcionek

W tym kroku dodamy niestandardowe źródła czcionek, aby mieć pewność, że Aspose.Words będzie w stanie zlokalizować i używać właściwych czcionek. Jest to szczególnie przydatne, jeśli masz określone czcionki przechowywane w niestandardowych katalogach.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

W tym kodzie:
-  Pobieramy bieżące źródła czcionek i dodajemy nowe`FolderFontSource` wskazując na nasz niestandardowy katalog czcionek (`C:\\MyFonts\\`).
- Następnie aktualizujemy źródła czcionek za pomocą tej nowej listy.

## Krok 4: Zapisz dokument

Na koniec zapisz dokument po zastosowaniu ustawień zastępowania czcionek. Na potrzeby tego samouczka zapiszemy go w formacie PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## Krok 5: Utwórz klasę obsługi ostrzeżeń

 Aby skutecznie obsługiwać ostrzeżenia, utwórz klasę niestandardową, która implementuje metodę`IWarningCallback` interfejs. Ta klasa będzie przechwytywać i rejestrować wszelkie ostrzeżenia dotyczące podstawiania czcionek.

```csharp
public class DocumentSubstitutionWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

W tej klasie:
-  The`Warning` metoda przechwytuje ostrzeżenia związane z zastępowaniem czcionek.
-  The`FontWarnings` kolekcja przechowuje te ostrzeżenia do dalszej kontroli lub rejestrowania.

## Wniosek

Opanowałeś teraz proces obsługi zastępowania czcionek bez przyrostków przy użyciu Aspose.Words dla .NET. Dzięki tej wiedzy Twoje dokumenty zachowają swój zamierzony wygląd, niezależnie od czcionek dostępnych w systemie. Eksperymentuj z różnymi ustawieniami i źródłami, aby w pełni wykorzystać moc Aspose.Words.

## Często zadawane pytania

### P1: Jak mogę używać czcionek z wielu niestandardowych katalogów?

 Możesz dodać wiele`FolderFontSource` przypadki do`fontSources`wylistuj i odpowiednio zaktualizuj źródła czcionek.

### P2: Gdzie mogę pobrać bezpłatną wersję próbną Aspose.Words dla .NET?

 Możesz pobrać bezpłatną wersję próbną ze strony[Aspose bezpłatna strona próbna](https://releases.aspose.com/).

###  P3: Czy mogę obsługiwać wiele typów ostrzeżeń za pomocą`IWarningCallback`?

 Tak`IWarningCallback` interfejs pozwala na obsługę różnego rodzaju ostrzeżeń, a nie tylko podmiany czcionek.

### P4: Gdzie mogę uzyskać wsparcie dla Aspose.Words?

 Aby uzyskać pomoc, odwiedź stronę[Forum wsparcia Aspose.Words](https://forum.aspose.com/c/words/8).

### P5: Czy można kupić licencję tymczasową?

 Tak, możesz uzyskać tymczasową licencję od[strona licencji tymczasowej](https://purchase.aspose.com/temporary-license/).