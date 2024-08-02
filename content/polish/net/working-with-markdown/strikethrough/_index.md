---
title: Przekreślenie
linktitle: Przekreślenie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zastosować styl przekreślonego tekstu za pomocą Aspose.Words dla .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/strikethrough/
---


tym przykładzie przeprowadzimy Cię przez proces stosowania stylu przekreślonego tekstu przy użyciu Aspose.Words dla .NET. Tekst przekreślony oznacza, że tekst został usunięty lub nie jest już ważny.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Zastosuj przekreślony styl tekstu

 Włączymy styl przekreślonego tekstu, ustawiając opcję`StrikeThrough` własność`Font` oponować`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Krok 3: Dodaj przekreślony tekst

 Możemy teraz dodać przekreślony tekst za pomocą generatora dokumentów`Writeln` metoda.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Przykładowy kod źródłowy przekreślonego tekstu w Aspose.Words dla .NET

```csharp
// Użyj narzędzia do tworzenia dokumentów, aby dodać treść do dokumentu.
DocumentBuilder builder = new DocumentBuilder();

// Zrób przekreślenie tekstu.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Gratulacje! Nauczyłeś się teraz, jak zastosować styl przekreślonego tekstu w Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Jak mogę dodać przekreślony tekst w Aspose.Words?

 O: Aby dodać przekreślony tekst w Aspose.Words, możesz użyć metody`Font.StrikeThrough` własność`Run` obiekt. Możesz ustawić tę właściwość na`true` , aby dodać przekreślony tekst do określonego tekstu. Możesz na przykład użyć`run.Font.StrikeThrough=true` , aby dodać przekreślony tekst do pliku`Run` obiekt.

#### P: Czy można dodać przekreślony tekst do kilku fragmentów tekstu w tym samym akapicie?

 Odp.: Tak, możesz dodać przekreślony tekst do wielu części tekstu w jednym akapicie, używając opcji wielokrotnych`Run` obiekty. Możesz utworzyć wiele`Run` obiektów i ustaw`Font.StrikeThrough`własność do`true` dla każdego obiektu, aby dodać przekreślony tekst do żądanych części tekstu. Następnie możesz dodać je do akapitu za pomocą`Paragraph.AppendChild(run)` metoda.

#### P: Czy mogę dodać przekreślony tekst do tekstu znajdującego się w tabeli lub komórce w Aspose.Words?

 O: Tak, możesz dodać przekreślony tekst do tekstu znajdującego się w tabeli lub komórce w Aspose.Words. Możesz przejść do żądanej komórki lub akapitu, korzystając z odpowiednich metod, a następnie zastosować przekreślone formatowanie tekstu, korzystając z opcji`Font.StrikeThrough` własność`Run` Lub`Paragraph` obiekt.