---
title: Określ domyślną czcionkę podczas renderowania
linktitle: Określ domyślną czcionkę podczas renderowania
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący określania domyślnej czcionki podczas renderowania dokumentu przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fonts/specify-default-font-when-rendering/
---

tym samouczku przeprowadzimy Cię krok po kroku przez proces określania domyślnej czcionki podczas renderowania dokumentu za pomocą Aspose.Words dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak określić domyślną czcionkę, która będzie używana podczas renderowania dokumentów za pomocą Aspose.Words dla .NET.

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja, w której chcesz zapisać edytowany, wyrenderowany dokument. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Załaduj dokument do renderowania
 Następnie musisz załadować dokument do renderowania za pomocą`Document` klasa. Pamiętaj, aby określić poprawną ścieżkę dokumentu.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Ustaw domyślną czcionkę
 Teraz możesz określić domyślną czcionkę używaną podczas renderowania, tworząc instancję pliku`FontSettings` klasę i ustawienie`DefaultFontName` własność`DefaultFontSubstitution` sprzeciwiać się`DefaultFontSubstitution` obiekt`SubstitutionSettings` z`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Krok 4: Zapisz wyrenderowany dokument
 Na koniec możesz zapisać wyrenderowany dokument do pliku za pomocą`Save()` metoda`Document` klasa. Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Przykładowy kod źródłowy dla opcji Określ domyślną czcionkę podczas renderowania przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Jeśli podczas renderowania nie można znaleźć zdefiniowanej tutaj domyślnej czcionki
// Zamiast tego używana jest najbliższa czcionka na komputerze.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Wniosek
tym samouczku nauczyliśmy się, jak określić domyślną czcionkę podczas renderowania dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz łatwo ustawić domyślną czcionkę, która będzie używana podczas renderowania dokumentów. Aspose.Words oferuje potężny i elastyczny interfejs API do przetwarzania tekstu z czcionkami w dokumentach. Dzięki tej wiedzy możesz kontrolować i dostosowywać renderowanie dokumentów do swoich konkretnych potrzeb.

### Często zadawane pytania

#### P: Jak mogę określić domyślną czcionkę podczas konwersji do formatu PDF w Aspose.Words?

 Odp.: Aby określić domyślną czcionkę podczas konwersji do formatu PDF w Aspose.Words, możesz użyć`PdfOptions` klasę i ustaw`DefaultFontName`właściwość na nazwę żądanej czcionki.

#### P: Co się stanie, jeśli domyślna czcionka nie będzie dostępna podczas konwersji do formatu PDF?

Odp.: Jeśli określona domyślna czcionka nie jest dostępna podczas konwersji do formatu PDF, Aspose.Words użyje czcionki zastępczej do wyświetlenia tekstu w przekonwertowanym dokumencie. Może to spowodować niewielką różnicę w wyglądzie czcionki oryginalnej.

#### P: Czy mogę określić domyślną czcionkę dla innych formatów wyjściowych, takich jak DOCX lub HTML?

O: Tak, możesz określić domyślną czcionkę dla innych formatów wyjściowych, takich jak DOCX lub HTML, używając odpowiednich opcji konwersji i ustawiając odpowiednią właściwość dla każdego formatu.

#### P: Jak mogę sprawdzić domyślną czcionkę określoną w Aspose.Words?

 Odp.: Aby sprawdzić domyślną czcionkę określoną w Aspose.Words, możesz użyć`DefaultFontName` własność`PdfOptions` class i pobierz nazwę skonfigurowanej czcionki.

#### P: Czy można określić inną domyślną czcionkę dla każdej sekcji dokumentu?

O: Tak, możliwe jest określenie innej domyślnej czcionki dla każdej sekcji dokumentu, korzystając z opcji formatowania właściwych dla każdej sekcji. Wymagałoby to jednak bardziej zaawansowanej manipulacji dokumentem przy użyciu funkcji Aspose.Words.