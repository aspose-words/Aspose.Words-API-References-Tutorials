---
title: Indeksowany format 1Bpp
linktitle: Indeksowany format 1Bpp
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak przekonwertować dokument programu Word na obraz indeksowany o wielkości 1 Bpp przy użyciu Aspose.Words dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby ułatwić konwersję.
type: docs
weight: 10
url: /pl/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
## Wstęp

Czy zastanawiałeś się kiedyś, jak zapisać dokument programu Word jako czarno-biały obraz za pomocą zaledwie kilku linii kodu? Cóż, masz szczęście! Dzisiaj zagłębimy się w małą sztuczkę przy użyciu Aspose.Words dla .NET, która pozwala konwertować dokumenty na obrazy indeksowane 1Bpp. Ten format jest idealny do niektórych rodzajów cyfrowej archiwizacji, drukowania lub gdy trzeba zaoszczędzić miejsce. Podzielimy każdy krok, aby było to tak proste, jak bułka z masłem. Gotowy żeby zacząć? Zanurzmy się!

## Warunki wstępne

Zanim ubrudzimy sobie ręce, warto mieć pod ręką kilka rzeczy:

-  Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną bibliotekę. Możesz[Pobierz to tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne .NET: Visual Studio to dobra opcja, ale możesz używać dowolnego środowiska, w którym czujesz się komfortowo.
- Podstawowa znajomość języka C#: Nie martw się, uprościmy to, ale odrobina znajomości języka C# będzie pomocna.
- Dokument programu Word: Przygotuj przykładowy dokument programu Word do konwersji.

## Importuj przestrzenie nazw

Po pierwsze, musimy zaimportować niezbędne przestrzenie nazw. Jest to kluczowe, ponieważ pozwala nam uzyskać dostęp do klas i metod, których potrzebujemy z Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Krok 1: Skonfiguruj katalog dokumentów

Musisz podać ścieżkę do katalogu dokumentów. W tym miejscu przechowywany jest dokument programu Word i zapisywany jest przekonwertowany obraz.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument Word

 Teraz załadujmy dokument programu Word do pliku Aspose.Words`Document` obiekt. Obiekt ten reprezentuje plik programu Word i umożliwia manipulowanie nim.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Skonfiguruj opcje zapisywania obrazu

 Następnie musimy skonfigurować`ImageSaveOptions`To tutaj dzieje się magia. Skonfigurujemy go tak, aby zapisywał obraz w formacie PNG z trybem kolorów indeksowanych 1Bpp.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1),
    ImageColorMode = ImageColorMode.BlackAndWhite,
    PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

- SaveFormat.Png: Określa, że chcemy zapisać dokument jako obraz PNG.
- PageSet(1): Oznacza to, że konwertujemy tylko pierwszą stronę.
- ImageColorMode.BlackAndWhite: Ustawia obraz na czarno-biały.
- ImagePixelFormat.Format1bppIndexed: Ustawia format obrazu na indeksowany 1Bpp.

## Krok 4: Zapisz dokument jako obraz

 Na koniec zapisujemy dokument jako obraz za pomocą`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

## Wniosek

I masz to! Za pomocą zaledwie kilku linii kodu przekształciłeś dokument programu Word w obraz indeksowany o wielkości 1 Bpp przy użyciu Aspose.Words dla .NET. Ta metoda jest niezwykle przydatna do tworzenia obrazów o wysokim kontraście i zajmujących mało miejsca z dokumentów. Teraz możesz łatwo zintegrować to ze swoimi projektami i przepływami pracy. Miłego kodowania!

## Często zadawane pytania

### Co to jest obraz indeksowany 1Bpp?
Obraz indeksowany 1 Bpp (1 bit na piksel) to czarno-biały format obrazu, w którym każdy piksel jest reprezentowany przez pojedynczy bit, 0 lub 1. Ten format zajmuje bardzo mało miejsca.

### Czy mogę przekonwertować wiele stron dokumentu Word na raz?
 Tak, możesz. Zmodyfikuj`PageSet` nieruchomość w`ImageSaveOptions` aby uwzględnić wiele stron lub cały dokument.

### Czy potrzebuję licencji, aby używać Aspose.Words dla .NET?
 Tak, Aspose.Words dla .NET wymaga licencji dla pełnej funkcjonalności. Możesz dostać[licencja tymczasowa tutaj](https://purchase.aspose.com/temporary-license/).

### Na jakie inne formaty obrazów mogę przekonwertować dokument programu Word?
 Aspose.Words obsługuje różne formaty obrazów, w tym JPEG, BMP i TIFF. Po prostu zmień`SaveFormat` w`ImageSaveOptions`.

### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Words dla .NET?
 Szczegółową dokumentację można znaleźć na stronie[Strona dokumentacji Aspose.Words dla platformy .NET](https://reference.aspose.com/words/net/).
