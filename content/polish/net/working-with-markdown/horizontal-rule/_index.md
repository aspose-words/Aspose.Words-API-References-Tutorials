---
title: Linia pozioma
linktitle: Linia pozioma
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić linię poziomą za pomocą Aspose.Words dla .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/horizontal-rule/
---

W tym przykładzie pokażemy, jak używać funkcji linii poziomej w Aspose.Words dla .NET. Linia pozioma służy do wizualnego oddzielania sekcji dokumentu.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Wstawianie linii poziomej

 Linię poziomą możemy wstawić za pomocą`InsertHorizontalRule` metoda generatora dokumentów.

```csharp
builder. InsertHorizontalRule();
```

## Przykładowy kod źródłowy reguły poziomej z Aspose.Words dla .NET

```csharp
// Użyj narzędzia do tworzenia dokumentów, aby dodać treść do dokumentu.
DocumentBuilder builder = new DocumentBuilder();

// Wstaw linijkę poziomą.
builder.InsertHorizontalRule();
```

Gratulacje! Nauczyłeś się teraz, jak korzystać z funkcji linii poziomej w Aspose.Words dla .NET.


### Często zadawane pytania

#### P: Jak utworzyć poziomą linijkę w Markdown?

Odp.: Aby utworzyć poziomą linijkę w Markdown, możesz użyć jednego z następujących symboli w pustej linii: trzy gwiazdki (\***), trzy kreski (\---) lub trzy podkreślenia (\___).

#### P: Czy mogę dostosować wygląd poziomej linijki w Markdown?

Odp.: W standardowym Markdown nie ma możliwości dostosowania wyglądu poziomych linijek. Jednak niektóre zaawansowane edytory i rozszerzenia Markdown oferują dodatkowe funkcje dostosowywania.

#### P: Czy wszystkie edytory Markdown obsługują linijki poziome?

Odp.: Tak, najpopularniejsze edytory Markdown obsługują linijki poziome. Jednak zawsze najlepiej jest sprawdzić dokumentację konkretnego dostawcy, aby upewnić się, że jest ona obsługiwana.

#### P: Jakie inne elementy mogę utworzyć w Markdown?

O: Oprócz linijek poziomych w Markdown możesz tworzyć tytuły, akapity, listy, łącza, obrazy, tabele i nie tylko.