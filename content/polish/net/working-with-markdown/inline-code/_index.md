---
title: Kod wbudowany
linktitle: Kod wbudowany
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić kod za pomocą Aspose.Words dla .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/inline-code/
---

W tym przykładzie przeprowadzimy Cię przez proces korzystania z funkcji kodu wbudowanego w Aspose.Words dla .NET. Kod wbudowany służy do wizualnego przedstawiania fragmentów kodu w akapicie.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Dodaj styl do kodu wbudowanego

 Dodamy niestandardowy styl dla kodu wbudowanego za pomocą`Styles.Add` metoda`Document` obiekt. W tym przykładzie tworzymy styl o nazwie „InlineCode” dla kodu wbudowanego z domyślnym znacznikiem wstecznym.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Krok 3: Dodaj kod wbudowany

Teraz możemy dodać kod wbudowany, korzystając z niestandardowego stylu „InlineCode”. W tym przykładzie dodajemy dwa fragmenty tekstu z różną liczbą odstępów.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Przykładowy kod źródłowy kodu wbudowanego z Aspose.Words dla .NET

```csharp
// Użyj narzędzia do tworzenia dokumentów, aby dodać treść do dokumentu.
DocumentBuilder builder = new DocumentBuilder();

// Pominięto liczbę backticków. Domyślnie zostanie użyty jeden backtick.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Będą 3 backticki.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Gratulacje! Nauczyłeś się teraz, jak korzystać z funkcji kodu wbudowanego w Aspose.Words dla .NET.


### Często zadawane pytania

#### P: Jak mogę użyć kodu wbudowanego w Aspose.Words?

 Odp.: Aby użyć kodu wbudowanego w Aspose.Words, możesz użyć odpowiednich znaczników, aby otoczyć tekst, który ma być sformatowany jako kod wbudowany. Można na przykład użyć`<code>` Lub`<kbd>` znacznik do otaczania tekstu, który ma być sformatowany jako kod wbudowany.

#### P: Czy można określić czcionkę lub kolor kodu wbudowanego w Aspose.Words?

 O: Tak, możesz określić czcionkę lub kolor kodu wbudowanego w Aspose.Words. Możesz skorzystać z`Font.Name` I`Font.Color` właściwości`Run` obiekt, aby ustawić czcionkę i kolor kodu wbudowanego. Możesz na przykład użyć`run.Font.Name = "Courier New"` aby określić czcionkę dla kodu wbudowanego i`run.Font.Color = Color.Blue`aby określić kolor.

#### P: Czy mogę użyć kodu wbudowanego w akapicie zawierającym inne elementy tekstowe?

 O: Tak, możesz użyć kodu wbudowanego w akapicie zawierającym inne elementy tekstowe. Możesz utworzyć wiele`Run` obiekty reprezentujące różne części akapitu, a następnie użyj znaczników kodu wbudowanego, aby sformatować tylko określone części jako kod wbudowany. Następnie możesz dodać je do akapitu za pomocą`Paragraph.AppendChild(run)` metoda.