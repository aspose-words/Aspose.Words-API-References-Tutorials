---
title: Dołącz zaznaczony tekst do dokumentu programu Word
linktitle: Dołącz zaznaczony tekst do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodać tekst z zakładkami do dokumentu programu Word za pomocą Aspose.Words dla .NET, korzystając z tego przewodnika krok po kroku. Idealny dla programistów.
type: docs
weight: 10
url: /pl/net/programming-with-bookmarks/append-bookmarked-text/
---
## Wstęp

Hej tam! Czy kiedykolwiek próbowałeś dołączyć tekst z sekcji oznaczonej zakładkami w dokumencie programu Word i okazało się to trudne? Masz szczęście! Ten samouczek przeprowadzi Cię przez proces korzystania z Aspose.Words dla .NET. Podzielimy to na proste kroki, dzięki czemu będziesz mógł łatwo je wykonać. Zanurzmy się i dołączmy tekst z zakładek jak profesjonalista!

## Warunki wstępne

Zanim zaczniemy, upewnijmy się, że masz wszystko, czego potrzebujesz:

-  Aspose.Words dla .NET: Upewnij się, że masz go zainstalowanego. Jeśli nie, możesz[pobierz go tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: dowolne środowisko programistyczne .NET, takie jak Visual Studio.
- Podstawowa znajomość języka C#: Pomocne będzie zrozumienie podstawowych koncepcji programowania w języku C#.
- Dokument programu Word z zakładkami: dokument programu Word z ustawionymi zakładkami, z których będziemy dodawać tekst.

## Importuj przestrzenie nazw

Na początek zaimportujmy niezbędne przestrzenie nazw. Dzięki temu będziemy mieć pewność, że wszystkie potrzebne nam narzędzia będą w zasięgu ręki.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Importing;
```

Podzielmy przykład na szczegółowe kroki.

## Krok 1: Załaduj dokument i zainicjuj zmienne

W porządku, zacznijmy od załadowania naszego dokumentu Worda i zainicjowania potrzebnych nam zmiennych.

```csharp
// Załaduj dokumenty źródłowe i docelowe.
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");

// Zainicjuj importera dokumentów.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

// Znajdź zakładkę w dokumencie źródłowym.
Bookmark srcBookmark = srcDoc.Range.Bookmarks["YourBookmarkName"];
```

## Krok 2: Znajdź akapit początkowy i końcowy

Teraz zlokalizujmy akapity, w których zaczyna się i kończy zakładka. Ma to kluczowe znaczenie, ponieważ musimy obsługiwać tekst w tych granicach.

```csharp
// To jest akapit zawierający początek zakładki.
Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;

// To jest akapit zawierający koniec zakładki.
Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

if (startPara == null || endPara == null)
    throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");
```

## Krok 3: Zweryfikuj elementy nadrzędne akapitów

Musimy upewnić się, że akapity początkowy i końcowy mają tego samego rodzica. Jest to prosty scenariusz, który pozwala zachować prostotę.

```csharp
// Ograniczmy się do w miarę prostego scenariusza.
if (startPara.ParentNode != endPara.ParentNode)
    throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");
```

## Krok 4: Zidentyfikuj węzeł do zatrzymania

Następnie musimy określić węzeł, w którym zakończymy kopiowanie tekstu. Będzie to węzeł bezpośrednio po akapicie końcowym.

```csharp
// Chcemy skopiować wszystkie akapity od akapitu początkowego do akapitu końcowego (włącznie),
// dlatego węzeł, w którym się zatrzymujemy, znajduje się po akapicie końcowym.
Node endNode = endPara.NextSibling;
```

## Krok 5: Dołącz tekst z zakładkami do dokumentu docelowego

Na koniec przejdźmy pętlą przez węzły od akapitu początkowego do węzła za akapitem końcowym i dołączmy je do dokumentu docelowego.

```csharp
for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
    // Tworzy to kopię bieżącego węzła i importuje ją (uważa) w kontekście
    // dokumentu docelowego. Importowanie oznacza prawidłowe dostosowanie stylów i identyfikatorów list.
    Node newNode = importer.ImportNode(curNode, true);

    // Dołącz zaimportowany węzeł do dokumentu docelowego.
    dstDoc.FirstSection.Body.AppendChild(newNode);
}

// Zapisz dokument docelowy z dołączonym tekstem.
dstDoc.Save("appended_document.docx");
```

## Wniosek

I masz to! Pomyślnie dodałeś tekst z sekcji oznaczonej zakładkami w dokumencie programu Word przy użyciu Aspose.Words dla .NET. To potężne narzędzie sprawia, że manipulowanie dokumentami jest dziecinnie proste, a teraz masz jeszcze jednego asa w rękawie. Miłego kodowania!

## Często zadawane pytania

### Czy mogę za jednym razem dodać tekst z wielu zakładek?
Tak, możesz powtórzyć proces dla każdej zakładki i odpowiednio dodać tekst.

### Co się stanie, jeśli akapity początkowy i końcowy mają różnych rodziców?
bieżącym przykładzie założono, że mają tego samego rodzica. W przypadku różnych rodziców wymagana jest bardziej złożona obsługa.

### Czy mogę zachować oryginalne formatowanie dołączonego tekstu?
 Absolutnie! The`ImportFormatMode.KeepSourceFormatting` gwarantuje zachowanie oryginalnego formatowania.

### Czy można dodać tekst w określonym miejscu w dokumencie docelowym?
Tak, możesz dołączyć tekst w dowolnej pozycji, przechodząc do żądanego węzła w dokumencie docelowym.

### Co się stanie, jeśli będę musiał dodać tekst z zakładki do nowej sekcji?
Możesz utworzyć nową sekcję w dokumencie docelowym i dołączyć tam tekst.