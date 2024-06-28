---
title: Kodeks Ogrodzony
linktitle: Kodeks Ogrodzony
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak korzystać z funkcji kodu chronionego w Aspose.Words dla .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/fenced-code/
---

W tym przykładzie przeprowadzimy Cię przez proces korzystania z funkcji chronionego kodu w Aspose.Words dla .NET. kod chroniony służy do reprezentowania bloków kodu o określonym formatowaniu.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Dodanie stylu dla chronionego kodu

 Dodamy niestandardowy styl dla chronionego kodu za pomocą`Styles.Add` metoda`Document` obiekt. W tym przykładzie tworzymy styl o nazwie „FencedCode” dla chronionego kodu.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Krok 3: Dodanie chronionego kodu bez informacji

Teraz możemy dodać chroniony blok kodu bez ciągu informacyjnego, używając niestandardowego stylu „FencedCode”.

```csharp
builder.Writeln("This is an fenced code");
```

## Krok 4: Dodaj chroniony kod z ciągiem informacyjnym

Możemy również dodać chroniony blok kodu z ciągiem informacji, używając innego niestandardowego stylu. W tym przykładzie tworzymy styl o nazwie „FencedCode.C#”, który będzie reprezentował blok kodu C#.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Przykładowy kod źródłowy dla Fenced Code przy użyciu Aspose.Words dla .NET

```csharp
// Użyj narzędzia do tworzenia dokumentów, aby dodać treść do dokumentu.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Często zadawane pytania

#### P: Co to jest kod rozdzielany w Markdown?

Odpowiedź: Kod rozdzielany w Markdown to metoda formatowania używana do wyświetlania kodu w dokumencie Markdown. Polega na obramowaniu kodu określonymi ogranicznikami.

#### P: Jakie są zalety kodu rozdzielanego w Markdown?

Odp.: Kod rozdzielany w Markdown poprawia czytelność kodu i ułatwia jego zrozumienie czytelnikom. Umożliwia także zachowanie podświetlania składni w niektórych edytorach Markdown.

#### P: Jaka jest różnica między kodem rozdzielanym i wciętym w Markdown?

Odp.: W kodzie rozdzielanym używane są określone ograniczniki do otaczania kodu, podczas gdy kod z wcięciem polega na wcięciu każdej linii kodu spacjami lub tabulatorami.

#### P: Czy kod rozdzielany w Markdown jest obsługiwany przez wszystkich redaktorów Markdown?

Odp.: Obsługa kodu rozdzielanego w Markdown może się różnić w zależności od redaktorów Markdown. Aby mieć pewność, sprawdź dokumentację wydawcy.

