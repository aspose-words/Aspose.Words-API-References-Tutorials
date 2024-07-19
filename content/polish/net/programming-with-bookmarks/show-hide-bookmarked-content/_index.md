---
title: Pokaż Ukryj zawartość dodaną do zakładek w dokumencie programu Word
linktitle: Pokaż Ukryj zawartość dodaną do zakładek w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wyświetlać i ukrywać zawartość zakładek w dokumentach programu Word przy użyciu Aspose.Words dla .NET, korzystając ze szczegółowego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-bookmarks/show-hide-bookmarked-content/
---
## Wstęp

Gotowy do zanurzenia się w świat manipulacji dokumentami za pomocą Aspose.Words dla .NET? Niezależnie od tego, czy jesteś programistą chcącym zautomatyzować zadania związane z dokumentami, czy po prostu osobą interesującą się programową obsługą plików Word, jesteś we właściwym miejscu. Dzisiaj przyjrzymy się, jak wyświetlać i ukrywać zawartość zakładek w dokumencie programu Word za pomocą Aspose.Words dla .NET. Dzięki temu przewodnikowi krok po kroku staniesz się profesjonalistą w kontrolowaniu widoczności treści na podstawie zakładek. Zacznijmy!

## Warunki wstępne

Zanim przejdziemy do sedna, jest kilka rzeczy, których będziesz potrzebować:

1. Visual Studio: dowolna wersja zgodna z .NET.
2.  Aspose.Words dla .NET: Pobierz[Tutaj](https://releases.aspose.com/words/net/).
3. Podstawowa znajomość języka C#: Jeśli potrafisz napisać prosty program „Hello World”, wszystko jest gotowe.
4. Dokument programu Word z zakładkami: W tym samouczku użyjemy przykładowego dokumentu z zakładkami.

## Importuj przestrzenie nazw

Na początek zaimportujmy niezbędne przestrzenie nazw. Dzięki temu mamy pewność, że mamy wszystkie narzędzia potrzebne do wykonania naszego zadania.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

Mając już gotowe przestrzenie nazw, możemy rozpocząć naszą podróż.

## Krok 1: Konfiguracja projektu

W porządku, zacznijmy od skonfigurowania naszego projektu w programie Visual Studio.

### Utwórz nowy projekt

Otwórz program Visual Studio i utwórz nowy projekt aplikacji konsolowej (.NET Core). Nazwij go czymś chwytliwym, na przykład „BookmarkVisibilityManager”.

### Dodaj Aspose.Words dla .NET

Będziesz musiał dodać Aspose.Words dla .NET do swojego projektu. Możesz to zrobić za pomocą Menedżera pakietów NuGet.

1. Przejdź do opcji Narzędzia > Menedżer pakietów NuGet > Zarządzaj pakietami NuGet dla rozwiązania.
2. Wyszukaj „Aspose.Words”.
3. Zainstaluj pakiet.

Świetnie! Teraz, gdy nasz projekt jest już skonfigurowany, przejdźmy do ładowania naszego dokumentu.

## Krok 2: Ładowanie dokumentu

Musimy załadować dokument Word zawierający zakładki. W tym samouczku użyjemy przykładowego dokumentu o nazwie „Bookmarks.docx”.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Ten fragment kodu ustawia ścieżkę do katalogu dokumentów i ładuje dokument do`doc` obiekt.

## Krok 3: Pokaż/ukryj zawartość dodaną do zakładek

Teraz przychodzi zabawna część – pokazywanie lub ukrywanie treści na podstawie zakładek. Stworzymy metodę o nazwie`ShowHideBookmarkedContent` sobie z tym poradzić.

Oto metoda przełączania widoczności zawartości dodanej do zakładek:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    Node currentNode = bm.BookmarkStart;
    while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
    {
        if (currentNode.NodeType == NodeType.Run)
        {
            Run run = currentNode as Run;
            run.Font.Hidden = isHidden;
        }
        currentNode = currentNode.NextSibling;
    }
}
```

### Podział metody

-  Pobieranie zakładek:`Bookmark bm = doc.Range.Bookmarks[bookmarkName];` pobiera zakładkę.
- Przechodzenie węzłów: Przechodzimy przez węzły w obrębie zakładki.
-  Przełącznik widoczności: Jeśli węzeł to a`Run` (ciągły ciąg tekstu), ustawiamy jego`Hidden` nieruchomość.

## Krok 4: Stosowanie metody

Dzięki naszej metodzie zastosujmy ją do pokazywania lub ukrywania treści na podstawie zakładki.

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true);
```

Ta linia kodu ukryje zawartość zakładki o nazwie „MyBookmark1”.

## Krok 5: Zapisywanie dokumentu

Na koniec zapiszmy nasz zmodyfikowany dokument.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

Spowoduje to zapisanie dokumentu z wprowadzonymi przez nas zmianami.

## Wniosek

masz to! Właśnie nauczyłeś się, jak pokazywać i ukrywać zawartość zakładek w dokumencie programu Word przy użyciu Aspose.Words dla .NET. To potężne narzędzie sprawia, że manipulowanie dokumentami jest dziecinnie proste, niezależnie od tego, czy automatyzujesz raporty, tworzysz szablony, czy po prostu majstrujesz przy plikach Word. Miłego kodowania!

## Często zadawane pytania

### Czy mogę przełączać wiele zakładek jednocześnie?
 Tak, możesz zadzwonić do`ShowHideBookmarkedContent` dla każdej zakładki, którą chcesz przełączyć.

### Czy ukrywanie treści wpływa na strukturę dokumentu?
Nie, ukrywanie treści wpływa tylko na jej widoczność. Treść pozostaje w dokumencie.

### Czy mogę użyć tej metody do innych typów treści?
Ta metoda w szczególności przełącza przebiegi tekstu. W przypadku innych typów zawartości należy zmodyfikować logikę przechodzenia węzłów.

### Czy Aspose.Words dla .NET jest darmowy?
 Aspose.Words oferuje bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/) , ale do użytku produkcyjnego wymagana jest pełna licencja. Możesz go kupić[Tutaj](https://purchase.aspose.com/buy).

### Jak mogę uzyskać pomoc, jeśli napotkam problemy?
 Możesz uzyskać wsparcie od społeczności Aspose[Tutaj](https://forum.aspose.com/c/words/8).