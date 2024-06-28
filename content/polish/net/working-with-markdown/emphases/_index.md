---
title: Podkreśla
linktitle: Podkreśla
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak używać wyróżnień (pogrubienie i kursywa) w Aspose.Words dla .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/emphases/
---

tym przykładzie wyjaśnimy, jak używać akcentów w Aspose.Words dla .NET. akcenty służą do podkreślenia pewnych części tekstu, np. pogrubienia i kursywy.

## Krok 1: Inicjalizacja dokumentu

 Najpierw zainicjujemy dokument, tworząc instancję klasy`Document` klasa.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Krok 2: Korzystanie z generatora dokumentów

Następnie użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Dodaj tekst z podkreśleniami

Możemy dodać podkreślenie tekstu, zmieniając właściwości czcionki generatora dokumentów. W tym przykładzie użyliśmy pogrubienia i kursywy, aby podkreślić różne części tekstu.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Krok 4: Zapisywanie dokumentu

 Wreszcie możemy zapisać dokument w żądanym formacie. W tym przykładzie używamy`.md` rozszerzenie formatu Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Gratulacje! Nauczyłeś się teraz, jak używać akcentów w Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Emphases przy użyciu Aspose.Words dla .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### Często zadawane pytania

#### P: Jak wyróżnić tekst za pomocą Markdown?

Odp.: Aby wyróżnić tekst za pomocą Markdown, po prostu otocz tekst odpowiednimi symbolami. Używać`*` Lub`_` dla kursywy,`**` Lub`__` za pogrubienie i`~~` do przekreślenia.

#### P: Czy możemy połączyć różne wyróżnienia w tym samym tekście?

 Odp.: Tak, możliwe jest łączenie różnych wyróżnień w tym samym tekście. Na przykład możesz pogrubić i pochylić słowo, używając obu`**` I`*` dookoła świata.

#### P: Jakie opcje wyróżniania są dostępne w Markdown?

Odp.: Opcje wyróżniania dostępne w Markdown są pisane kursywą (`*` Lub`_`), pogrubiony (`**` Lub`__`) i przekreślenie (`~~`).

#### P: Jak postępować w przypadkach, gdy tekst zawiera znaki specjalne używane przez Markdown do wyróżniania?

 Odp.: Jeśli Twój tekst zawiera znaki specjalne używane przez Markdown do wyróżniania, możesz je pominąć, poprzedzając je znakiem a`\` . Na przykład,`\*` wyświetli dosłowną gwiazdkę.

#### P: Czy możemy dostosować wygląd podświetlenia za pomocą CSS?

Odp.: Podświetlanie w Markdown jest zwykle renderowane przy użyciu domyślnych stylów przeglądarki. Jeśli przekonwertujesz Markdown na HTML, możesz dostosować wygląd podświetlania za pomocą reguł CSS.