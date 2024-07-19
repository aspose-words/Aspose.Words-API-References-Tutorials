---
title: Wcięty kod
linktitle: Wcięty kod
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak używać kodu z wcięciami w Aspose.Words for .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/indented-code/
---

W tym przykładzie wyjaśnimy, jak używać funkcji kodu z wcięciem w Aspose.Words dla .NET. Kod wcięty służy do wizualnego przedstawiania bloków kodu o określonym formatowaniu.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Dodaj styl dla wciętego kodu

 Dodamy niestandardowy styl dla wciętego kodu za pomocą`Styles.Add` metoda`Document` obiekt. W tym przykładzie tworzymy styl o nazwie „IndentedCode” dla kodu z wcięciem.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Krok 3: Dodaj wcięty kod

Teraz możemy dodać blok kodu z wcięciem, używając niestandardowego stylu „IndentedCode”.

```csharp
builder.Writeln("This is an indented code block");
```

### Przykładowy kod źródłowy kodu z wcięciem w Aspose.Words dla .NET

```csharp
// Użyj narzędzia do tworzenia dokumentów, aby dodać treść do dokumentu.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Gratulacje! Nauczyłeś się teraz, jak korzystać z funkcji kodu z wcięciami w Aspose.Words dla .NET.


### Często zadawane pytania

#### P: Co to jest kod z wcięciem w Markdown?

Odp.: Kod z wcięciem w Markdown to metoda formatowania używana do wyświetlania kodu w dokumencie Markdown. Polega na wcięciu każdej linii kodu spacjami lub tabulatorami.

#### P: Jak używać kodu z wcięciem w Markdown?

Odp.: Aby użyć w Markdown kodu z wcięciami, wpisz w każdym wierszu kodu spacje lub tabulatory.

#### P: Jakie są zalety kodu z wcięciem w Markdown?

Odp.: Wcięty kod w Markdown poprawia czytelność kodu i ułatwia jego zrozumienie czytelnikom.

#### P: Jaka jest różnica między kodem z wcięciem a blokami kodu w Markdown?

Odp.: Kod z wcięciem jest używany w przypadku małych fragmentów kodu wstawianych do tekstu, natomiast bloki kodu służą do wyświetlania większych fragmentów kodu w oddzielnym formatowaniu.

#### P: Czy wszystkie edytory Markdown obsługują wcięty kod w Markdown?

Odp.: Obsługa kodu z wcięciami w Markdown może się różnić w zależności od redaktorów Markdown. Aby mieć pewność, sprawdź dokumentację wydawcy.