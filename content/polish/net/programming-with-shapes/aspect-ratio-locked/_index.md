---
title: Proporcje obrazu zablokowane
linktitle: Proporcje obrazu zablokowane
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zablokować proporcje kształtów w dokumentach programu Word za pomocą Aspose.Words dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby zachować proporcje obrazów i kształtów.
type: docs
weight: 10
url: /pl/net/programming-with-shapes/aspect-ratio-locked/
---
## Wstęp

Czy zastanawiałeś się kiedyś, jak zachować idealne proporcje obrazów i kształtów w dokumentach programu Word? Czasami musisz upewnić się, że obrazy i kształty nie ulegną zniekształceniu podczas zmiany rozmiaru. W tym miejscu przydaje się blokowanie proporcji. W tym samouczku omówimy, jak ustawić współczynnik proporcji kształtów w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Podzielimy to na łatwe do wykonania kroki, dzięki czemu będziesz mieć pewność, że będziesz mógł bez obaw zastosować te umiejętności w swoich projektach.

## Warunki wstępne

Zanim zagłębimy się w kod, przyjrzyjmy się, czego potrzebujesz, aby zacząć:

- Biblioteka Aspose.Words dla .NET: Musisz mieć zainstalowaną bibliotekę Aspose.Words dla .NET. Jeśli jeszcze tego nie zrobiłeś, możesz[pobierz go tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: Upewnij się, że masz skonfigurowane środowisko programistyczne .NET. Visual Studio to popularny wybór.
- Podstawowa znajomość języka C#: Pomocna będzie pewna znajomość programowania w języku C#.

## Importuj przestrzenie nazw

Na początek zaimportujmy niezbędne przestrzenie nazw. Te przestrzenie nazw zapewnią nam dostęp do klas i metod potrzebnych do pracy z dokumentami i kształtami programu Word.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Krok 1: Skonfiguruj katalog dokumentów

 Zanim zaczniemy manipulować kształtami, musimy założyć katalog, w którym będą przechowywane nasze dokumenty. Dla uproszczenia użyjemy symbolu zastępczego`YOUR DOCUMENT DIRECTORY`. Zastąp to rzeczywistą ścieżką do katalogu dokumentów.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz nowy dokument

Następnie utworzymy nowy dokument programu Word przy użyciu Aspose.Words. Dokument ten posłuży nam jako płótno do dodawania kształtów i obrazów.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tutaj tworzymy instancję`Document` klasę i użyj a`DocumentBuilder` aby pomóc nam w tworzeniu treści dokumentu.

## Krok 3: Wstaw obraz

 Teraz wstawmy obraz do naszego dokumentu. Skorzystamy z`InsertImage` metoda`DocumentBuilder`klasa. Upewnij się, że masz obraz w określonym katalogu.

```csharp
Shape shape = builder.InsertImage(dataDir + "Transparent background logo.png");
```

 Zastępować`dataDir + "Transparent background logo.png"` ze ścieżką do pliku obrazu.

## Krok 4: Zablokuj współczynnik proporcji

Po wstawieniu obrazu możemy zablokować jego proporcje. Zablokowanie proporcji obrazu gwarantuje, że proporcje obrazu pozostaną stałe podczas zmiany rozmiaru.

```csharp
shape.AspectRatioLocked = true;
```

 Ustawienie`AspectRatioLocked` Do`true` gwarantuje, że obraz zachowa oryginalne proporcje.

## Krok 5: Zapisz dokument

Na koniec zapiszemy dokument we wskazanym katalogu. W tym kroku zapisywane są wszystkie zmiany, które dokonaliśmy w pliku dokumentu.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się ustawiać współczynnik proporcji kształtów w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Wykonując poniższe kroki, możesz mieć pewność, że obrazy i kształty zachowają swoje proporcje, dzięki czemu Twoje dokumenty będą wyglądać profesjonalnie i dopracowanie. Możesz eksperymentować z różnymi obrazami i kształtami, aby zobaczyć, jak działa funkcja blokowania proporcji obrazu w różnych scenariuszach.

## Często zadawane pytania

### Czy mogę odblokować proporcje po ich zablokowaniu?
Tak, możesz odblokować współczynnik proporcji, ustawiając`shape.AspectRatioLocked = false`.

### Co się stanie, jeśli zmienię rozmiar obrazu przy zablokowanym współczynniku proporcji?
Rozmiar obrazu zmieni się proporcjonalnie, zachowując oryginalny stosunek szerokości do wysokości.

### Czy mogę zastosować to do innych kształtów oprócz obrazów?
Absolutnie! Funkcję blokowania proporcji można zastosować do dowolnego kształtu, w tym prostokątów, okręgów i innych.

### Czy Aspose.Words dla .NET jest kompatybilny z .NET Core?
Tak, Aspose.Words dla .NET obsługuje zarówno .NET Framework, jak i .NET Core.

### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Words dla .NET?
 Można znaleźć obszerną dokumentację[Tutaj](https://reference.aspose.com/words/net/).