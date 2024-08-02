---
title: Lista punktowana
linktitle: Lista punktowana
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć listę punktowaną za pomocą Aspose.Words dla .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/bulleted-list/
---

W tym samouczku powiemy Ci, jak utworzyć listę punktowaną za pomocą Aspose.Words dla .NET. Lista punktowana służy do wyszczególniania elementów bez stosowania numeracji.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Stosowanie domyślnej listy punktowanej

 Możemy zastosować domyślną listę punktowaną, korzystając z narzędzia do tworzenia dokumentów`ApplyBulletDefault` metoda.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Krok 3: Dostosowywanie formatu punktora

 Możemy dostosować format punktora, uzyskując dostęp do właściwości`ListFormat.List.ListLevels[0]`. W tym przykładzie użyliśmy myślnika „-” jako punktora.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Krok 4: Dodawanie pozycji do listy

 Teraz możemy dodawać elementy do listy punktowanej, korzystając z narzędzia do tworzenia dokumentów`Writeln` metoda.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Krok 5: Usuwanie wcięcia z listy

 Jeśli chcemy utworzyć podlistę, możemy zwiększyć wcięcie za pomocą`ListFormat.ListIndent()` metoda. W tym przykładzie dodajemy podlistę do pozycji 2a i 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Przykładowy kod źródłowy listy punktowanej przy użyciu Aspose.Words dla .NET


```csharp
// Użyj narzędzia do tworzenia dokumentów, aby dodać treść do dokumentu.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Gratulacje! Nauczyłeś się teraz, jak tworzyć listę punktowaną za pomocą Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Jak utworzyć listę punktowaną w Markdown?

Odp.: Aby utworzyć listę punktowaną w Markdown, zacznij każdy element listy symbolem punktora (`-`, `*` , Lub`+`), po którym następuje spacja.

#### P: Czy w Markdown można zagnieżdżać listy punktowane?

O: Tak, możliwe jest zagnieżdżanie list punktowanych w Markdown poprzez dodanie czterech przesuniętych spacji przed każdym zagnieżdżonym elementem listy.

#### P: Jak dostosować symbole punktorów?

Odp.: W standardowym Markdown symbole punktorów są predefiniowane. Jednak niektóre edytory Markdown umożliwiają ich dostosowanie za pomocą określonych rozszerzeń.

#### P: Czy listy punktowane w Markdown obsługują wcięcia?

O: Tak, listy punktowane w Markdown obsługują wcięcia. Możesz dodać przesunięcie w lewo za pomocą spacji lub tabulatorów.

#### P: Czy do elementów listy można dodawać łącza lub tekst osadzony?

Odp.: Tak, możesz dodawać łącza lub tekst osadzony do elementów listy, korzystając z odpowiedniej składni Markdown.
