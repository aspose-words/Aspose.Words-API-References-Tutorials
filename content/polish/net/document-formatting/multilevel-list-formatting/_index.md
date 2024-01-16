---
title: Wielopoziomowe formatowanie listy w dokumencie programu Word
linktitle: Wielopoziomowe formatowanie listy w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć listę wielopoziomową i zastosować niestandardowe formatowanie w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/document-formatting/multilevel-list-formatting/
---
W tym samouczku pokażemy, jak używać wielopoziomowego formatowania list w funkcji dokumentu tekstowego w Aspose.Words dla .NET. Wykonaj poniższe kroki, aby zrozumieć kod źródłowy i zastosować zmiany.

## Krok 1: Tworzenie i konfiguracja dokumentu

Aby rozpocząć, utwórz nowy dokument i powiązany obiekt DocumentBuilder. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Formatowanie listy wielopoziomowej

Zastosujemy teraz formatowanie listy wielopoziomowej wykorzystując metody dostępne w obiekcie DocumentBuilder. Oto jak:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Krok 3: Zapisywanie dokumentu

 Po wstawieniu pola formularza wprowadzania tekstu zapisz dokument w wybranej lokalizacji za pomocą przycisku`Save` metoda. Upewnij się, że podałeś odpowiednią ścieżkę pliku:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Przykładowy kod źródłowy dla formatowania listy wielopoziomowej przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy funkcji formatowania list wielopoziomowych w Aspose.Words dla .NET:


```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Za pomocą tego kodu będziesz mógł utworzyć listę wielopoziomową i zastosować odpowiednie formatowanie do każdego poziomu za pomocą Aspose.Words dla .NET.


## Wniosek

W tym samouczku zbadaliśmy proces wykorzystania funkcji formatowania listy wielopoziomowej w dokumencie programu Word za pomocą Aspose.Words dla .NET. Wykonując opisane czynności, możesz tworzyć dobrze zorganizowane listy wielopoziomowe, poprawiając strukturę i czytelność dokumentów.

### Często zadawane pytania

#### P: Co to jest lista wielopoziomowa w dokumencie programu Word?

O: Lista wielopoziomowa w dokumencie programu Word to lista hierarchiczna, która umożliwia organizowanie elementów na różnych poziomach podelementów. Pomaga przedstawić informacje w uporządkowany sposób, ułatwiając czytelnikom zrozumienie treści.

#### P: Czy mogę dostosować wygląd listy wielopoziomowej?

Odp.: Tak, możesz dostosować wygląd listy wielopoziomowej w dokumencie programu Word. Stosując różne style, takie jak wypunktowania, cyfry lub litery, a także dostosowując wcięcia i odstępy, możesz utworzyć atrakcyjną wizualnie i uporządkowaną listę.

#### P: Czy Aspose.Words dla .NET obsługuje inne opcje formatowania list?

O: Tak, Aspose.Words dla .NET zapewnia kompleksowy zestaw funkcji do formatowania list. Obsługuje różne typy list, w tym listy punktowane, listy numerowane i listy wielopoziomowe. Możesz manipulować formatowaniem list, dodawać lub usuwać elementy i dostosowywać ich wygląd.

#### P: Czy mogę używać Aspose.Words dla .NET do pracy z innymi elementami dokumentu?

Odp.: Tak, Aspose.Words dla .NET oferuje szerokie możliwości pracy z różnymi elementami dokumentu, takimi jak akapity, tabele, obrazy i inne. Umożliwia programowe tworzenie, modyfikowanie i konwertowanie dokumentów programu Word, usprawniając zadania przetwarzania dokumentów.