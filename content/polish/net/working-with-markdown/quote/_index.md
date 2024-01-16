---
title: Cytat
linktitle: Cytat
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak korzystać z cytatów w Aspose.Words dla .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/quote/
---

W tym przykładzie wyjaśnimy, jak korzystać z funkcji cytowania w Aspose.Words for .NET Quote służy do wyróżniania fragmentów tekstu poprzez otaczanie ich specjalną ramką.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Korzystanie z domyślnego stylu cytatu

Aby zastosować do tekstu formatowanie cudzysłowu, użyjemy domyślnego stylu akapitu o nazwie „Cytat”.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Krok 3: Tworzenie stylów dla zagnieżdżonych poziomów

 Możemy tworzyć style dla zagnieżdżonych poziomów za pomocą`Styles.Add` metoda`Document` obiekt. W tym przykładzie tworzymy styl o nazwie „Cytat1”, który będzie reprezentował zagnieżdżony poziom cytatu.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Przykładowy kod źródłowy cytatów z Aspose.Words dla .NET


```csharp
// Użyj narzędzia do tworzenia dokumentów, aby dodać treść do dokumentu.
DocumentBuilder builder = new DocumentBuilder();

// Domyślnie dokument przechowuje styl cytatu blokowego dla pierwszego poziomu.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Twórz style dla zagnieżdżonych poziomów poprzez dziedziczenie stylów.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Gratulacje! Nauczyłeś się teraz, jak korzystać z funkcji cytatów w Aspose.Words dla .NET.


### Często zadawane pytania

#### P: Co to jest cytat w Markdown?

O: Cytat w Markdown to sposób na podkreślenie fragmentów tekstu z innych źródeł lub nawiązanie do znanych cytatów.

#### P: Jak używać cudzysłowów w Markdown?

Odp.: Aby użyć cytatu w Markdown, umieść tekst cytatu w nawiasach ostrych (`>`). Każdy wiersz cytatu musi zaczynać się od jodełki.

#### P: Czy cytaty Markdown obsługują atrybuty?

Odp.: Cytaty Markdown nie obsługują określonych atrybutów. Podkreśla je po prostu formatowanie cytowanego tekstu.

#### P: Czy możesz osadzać cytaty w Markdown?

O: Tak, możliwe jest zagnieżdżanie cudzysłowów w Markdown poprzez dodanie dodatkowego poziomu nawiasów ostrych (`>`).