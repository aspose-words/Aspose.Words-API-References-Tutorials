---
title: Eksportuj do Markdown z wyrównaniem zawartości tabeli
linktitle: Eksportuj do Markdown z wyrównaniem zawartości tabeli
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak eksportować dokumenty programu Word do Markdown z wyrównanymi tabelami przy użyciu Aspose.Words dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby uzyskać doskonałe tabele Markdown.
type: docs
weight: 10
url: /pl/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
## Wstęp

No hej! Czy zastanawiałeś się kiedyś, jak wyeksportować dokument programu Word do formatu Markdown z idealnie wyrównanymi tabelami? Niezależnie od tego, czy jesteś programistą pracującym nad dokumentacją, czy po prostu miłośnikiem Markdown, ten przewodnik jest dla Ciebie. Aby to osiągnąć, zagłębimy się w szczegóły korzystania z Aspose.Words dla .NET. Gotowy do przekształcenia tabel programu Word w starannie wyrównane tabele Markdown? Zacznijmy!

## Warunki wstępne

Zanim zagłębimy się w kod, musisz przygotować kilka rzeczy:

1.  Biblioteka Aspose.Words dla .NET: Upewnij się, że masz bibliotekę Aspose.Words dla .NET. Można go pobrać z[Strona z wydaniami Aspose](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: Skonfiguruj środowisko programistyczne. Visual Studio jest popularnym wyborem do programowania .NET.
3. Podstawowa znajomość języka C#: Zrozumienie języka C# jest niezbędne, ponieważ będziemy pisać kod w tym języku.
4. Przykładowy dokument programu Word: Przygotuj dokument programu Word, którego możesz użyć do testowania.

## Importuj przestrzenie nazw

Zanim zaczniemy kodować, zaimportujmy niezbędne przestrzenie nazw. Dają nam one dostęp do klas i metod Aspose.Words, których będziemy używać.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Krok 1: Zainicjuj dokument i narzędzie DocumentBuider

Po pierwsze, musimy utworzyć nowy dokument Word i zainicjować plik`DocumentBuilder` obiekt, aby rozpocząć budowanie naszego dokumentu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz nowy dokument.
Document doc = new Document();

// Zainicjuj program DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstaw komórki i wyrównaj zawartość

Następnie wstawimy kilka komórek do naszego dokumentu i ustawimy ich wyrównanie. Ma to kluczowe znaczenie dla zapewnienia prawidłowego wyrównania eksportu Markdown.

```csharp
// Wstaw komórkę i ustaw wyrównanie w prawo.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");

// Wstaw kolejną komórkę i ustaw wyrównanie do środka.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

## Krok 3: Ustaw wyrównanie zawartości tabeli dla eksportu Markdown

 Teraz czas na konfigurację`MarkdownSaveOptions` do kontrolowania wyrównania zawartości tabeli w wyeksportowanym pliku Markdown. Zapiszemy dokument z różnymi ustawieniami wyrównania, aby zobaczyć, jak to działa.

```csharp
// Utwórz obiekt MarkdownSaveOptions.
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    TableContentAlignment = TableContentAlignment.Left
};

// Zapisz dokument z wyrównaniem do lewej.
doc.Save(dataDir + "LeftTableContentAlignment.md", saveOptions);

// Zmień wyrównanie na prawe i zapisz.
saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "RightTableContentAlignment.md", saveOptions);

// Zmień wyrównanie na wyśrodkowane i zapisz.
saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "CenterTableContentAlignment.md", saveOptions);
```

## Krok 4: Użyj automatycznego wyrównywania zawartości tabeli

 The`Auto`Opcja wyrównania pobiera wyrównanie z pierwszego akapitu w odpowiedniej kolumnie tabeli. Może to być przydatne, jeśli w jednej tabeli znajdują się mieszane wyrównania.

```csharp
// Ustaw wyrównanie na Auto.
saveOptions.TableContentAlignment = TableContentAlignment.Auto;

// Zapisz dokument z automatycznym wyrównaniem.
doc.Save(dataDir + "AutoTableContentAlignment.md", saveOptions);
```

## Wniosek

I masz to! Eksportowanie dokumentów Word do Markdown z wyrównanymi tabelami przy użyciu Aspose.Words dla .NET jest proste, jeśli wiesz, jak to zrobić. Ta potężna biblioteka ułatwia kontrolowanie formatowania i wyrównania tabel, zapewniając, że dokumenty Markdown wyglądają dokładnie tak, jak chcesz. Miłego kodowania!

## Często zadawane pytania

### Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka, która umożliwia programistom programowe tworzenie, modyfikowanie, konwertowanie i eksportowanie dokumentów programu Word.

### Czy mogę ustawić różne wyrównania dla różnych kolumn w tej samej tabeli?
 Tak, za pomocą`Auto` opcję wyrównania, możesz zastosować różne wyrównania w oparciu o pierwszy akapit w każdej kolumnie.

### Czy potrzebuję licencji, aby używać Aspose.Words dla .NET?
 Tak, Aspose.Words dla .NET wymaga licencji dla pełnej funkcjonalności. Możesz dostać[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) dla ewolucji.

### Czy można eksportować inne elementy dokumentu do Markdown za pomocą Aspose.Words?
Tak, Aspose.Words obsługuje eksportowanie różnych elementów, takich jak nagłówki, listy i obrazy do formatu Markdown.

### Gdzie mogę uzyskać pomoc, jeśli napotkam problemy?
 Możesz uzyskać wsparcie od[Forum wsparcia Aspose.Words](https://forum.aspose.com/c/words/8).
