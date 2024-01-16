---
title: Wstaw spis treści do dokumentu programu Word
linktitle: Wstaw spis treści do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić spis treści do dokumentów programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/insert-table-of-contents/
---
W tym obszernym samouczku dowiesz się, jak wstawić spis treści do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Przeprowadzimy Cię przez proces i udostępnimy niezbędne fragmenty kodu C#. Pod koniec tego przewodnika będziesz w stanie wygenerować spis treści z odpowiednimi nagłówkami i numerami stron.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim systemie.

## Krok 1: Utwórz nowy dokument i narzędzie DocumentBuider
Aby rozpocząć, utwórz nowy dokument za pomocą klasy Document i zainicjuj obiekt DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstaw spis treści
Następnie użyj metody InsertTableOfContents klasy DocumentBuilder, aby wstawić spis treści. Określ wymagane opcje formatowania w ramach metody:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Krok 3: Dodaj treść dokumentu
Po wstawieniu spisu treści należy dodać rzeczywistą treść dokumentu. Ustaw odpowiednie style nagłówków za pomocą StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Krok 4: Zaktualizuj spis treści
Nowo wstawiony spis treści będzie początkowo pusty. Aby go wypełnić, zaktualizuj pola w dokumencie:

```csharp
doc.UpdateFields();
```

## Krok 5: Zapisz dokument
Po wstawieniu spisu treści i aktualizacji pól należy zapisać dokument do pliku korzystając z metody Save klasy Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Przykładowy kod źródłowy do wstawiania spisu treści przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy do wstawiania spisu treści przy użyciu Aspose.Words dla .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Zainicjuj DocumentBuilder za pomocą obiektu Document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw spis treścia
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Rozpocznij właściwą treść dokumentu na drugiej stronie.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// Nowo wstawiony spis treści będzie początkowo pusty.
// Należy go wypełnić poprzez aktualizację pól w dokumencie.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się, jak wstawić spis treści do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wykorzystując dostarczony kod źródłowy, możesz teraz wygenerować spis treści z odpowiednimi nagłówkami i numerami stron dla swoich dokumentów.

### Często zadawane pytania dotyczące wstawiania spisu treści w dokumencie programu Word

#### P: Czy mogę dostosować wygląd spisu treści?

 O: Tak, możesz dostosować wygląd spisu treści, modyfikując opcje formatowania określone w pliku`InsertTableOfContents` metoda. Parametry umożliwiają kontrolowanie numerów stron, wcięć i innych stylów.

#### P: Co się stanie, jeśli chcę uwzględnić w spisie treści określone poziomy nagłówków?

 O: Możesz określić żądane poziomy nagłówków, które mają być uwzględnione w spisie treści, dostosowując wartość w obrębie`InsertTableOfContents` metoda. Na przykład za pomocą`"\\o \"1-3\""` będzie obejmować poziomy nagłówków od 1 do 3.

#### P: Czy mogę automatycznie zaktualizować spis treści, jeśli dokonam zmian w treści dokumentu?

 O: Tak, możesz automatycznie zaktualizować spis treści, wywołując metodę`UpdateFields` metoda na dokumencie. Dzięki temu wszelkie zmiany dokonane w treści dokumentu, takie jak dodanie lub usunięcie nagłówków, zostaną odzwierciedlone w spisie treści.

#### P: Jak mogę zmienić styl poziomów nagłówków w spisie treści?

 O: Możesz stylizować poziomy nagłówków w różny sposób, używając różnych stylów akapitów dla każdego poziomu nagłówków. Przypisując różne`StyleIdentifier` wartości do`ParagraphFormat` z`DocumentBuilder`, możesz utworzyć odrębne style dla każdego poziomu nagłówka.

#### P: Czy można dodać dodatkowe formatowanie nagłówków w spisie treści?

 O: Tak, możesz dodać dodatkowe formatowanie do nagłówków spisu treści, takie jak style czcionek, kolory i inne właściwości. Dostosowując`Font` właściwości`DocumentBuilder`, możesz zastosować niestandardowe formatowanie nagłówków.