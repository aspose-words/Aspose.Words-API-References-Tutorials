---
title: Uporządkowana lista
linktitle: Uporządkowana lista
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć uporządkowaną listę za pomocą Aspose.Words dla .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/ordered-list/
---

W tym przykładzie wyjaśnimy, jak korzystać z funkcji listy uporządkowanej w Aspose.Words dla .NET. Lista uporządkowana umożliwia porządkowanie elementów sekwencyjnie za pomocą numerów.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby utworzyć nowy dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Zastosowanie uporządkowanego formatu listy

 Zastosujemy uporządkowany format listy, korzystając z kreatora dokumentów`ApplyBulletDefault`metoda. Możemy również dostosować format numeracji, przechodząc do poziomów listy i ustawiając żądany format.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Krok 3: Dodawanie pozycji do listy

 Pozycje do listy możemy dodawać za pomocą generatora dokumentów`Writeln` metoda.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Krok 4: Zrób wcięcie na liście

 Możemy wciąć listę za pomocą generatora dokumentów`ListIndent` metoda.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Krok 5: Zapisanie dokumentu

Wreszcie możemy zapisać dokument w żądanym formacie.

### Przykładowy kod źródłowy listy uporządkowanej z Aspose.Words dla .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Gratulacje! Nauczyłeś się teraz, jak korzystać z funkcji listy uporządkowanej w Aspose.Words dla .NET.


### Często zadawane pytania

#### P: Jak utworzyć uporządkowaną listę w Markdown?

Odp.: Aby utworzyć uporządkowaną listę w Markdown, zacznij każdy element listy numerem, po którym następuje kropka (`1.`, `2.`, `3.`), po którym następuje spacja.

#### P: Czy możemy zagnieżdżać uporządkowane listy w Markdown?

O: Tak, możliwe jest zagnieżdżanie uporządkowanych list w Markdown poprzez dodanie czterech przesuniętych spacji przed każdym zagnieżdżonym elementem listy.

#### P: Jak dostosować numerację uporządkowanych list?

Odp.: W standardowym Markdown uporządkowana numeracja list jest generowana automatycznie. Jednak niektóre edytory Markdown umożliwiają dostosowanie go za pomocą określonych rozszerzeń.

#### P: Czy uporządkowane listy w Markdown obsługują wcięcia?

O: Tak, uporządkowane listy w Markdown obsługują wcięcia. Możesz dodać przesunięcie w lewo za pomocą spacji lub tabulatorów.

#### P: Czy do elementów listy można dodawać łącza lub tekst osadzony?

Odp.: Tak, możesz dodawać łącza lub tekst osadzony do elementów listy, korzystając z odpowiedniej składni Markdown.