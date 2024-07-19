---
title: Skopiuj tekst z zakładek do dokumentu programu Word
linktitle: Skopiuj tekst z zakładek do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Bez wysiłku kopiuj tekst z zakładek pomiędzy dokumentami programu Word za pomocą Aspose.Words dla .NET. Dowiedz się, jak to zrobić, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-bookmarks/copy-bookmarked-text/
---
## Wstęp

Czy zdarzyło Ci się kiedyś skopiować określone sekcje z jednego dokumentu programu Word do drugiego? Cóż, masz szczęście! W tym samouczku przeprowadzimy Cię przez proces kopiowania tekstu z zakładek z jednego dokumentu programu Word do drugiego za pomocą Aspose.Words dla .NET. Niezależnie od tego, czy tworzysz raport dynamiczny, czy automatyzujesz generowanie dokumentów, ten przewodnik uprości Ci ten proces.

## Warunki wstępne

Zanim zagłębimy się w temat, upewnij się, że masz następujące elementy:

-  Biblioteka Aspose.Words dla .NET: Możesz ją pobrać z[Tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: Visual Studio lub dowolne inne środowisko programistyczne .NET.
- Podstawowa znajomość języka C#: Znajomość programowania w języku C# i frameworku .NET.

## Importuj przestrzenie nazw

Na początek upewnij się, że w projekcie zaimportowano niezbędne przestrzenie nazw:

```csharp
using Aspose.Words;
using Aspose.Words.Import;
using Aspose.Words.Bookmark;
```

## Krok 1: Załaduj dokument źródłowy

Najpierw musisz załadować dokument źródłowy zawierający tekst z zakładek, który chcesz skopiować.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

 Tutaj,`dataDir` to ścieżka do katalogu dokumentów, oraz`Bookmarks.docx` jest dokumentem źródłowym.

## Krok 2: Zidentyfikuj zakładkę

Następnie określ zakładkę, którą chcesz skopiować z dokumentu źródłowego.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

 Zastępować`"MyBookmark1"` z rzeczywistą nazwą Twojej zakładki.

## Krok 3: Utwórz dokument docelowy

Teraz utwórz nowy dokument, do którego zostanie skopiowany tekst z zakładek.

```csharp
Document dstDoc = new Document();
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Krok 4: Zaimportuj zawartość dodaną do zakładek

 Aby mieć pewność, że style i formatowanie zostaną zachowane, użyj`NodeImporter` , aby zaimportować zawartość zakładek z dokumentu źródłowego do dokumentu docelowego.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(importer, srcBookmark, dstNode);
```

## Krok 5: Zdefiniuj metodę AppendBookmarkedText

Tutaj dzieje się magia. Zdefiniuj metodę obsługi kopiowania tekstu z zakładek:

```csharp
private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
{
    Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
    Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

    if (startPara == null || endPara == null)
        throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

    if (startPara.ParentNode != endPara.ParentNode)
        throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");

    Node endNode = endPara.NextSibling;

    for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
    {
        Node newNode = importer.ImportNode(curNode, true);
        dstNode.AppendChild(newNode);
    }
}
```

## Krok 6: Zapisz dokument docelowy

Na koniec zapisz dokument docelowy, aby zweryfikować skopiowaną treść.

```csharp
dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## Wniosek

I to wszystko! Pomyślnie skopiowałeś tekst z zakładek z jednego dokumentu programu Word do innego za pomocą Aspose.Words dla .NET. Ta metoda doskonale nadaje się do automatyzacji zadań związanych z manipulacją dokumentami, dzięki czemu przepływ pracy jest bardziej wydajny i usprawniony.

## Często zadawane pytania

### Czy mogę skopiować wiele zakładek jednocześnie?
Tak, możesz przeglądać wiele zakładek i używać tej samej metody do kopiowania każdej z nich.

### Co się stanie, jeśli zakładka nie zostanie znaleziona?
 The`Range.Bookmarks` nieruchomość powróci`null`, więc upewnij się, że zajmiesz się tą sprawą, aby uniknąć wyjątków.

### Czy mogę zachować formatowanie oryginalnej zakładki?
 Absolutnie! Za pomocą`ImportFormatMode.KeepSourceFormatting` gwarantuje zachowanie oryginalnego formatowania.

### Czy istnieje ograniczenie rozmiaru tekstu dodanego do zakładek?
Nie ma określonego limitu, ale wydajność może się różnić w przypadku bardzo dużych dokumentów.

### Czy mogę kopiować tekst pomiędzy różnymi formatami dokumentów programu Word?
Tak, Aspose.Words obsługuje różne formaty programu Word i metoda działa w przypadku tych formatów.