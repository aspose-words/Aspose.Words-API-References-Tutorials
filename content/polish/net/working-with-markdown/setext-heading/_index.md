---
title: Nagłówek setekstu
linktitle: Nagłówek setekstu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak używać nagłówków Setext do formatowania dokumentów za pomocą Aspose.Words dla .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/setext-heading/
---

W tym samouczku przeprowadzimy Cię przez proces korzystania z funkcji Setext Heading w Aspose.Words dla .NET. Nagłówki Setext to alternatywna metoda formatowania tytułów w dokumentach Markdown.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Używanie stylu nagłówka Setext

Zamierzamy użyć domyślnego stylu akapitu „Nagłówek 1”, aby utworzyć nagłówek poziomu 1 w naszym dokumencie.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Krok 3: Resetowanie stylów

Resetujemy wcześniej zastosowane style czcionek, aby uniknąć niepożądanej kombinacji stylów między akapitami.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Krok 4: Dostosowywanie poziomów nagłówków Setext

Możemy dostosować poziomy nagłówków Setext, dodając nowe style akapitów w oparciu o istniejące style nagłówków. W tym przykładzie tworzymy styl „SetextHeading1” w oparciu o styl „Nagłówek 1”, który reprezentuje nagłówek poziomu 1 w formacie Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Krok 5: Zapisanie dokumentu

Wreszcie możemy zapisać dokument w żądanym formacie.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Przykładowy kod źródłowy tytułów Setext z Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Użyj narzędzia do tworzenia dokumentów, aby dodać treść do dokumentu.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Zresetuj style z poprzedniego akapitu, aby nie łączyć stylów między akapitami.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Zresetuj style z poprzedniego akapitu, aby nie łączyć stylów między akapitami.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// Poziom nagłówka Setex zostanie zresetowany do 2, jeśli akapit podstawowy ma poziom nagłówka większy niż 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### Często zadawane pytania

#### P: Co to jest nagłówek Setext Markdown?

O: Nagłówek Setext Markdown to alternatywny sposób tworzenia nagłówków w dokumencie Markdown. Używa znaków podkreślenia (= lub -), aby wskazać różne poziomy nagłówków.

#### P: Jak używać nagłówków Setext Markdown?

Odp.: Aby użyć nagłówków Setext Markdown, umieść podkreślenia pod tekstem tytułu. Użyj znaków równości (=) dla nagłówka poziomu 1 i łączników (-) dla nagłówka poziomu 2.

#### P: Czy istnieją jakieś ograniczenia w używaniu nagłówków Setext Markdown?

O: Nagłówki Setext Markdown mają ograniczenia w zakresie hierarchii nagłówków i nie różnią się wizualnie tak jak standardowe nagłówki Markdown.

#### P: Czy mogę dostosować wygląd nagłówków Setext Markdown?

Odp.: W standardowym Markdown nie można dostosować wyglądu nagłówków Setext Markdown. Mają predefiniowany wygląd oparty na użytych znakach podkreślenia.

#### P: Czy nagłówki Setext Markdown są obsługiwane przez wszystkie edytory Markdown?

Odp.: Obsługa nagłówków Setext Markdown może się różnić w zależności od redaktorów Markdown. Aby mieć pewność, sprawdź dokumentację wydawcy.