---
title: Pogrubiony tekst
linktitle: Pogrubiony tekst
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak pogrubić tekst za pomocą Aspose.Words dla .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/bold-text/
---

W tym przykładzie powiemy Ci, jak pogrubić tekst za pomocą Aspose.Words dla .NET. Pogrubienie tekstu sprawia, że jest on bardziej widoczny i wyeksponowany.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Pogrubiony tekst

 Możemy pogrubić tekst, ustawiając kreatora dokumentów`Font.Bold`własność do`true`.

```csharp
builder.Font.Bold = true;
```

## Krok 3: Dodaj treść do dokumentu

 Teraz możemy dodać treść do dokumentu za pomocą metod tworzenia dokumentów, takich jak`Writeln`, który dodaje wiersz tekstu.

```csharp
builder.Writeln("This text will be bold");
```

## Przykładowy kod źródłowy pogrubionego tekstu przy użyciu Aspose.Words dla .NET


```csharp
// Użyj narzędzia do tworzenia dokumentów, aby dodać treść do dokumentu.
DocumentBuilder builder = new DocumentBuilder();

// Pogrub tekst.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Gratulacje! Nauczyłeś się teraz, jak pogrubiać tekst za pomocą Aspose.Words dla .NET.


### Często zadawane pytania

#### P: Jak mogę pogrubić tekst w Aspose.Words?

 O: Aby pogrubić tekst w Aspose.Words, możesz użyć opcji`Font.Bold` własność`Run`obiekt. Możesz ustawić tę właściwość na`true` pogrubić określony tekst. Możesz na przykład użyć`run.Font.Bold=true` aby pogrubić tekst wewnątrz`Run` obiekt.

#### P: Czy można pogrubić kilka fragmentów tekstu w tym samym akapicie?

 Odp.: Tak, możesz pogrubić wiele fragmentów tekstu w jednym akapicie, używając opcji wielokrotnych`Run` obiekty. Możesz utworzyć wiele`Run` obiektów i ustaw`Font.Bold`własność do`true` dla każdego obiektu, aby pogrubić wybrane fragmenty tekstu. Następnie możesz dodać je do akapitu za pomocą`Paragraph.AppendChild(run)` metoda.

#### P: Czy mogę pogrubić tekst znajdujący się w tabeli lub komórce w Aspose.Words?

 O: Tak, możesz pogrubić tekst znajdujący się w tabeli lub komórce w Aspose.Words. Możesz przejść do żądanej komórki lub akapitu, korzystając z odpowiednich metod, a następnie zastosować pogrubione formatowanie, korzystając z opcji`Font.Bold` własność`Run` Lub`Paragraph` obiekt.