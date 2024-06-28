---
title: Wstaw spis treści do dokumentu programu Word
linktitle: Wstaw spis treści do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić spis treści w programie Word przy użyciu Aspose.Words dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby uzyskać płynną nawigację po dokumentach.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/insert-table-of-contents/
---
## Wstęp
W tym samouczku dowiesz się, jak efektywnie dodawać spis treści (TOC) do dokumentów programu Word przy użyciu Aspose.Words dla .NET. Ta funkcja jest niezbędna do organizowania i nawigacji w długich dokumentach, zwiększania czytelności i zapewniania szybkiego przeglądu sekcji dokumentu.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Podstawowa znajomość C# i frameworku .NET.
- Program Visual Studio zainstalowany na Twoim komputerze.
-  Aspose.Words dla biblioteki .NET. Jeśli jeszcze go nie zainstalowałeś, możesz go pobrać ze strony[Tutaj](https://releases.aspose.com/words/net/).

## Importuj przestrzenie nazw

Aby rozpocząć, zaimportuj niezbędne przestrzenie nazw do swojego projektu C#:

```csharp
using Aspose.Words;
using Aspose.Words.Builder;
using Aspose.Words.Fields;
using Aspose.Words.Tables;
```

Podzielmy proces na jasne etapy:

## Krok 1: Zainicjuj dokument Aspose.Words i narzędzie DocumentBuilder

 Najpierw zainicjuj nowy plik Aspose.Words`Document` obiekt i a`DocumentBuilder` pracować z:

```csharp
// Zainicjuj dokument i narzędzie DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstaw spis treści

 Teraz wstaw spis treści za pomocą`InsertTableOfContents` metoda:

```csharp
// Wstaw spis treści
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Krok 3: Rozpocznij zawartość dokumentu na nowej stronie

Aby zapewnić prawidłowe formatowanie, należy rozpocząć właściwą treść dokumentu na nowej stronie:

```csharp
// Wstaw podział strony
builder.InsertBreak(BreakType.PageBreak);
```

## Krok 4: Zbuduj swój dokument za pomocą nagłówków

Uporządkuj zawartość dokumentu, używając odpowiednich stylów nagłówków:

```csharp
// Ustaw style nagłówków
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Krok 5: Zaktualizuj i wypełnij spis treści

Zaktualizuj spis treści, aby odzwierciedlał strukturę dokumentu:

```csharp
// Zaktualizuj pola spisu treści
doc.UpdateFields();
```

## Krok 6: Zapisz dokument

Na koniec zapisz dokument w określonym katalogu:

```csharp
// Zapisz dokument
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
doc.Save(dataDir + "InsertTableOfContentsUsingAsposeWords.docx");
```

## Wniosek

Dodanie spisu treści przy użyciu Aspose.Words dla .NET jest proste i znacznie zwiększa użyteczność dokumentów. Wykonując poniższe kroki, możesz efektywnie organizować i poruszać się po złożonych dokumentach.

## Często zadawane pytania

### Czy mogę dostosować wygląd spisu treści?
Tak, możesz dostosować wygląd i zachowanie spisu treści za pomocą Aspose.Words dla interfejsów API .NET.

### Czy Aspose.Words obsługuje automatyczne aktualizowanie pól?
Tak, Aspose.Words umożliwia dynamiczną aktualizację pól takich jak spis treści w oparciu o zmiany w dokumencie.

### Czy mogę wygenerować wiele spisów treści w jednym dokumencie?
Aspose.Words obsługuje generowanie wielu spisów treści z różnymi ustawieniami w jednym dokumencie.

### Czy Aspose.Words jest kompatybilny z różnymi wersjami Microsoft Word?
Tak, Aspose.Words zapewnia kompatybilność z różnymi wersjami formatów Microsoft Word.

### Gdzie mogę znaleźć dalszą pomoc i wsparcie dla Aspose.Words?
Aby uzyskać dodatkową pomoc, odwiedź stronę[Forum Aspose.Words](https://forum.aspose.com/c/words/8) lub sprawdź[oficjalna dokumentacja](https://reference.aspose.com/words/net/).