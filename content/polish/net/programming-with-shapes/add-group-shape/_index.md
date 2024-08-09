---
title: Dodaj kształt grupy
linktitle: Dodaj kształt grupy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodawać kształty grup do dokumentów programu Word za pomocą Aspose.Words dla .NET, korzystając z tego wszechstronnego samouczka krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-shapes/add-group-shape/
---
## Wstęp

Tworzenie złożonych dokumentów z bogatymi elementami wizualnymi może czasami być trudnym zadaniem, szczególnie w przypadku kształtów grupowych. Ale nie bój się! Aspose.Words dla .NET upraszcza ten proces, czyniąc go tak prostym, jak ciasto. W tym samouczku przeprowadzimy Cię przez kolejne etapy dodawania kształtów grupowych do dokumentów programu Word. Gotowy do nurkowania? Zacznijmy!

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1.  Aspose.Words dla .NET: Możesz pobrać go z[Strona z wydaniami Aspose](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: Visual Studio lub dowolne inne IDE kompatybilne z .NET.
3. Podstawowa znajomość języka C#: Znajomość programowania w języku C# będzie dodatkowym atutem.

## Importuj przestrzenie nazw

Na początek musimy zaimportować niezbędne przestrzenie nazw w naszym projekcie. Te przestrzenie nazw zapewniają dostęp do klas i metod wymaganych do manipulowania dokumentami Worda za pomocą Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Krok 1: Zainicjuj dokument

Na początek zainicjujmy nowy dokument programu Word. Pomyśl o tym jak o utworzeniu pustego płótna, na którym będziemy dodawać kształty naszych grup.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.EnsureMinimum();
```

 Tutaj,`EnsureMinimum()` dodaje minimalny zestaw węzłów wymaganych dla dokumentu.

## Krok 2: Utwórz obiekt GroupShape

 Następnie musimy utworzyć`GroupShape`obiekt. Obiekt ten będzie pełnił funkcję pojemnika na inne kształty, co umożliwi nam ich grupowanie.

```csharp
GroupShape groupShape = new GroupShape(doc);
```

## Krok 3: Dodaj kształty do GroupShape

 Teraz dodajmy poszczególne kształty do naszego`GroupShape` pojemnik. Zaczniemy od akcentującego kształtu obramowania, a następnie dodamy kształt przycisku akcji.

### Dodawanie kształtu obramowania akcentującego

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1)
{
    Width = 100,
    Height = 100
};
groupShape.AppendChild(accentBorderShape);
```

 Ten fragment kodu tworzy akcentujący kształt obramowania o szerokości i wysokości 100 jednostek i dodaje go do`GroupShape`.

### Dodawanie kształtu przycisku akcji

```csharp
Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

 Tutaj tworzymy kształt przycisku akcji, ustawiamy go i dodajemy do naszego`GroupShape`.

## Krok 4: Zdefiniuj wymiary GroupShape

 Aby mieć pewność, że nasze kształty dobrze pasują do grupy, musimy ustawić wymiary pliku`GroupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

 Określa szerokość i wysokość`GroupShape` jako 200 jednostek i odpowiednio ustawia rozmiar współrzędnych.

## Krok 5: Wstaw GroupShape do dokumentu

 Teraz wstawmy nasze`GroupShape` do dokumentu za pomocą`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

`DocumentBuilder` zapewnia łatwy sposób dodawania węzłów, w tym kształtów, do dokumentu.

## Krok 6: Zapisz dokument

Na koniec zapisz dokument w określonym katalogu.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

masz to! Twój dokument z kształtami grupowymi jest gotowy.

## Wniosek

Dodawanie kształtów grupowych do dokumentów programu Word nie musi być skomplikowanym procesem. Dzięki Aspose.Words dla .NET możesz z łatwością tworzyć kształty i manipulować nimi, dzięki czemu Twoje dokumenty będą bardziej atrakcyjne wizualnie i funkcjonalne. Postępuj zgodnie z instrukcjami opisanymi w tym samouczku, a w mgnieniu oka staniesz się profesjonalistą!

## Często zadawane pytania

### Czy mogę dodać więcej niż dwa kształty do GroupShape?
 Tak, możesz dodać tyle kształtów, ile potrzebujesz`GroupShape` . Po prostu skorzystaj z`AppendChild` metoda dla każdego kształtu.

### Czy można stylizować kształty w GroupShape?
 Absolutnie! Każdy kształt można stylizować indywidualnie, korzystając z właściwości dostępnych w pliku`Shape` klasa.

### Jak ustawić GroupShape w dokumencie?
 Możesz ustawić`GroupShape` ustawiając jego`Left`I`Top` właściwości.

### Czy mogę dodać tekst do kształtów w GroupShape?
 Tak, możesz dodawać tekst do kształtów za pomocą`AppendChild` metoda dodania a`Paragraph` zawierający`Run` węzły z tekstem.

### Czy możliwe jest dynamiczne grupowanie kształtów na podstawie danych wejściowych użytkownika?
Tak, możesz dynamicznie tworzyć i grupować kształty na podstawie danych wprowadzonych przez użytkownika, dostosowując odpowiednio właściwości i metody.