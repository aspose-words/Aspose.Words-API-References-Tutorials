---
title: Wstaw kształt
linktitle: Wstaw kształt
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawiać kształty w dokumentach programu Word i manipulować nimi za pomocą Aspose.Words dla .NET, korzystając z naszego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-shapes/insert-shape/
---
## Wstęp

Jeśli chodzi o tworzenie atrakcyjnych wizualnie i dobrze zorganizowanych dokumentów programu Word, kształty mogą odegrać kluczową rolę. Niezależnie od tego, czy dodajesz strzałki, ramki, czy nawet złożone, niestandardowe kształty, możliwość programowego manipulowania tymi elementami zapewnia niezrównaną elastyczność. W tym samouczku omówimy, jak wstawiać kształty i manipulować nimi w dokumentach programu Word za pomocą Aspose.Words dla .NET.

## Warunki wstępne

Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:

1.  Aspose.Words dla .NET: Pobierz i zainstaluj najnowszą wersję z[Strona z wydaniami Aspose](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: odpowiednie środowisko programistyczne .NET, takie jak Visual Studio.
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# i podstawowych pojęć.

## Importuj przestrzenie nazw

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Krok 1: Skonfiguruj swój projekt

Zanim zaczniesz wstawiać kształty, musisz skonfigurować swój projekt i dodać bibliotekę Aspose.Words dla .NET.

1. Utwórz nowy projekt: Otwórz program Visual Studio i utwórz nowy projekt aplikacji konsolowej C#.
2. Dodaj Aspose.Words dla .NET: Zainstaluj bibliotekę Aspose.Words dla .NET za pomocą Menedżera pakietów NuGet.

```bash
Install-Package Aspose.Words
```

## Krok 2: Zainicjuj dokument

Najpierw musisz zainicjować nowy dokument i narzędzie do tworzenia dokumentów, które pomoże w skonstruowaniu dokumentu.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Zainicjuj nowy dokument
Document doc = new Document();

// Zainicjuj narzędzie DocumentBuilder, aby pomóc w tworzeniu dokumentu
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstaw kształt

Teraz wstawmy kształt do dokumentu. Zaczniemy od dodania prostego pola tekstowego.

```csharp
// Wstaw kształt pola tekstowego do dokumentu
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100, RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// Obróć kształt
shape.Rotation = 30.0;
```

tym przykładzie wstawiamy pole tekstowe w pozycji (100, 100) o szerokości i wysokości 50 jednostek każde. Obracamy również kształt o 30 stopni.

## Krok 4: Dodaj kolejny kształt

Dodajmy do dokumentu kolejny kształt, tym razem bez określania położenia.

```csharp
// Dodaj kolejny kształt pola tekstowego
Shape secondShape = builder.InsertShape(ShapeType.TextBox, 50, 50);

// Obróć kształt
secondShape.Rotation = 30.0;
```

Ten fragment kodu wstawia kolejne pole tekstowe o tych samych wymiarach i obrocie co pierwsze, ale bez określenia jego położenia.

## Krok 5: Zapisz dokument

 Ostatnim krokiem po dodaniu kształtów jest zapisanie dokumentu. Skorzystamy z`OoxmlSaveOptions` aby określić format zapisu.

```csharp
// Zdefiniuj opcje zapisywania zgodnie z przepisami
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};

// Zapisz dokument
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## Wniosek

I masz to! Udało Ci się wstawić kształty i manipulować nimi w dokumencie programu Word przy użyciu Aspose.Words dla .NET. W tym samouczku omówiono podstawy, ale Aspose.Words oferuje wiele bardziej zaawansowanych funkcji do pracy z kształtami, takich jak niestandardowe style, łączniki i kształty grupowe.

 Więcej szczegółowych informacji można znaleźć na stronie[Aspose.Words dla dokumentacji .NET](https://reference.aspose.com/words/net/).

## Często zadawane pytania

### Jak wstawiać różne typy kształtów?
Możesz zmienić`ShapeType` w`InsertShape` metoda wstawiania różnych typów kształtów, takich jak okręgi, prostokąty i strzałki.

### Czy mogę dodać tekst wewnątrz kształtów?
 Tak, możesz skorzystać z`builder.Write` metoda dodawania tekstu wewnątrz kształtów po ich wstawieniu.

### Czy można stylizować kształty?
 Tak, możesz stylizować kształty, ustawiając właściwości takie jak`FillColor`, `StrokeColor` , I`StrokeWeight`.

### Jak ustawić kształty względem innych elementów?
 Użyj`RelativeHorizontalPosition`I`RelativeVerticalPosition` właściwości umożliwiające położenie kształtów względem innych elementów w dokumencie.

### Czy mogę zgrupować wiele kształtów?
 Tak, Aspose.Words dla .NET umożliwia grupowanie kształtów za pomocą`GroupShape` klasa.