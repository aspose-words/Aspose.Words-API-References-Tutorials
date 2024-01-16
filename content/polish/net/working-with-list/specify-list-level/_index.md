---
title: Określ poziom listy
linktitle: Określ poziom listy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak określić poziom listy w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-list/specify-list-level/
---

W tym samouczku krok po kroku pokażemy, jak określić poziom listy w dokumencie programu Word za pomocą Aspose.Words dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach.

 Aby rozpocząć, upewnij się, że masz zainstalowane i skonfigurowane Aspose.Words for .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj bibliotekę z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Tworzenie dokumentu i generatora dokumentów

Najpierw utwórz nowy dokument i powiązany z nim generator dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Tworzenie i stosowanie listy numerowanej

Następnie utwórz listę numerowaną na podstawie jednego z szablonów list programu Microsoft Word i zastosuj ją do bieżącego akapitu w kreatorze dokumentów:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Krok 3: Specyfikacja na poziomie listy

 Użyj narzędzia do tworzenia dokumentów`ListLevelNumber` aby określić poziom listy i dodać tekst do akapitu:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Powtórz te kroki, aby określić poziomy listy i dodać tekst na każdym poziomie.

## Krok 4: Tworzenie i stosowanie listy wypunktowanej

Możesz także utworzyć i zastosować listę punktowaną, korzystając z jednego z szablonów list programu Microsoft Word:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Krok 5: Dodawanie tekstu do poziomów listy wypunktowanej

 Użyj`ListLevelNumber` ponownie, aby określić poziom listy punktowanej i dodać tekst:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Krok 6: Zatrzymaj formatowanie listy

 Aby zatrzymać formatowanie listy, ustaw`null` do`List` właściwość generatora dokumentów:

```csharp
builder. ListFormat. List = null;
```

## Krok 7: Zapisanie zmodyfikowanego dokumentu

Zapisz zmodyfikowany dokument:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Więc ! Pomyślnie określiłeś poziom listy w dokumencie programu Word przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy, aby określić poziom listy

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Utwórz listę numerowaną w oparciu o jeden z szablonów list Microsoft Word
// zastosuj go do bieżącego akapitu kreatora dokumentu.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Na tej liście jest dziewięć poziomów, wypróbujmy je wszystkie.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Utwórz listę punktowaną w oparciu o jeden z szablonów list programu Microsoft Word
// zastosuj go do bieżącego akapitu kreatora dokumentu.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Jest to sposób na zatrzymanie formatowania listy.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### Często zadawane pytania

#### P: Jak mogę określić poziom listy w Aspose.Words?

 O: Aby określić poziom listy w Aspose.Words, musisz utworzyć instancję`List` klasę i podaj jej listę numerowaną. Następnie możesz użyć`Paragraph.ListFormat.ListLevelNumber` Aby określić poziom każdego elementu listy. Możesz powiązać tę listę z sekcją dokumentu, aby elementy listy miały pożądany poziom.

#### P: Czy można zmienić format numeracji elementów listy w Aspose.Words?

 O: Tak, możesz zmienić format numeracji elementów listy w Aspose.Words. The`ListLevel` class oferuje do tego kilka właściwości, takich jak`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`itp. Możesz użyć tych właściwości, aby ustawić format numeracji elementów listy, takich jak cyfry arabskie, cyfry rzymskie, litery itp.

#### P: Czy mogę dodać dodatkowe poziomy do listy numerowanej w Aspose.Words?

 O: Tak, możliwe jest dodanie dodatkowych poziomów do listy numerowanej w Aspose.Words. The`ListLevel` class umożliwia ustawienie właściwości formatowania dla każdego poziomu listy. Możesz ustawić opcje takie jak przedrostek, przyrostek, wyrównanie, wcięcie itp. Umożliwia to tworzenie list o wielu poziomach hierarchii.


