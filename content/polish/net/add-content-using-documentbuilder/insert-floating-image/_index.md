---
title: Wstaw pływający obraz do dokumentu programu Word
linktitle: Wstaw pływający obraz do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić pływający obraz do dokumentu programu Word za pomocą Aspose.Words dla .NET, korzystając ze szczegółowego przewodnika krok po kroku. Idealny do ulepszania dokumentów.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/insert-floating-image/
---
## Wstęp

Wyobraź sobie, że tworzysz oszałamiający raport lub propozycję, w której obrazy są idealnie umieszczone, aby uzupełniać tekst. Dzięki Aspose.Words dla .NET możesz to osiągnąć bez wysiłku. Ta biblioteka zapewnia zaawansowane funkcje manipulacji dokumentami, dzięki czemu jest idealnym rozwiązaniem dla programistów. W tym samouczku skupimy się na wstawieniu pływającego obrazu przy użyciu klasy DocumentBuilder. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik przeprowadzi Cię przez każdy krok.

## Warunki wstępne

Zanim zagłębimy się w szczegóły, upewnijmy się, że masz wszystko, czego potrzebujesz, aby zacząć:

1.  Aspose.Words dla .NET: Możesz pobrać bibliotekę z[Strona z wydaniami Aspose](https://releases.aspose.com/words/net/).
2. Visual Studio: dowolna wersja obsługująca programowanie .NET.
3. Podstawowa znajomość języka C#: Pomocne będzie zrozumienie podstaw programowania w języku C#.
4. Plik obrazu: plik obrazu, który chcesz wstawić, na przykład logo lub obraz.

## Importuj przestrzenie nazw

Aby użyć Aspose.Words w swoim projekcie, musisz zaimportować niezbędne przestrzenie nazw. Odbywa się to poprzez dodanie następujących wierszy na górze pliku C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Po spełnieniu tych wymagań wstępnych i przestrzeni nazw możemy rozpocząć nasz samouczek.

Podzielmy proces wstawiania pływającego obrazu do dokumentu programu Word na łatwe do wykonania kroki. Każdy krok zostanie szczegółowo wyjaśniony, abyś mógł go wykonać bez żadnych problemów.

## Krok 1: Skonfiguruj swój projekt

Najpierw utwórz nowy projekt C# w programie Visual Studio. Dla uproszczenia możesz wybrać aplikację konsolową.

1. Otwórz Visual Studio i utwórz nowy projekt.
2. Wybierz „Aplikacja konsolowa (.NET Core)” i kliknij „Dalej”.
3. Nazwij swój projekt i wybierz lokalizację, w której chcesz go zapisać. Kliknij „Utwórz”.
4. Zainstaluj Aspose.Words dla .NET za pomocą Menedżera pakietów NuGet. Kliknij projekt prawym przyciskiem myszy w Eksploratorze rozwiązań, wybierz opcję „Zarządzaj pakietami NuGet” i wyszukaj ciąg „Aspose.Words”. Zainstaluj najnowszą wersję.

## Krok 2: Zainicjuj dokument i narzędzie DocumentBuider

Teraz, gdy projekt jest już skonfigurowany, zainicjujmy obiekty Document i DocumentBuilder.

1.  Utwórz nową instancję`Document` klasa:

```csharp
Document doc = new Document();
```

2. Zainicjuj obiekt DocumentBuilder:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

 The`Document` obiekt reprezentuje dokument programu Word, a`DocumentBuilder` pomaga w dodawaniu do niego treści.

## Krok 3: Zdefiniuj ścieżkę obrazu

Następnie określ ścieżkę do pliku obrazu. Upewnij się, że Twój obraz jest dostępny z katalogu projektu.

Zdefiniuj katalog obrazu i nazwę pliku obrazu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imagePath = dataDir + "Transparent background logo.png";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, w której przechowywany jest obraz.

## Krok 4: Wstaw pływający obraz

Po skonfigurowaniu wszystkiego wstawmy pływający obraz do dokumentu.

 Skorzystaj z`InsertImage` metoda`DocumentBuilder` klasa, aby wstawić obraz:

```csharp
builder.InsertImage(imagePath,
   RelativeHorizontalPosition.Margin,
   100,
   RelativeVerticalPosition.Margin,
   100,
   200,
   100,
   WrapType.Square);
```

Oto znaczenie poszczególnych parametrów:
- `imagePath`Ścieżka do pliku obrazu.
- `RelativeHorizontalPosition.Margin`: Pozycja pozioma względem marginesu.
- `100`: Poziome odsunięcie od marginesu (w punktach).
- `RelativeVerticalPosition.Margin`: Pozycja pionowa względem marginesu.
- `100`: Odsunięcie w pionie od marginesu (w punktach).
- `200`: Szerokość obrazu (w punktach).
- `100`: Wysokość obrazu (w punktach).
- `WrapType.Square`: styl zawijania tekstu wokół obrazu.

## Krok 5: Zapisz dokument

Na koniec zapisz dokument w wybranej lokalizacji.

1. Określ ścieżkę pliku wyjściowego:

```csharp
string outputPath = dataDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx";
```

2. Zapisz dokument:

```csharp
doc.Save(outputPath);
```

Twój dokument Word z pływającym obrazem jest już gotowy!

## Wniosek

Wstawianie pływającego obrazu do dokumentu programu Word za pomocą Aspose.Words dla .NET jest prostym procesem, jeśli zostanie podzielony na łatwe do wykonania kroki. Postępując zgodnie z tym przewodnikiem, możesz dodawać profesjonalnie wyglądające obrazy do swoich dokumentów, poprawiając ich atrakcyjność wizualną. Aspose.Words zapewnia solidny interfejs API, który sprawia, że manipulowanie dokumentami jest dziecinnie proste, niezależnie od tego, czy pracujesz nad raportami, propozycjami, czy jakimkolwiek innym typem dokumentu.

## Często zadawane pytania

### Czy mogę wstawić wiele obrazów za pomocą Aspose.Words dla .NET?

 Tak, możesz wstawić wiele obrazów, powtarzając`InsertImage` metodę dla każdego obrazu o pożądanych parametrach.

### Jak zmienić położenie obrazu?

 Możesz dostosować`RelativeHorizontalPosition`, `RelativeVerticalPosition`i parametry przesunięcia, aby ustawić obraz zgodnie z potrzebami.

### Jakie inne rodzaje zawijania są dostępne dla obrazów?

 Aspose.Words obsługuje różne typy zawijania, takie jak`Inline`, `TopBottom`, `Tight`, `Through`i nie tylko. Możesz wybrać ten, który najlepiej pasuje do układu Twojego dokumentu.

### Czy mogę używać różnych formatów obrazów?

Tak, Aspose.Words obsługuje szeroką gamę formatów obrazów, w tym JPEG, PNG, BMP i GIF.

### Jak uzyskać bezpłatną wersję próbną Aspose.Words dla .NET?

 Możesz uzyskać bezpłatną wersję próbną od[Aspose bezpłatna strona próbna](https://releases.aspose.com/).