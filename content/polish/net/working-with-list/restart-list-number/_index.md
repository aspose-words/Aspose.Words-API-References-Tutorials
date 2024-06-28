---
title: Uruchom ponownie numer listy
linktitle: Uruchom ponownie numer listy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zresetować numer listy w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-list/restart-list-number/
---
W tym samouczku krok po kroku pokażemy, jak zresetować numer listy w dokumencie programu Word za pomocą Aspose.Words dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach.

 Aby rozpocząć, upewnij się, że masz zainstalowane i skonfigurowane Aspose.Words for .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj bibliotekę z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Tworzenie dokumentu i generatora dokumentów

Najpierw utwórz nowy dokument i powiązany z nim generator dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Tworzenie i dostosowywanie pierwszej listy

Następnie utwórz listę na podstawie istniejącego szablonu, a następnie dostosuj jej poziomy:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Krok 3: Dodanie pozycji do pierwszej listy

Użyj narzędzia do tworzenia dokumentów, aby dodać elementy do pierwszej listy i usunąć numery list:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Krok 4: Tworzenie i dostosowywanie drugiej listy

Aby ponownie wykorzystać pierwszą listę poprzez zresetowanie numeru, utwórz kopię oryginalnego układu listy:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

W razie potrzeby możesz także wprowadzić dodatkowe zmiany na drugiej liście.

## Krok 5: Dodanie pozycji do drugiej listy

Użyj ponownie narzędzia do tworzenia dokumentów, aby dodać elementy do drugiej listy i usunąć numery list:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Krok 6: Zapisz zmodyfikowany dokument

Na koniec zapisz zmodyfikowany dokument:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Więc ! Pomyślnie zresetowałeś numer listy w dokumencie programu Word przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy do resetowania numeru listy

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Utwórz listę na podstawie szablonu.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Aby ponownie wykorzystać pierwszą listę, musimy ponownie rozpocząć numerację, tworząc kopię oryginalnego formatowania listy.
List list2 = doc.Lists.AddCopy(list1);

// Nową listę możemy w dowolny sposób modyfikować, łącznie z ustawieniem nowego numeru startowego.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### Często zadawane pytania

#### P: Jak mogę ponownie rozpocząć numerację listy w Aspose.Words?

 O: Aby ponownie rozpocząć numerację listy w Aspose.Words, możesz użyć opcji`ListRestartAtNumber` metoda`List` klasa. Metoda ta pozwala na ustawienie nowej wartości wybierania, od której lista ma zostać wznowiona. Możesz na przykład użyć`list.ListRestartAtNumber(1)` aby wznowić numerację od 1.

#### P: Czy można dostosować prefiks i sufiks wznowionej numeracji list w Aspose.Words?

 O: Tak, możesz dostosować przedrostek i przyrostek ponownie uruchomionej numeracji list w Aspose.Words. The`ListLevel` klasa oferuje właściwości takie jak`ListLevel.NumberPrefix` I`ListLevel.NumberSuffix`które pozwalają określić przedrostek i przyrostek dla każdego poziomu na liście. Możesz użyć tych właściwości, aby dostosować przedrostek i przyrostek zgodnie z potrzebami.

#### P: Jak mogę określić konkretną wartość numeracji, od której lista powinna zostać wznowiona?

 O: Aby określić konkretną wartość liczbową, od której lista powinna zostać ponownie uruchomiona, możesz użyć opcji`ListRestartAtNumber` metoda przekazująca żądaną wartość jako argument. Na przykład, aby wznowić numerację od 5, możesz użyć`list.ListRestartAtNumber(5)`.

#### P: Czy można zrestartować wielopoziomową numerację list w Aspose.Words?

 O: Tak, Aspose.Words obsługuje ponowne numerowanie wielu poziomów list. Można zastosować`ListRestartAtNumber` na każdym poziomie listy, aby indywidualnie ponownie rozpocząć numerację. Możesz na przykład użyć`list.Levels[0].ListRestartAtNumber(1)` aby zrestartować pierwszy poziom listy od 1, i`list.Levels[1].ListRestartAtNumber(1)` aby zrestartować listę drugiego poziomu, zaczynając od 1 i tak dalej.



