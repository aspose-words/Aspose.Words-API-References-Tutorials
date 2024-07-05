---
title: Uzyskaj odstępy między wierszami czcionki
linktitle: Uzyskaj odstępy między wierszami czcionki
second_title: Aspose.Words API do przetwarzania dokumentów
description: W tym samouczku dowiesz się, jak uzyskać odstępy między wierszami czcionki w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fonts/get-font-line-spacing/
---
W tym samouczku pokażemy, jak uzyskać odstępy między wierszami czcionki w dokumencie programu Word przy użyciu biblioteki Aspose.Words dla .NET. Odstęp między wierszami czcionki określa pionowy odstęp między wierszami tekstu. Poprowadzimy Cię krok po kroku, aby pomóc Ci zrozumieć i wdrożyć kod w Twoim projekcie .NET.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
- Praktyczna znajomość języka programowania C#
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim projekcie

## Krok 1: Utwórz nowy dokument i generator dokumentów
 Najpierw utworzymy nowy dokument, tworząc instancję pliku`Document` klasę i narzędzie do tworzenia dokumentów, tworząc instancję`DocumentBuilder` klasa.

```csharp
// Utwórz nowy dokument
Document doc = new Document();

//Utwórz generator dokumentów
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Skonfiguruj czcionkę
 Następnie skonfigurujemy czcionkę, ustawiając`Name` właściwość generatora dokumentów.

```csharp
// Skonfiguruj czcionkę
builder.Font.Name = "Calibri";
```

## Krok 3: Dodaj tekst do dokumentu
Użyjemy teraz generatora dokumentów, aby dodać sformatowany tekst do dokumentu.

```csharp
// Dodaj tekst do dokumentu
builder. Writen("qText");
```

## Krok 4: Uzyskaj odstępy między wierszami czcionki
 Teraz uzyskamy dostęp do`Font` obiekt pierwszego akapitu dokumentu i pobierz wartość`LineSpacing` nieruchomość.

```csharp
// Uzyskaj odstępy między wierszami czcionki
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Przykładowy kod źródłowy funkcji Uzyskaj odstępy między wierszami czcionki przy użyciu Aspose.Words dla .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Wniosek
W tym samouczku widzieliśmy, jak uzyskać odstępy między wierszami czcionki w dokumencie programu Word za pomocą Aspose.Words dla .NET. Odstępy między wierszami czcionki są ważne przy kontrolowaniu odstępów w pionie między wierszami tekstu. Możesz skorzystać z tej funkcji, aby dostosować wygląd tekstu w dokumentach.

### Często zadawane pytania

#### P: Jak mogę zmienić odstępy między wierszami określonego tekstu w dokumencie programu Word?

Odp.: Dzięki Aspose.Words możesz łatwo zmienić odstępy między wierszami określonego tekstu w dokumencie programu Word. Użyj API, aby zaznaczyć żądany tekst i dostosować odstępy między wierszami, podając odpowiednią wartość.

#### P: Czy można zastosować dokładne odstępy między wierszami w dokumencie programu Word?

Odp.: Tak, Aspose.Words umożliwia zastosowanie dokładnych odstępów między wierszami w dokumencie programu Word. Za pomocą interfejsu API możesz określić dokładną wartość odstępu między wierszami.

#### P: Jak mogę dostosować odstępy między wierszami w całym dokumencie programu Word?

Odp.: Dzięki Aspose.Words możesz łatwo dostosować odstępy między wierszami w całym dokumencie programu Word. Użyj metod udostępnianych przez API, aby określić żądany odstęp między wierszami dla całego dokumentu.

#### P: Czy Aspose.Words obsługuje wiele odstępów między wierszami?

Odp.: Tak, Aspose.Words obsługuje wiele odstępów między wierszami w dokumentach programu Word. Dla linii tekstu możesz ustawić wielokrotne odstępy, na przykład 1,5-krotne lub 2-krotne odstępy normalne.

#### P: Jak mogę uniknąć problemów z nakładaniem się linii podczas dostosowywania odstępów między wierszami?

Odp.: Aby uniknąć problemów z nakładaniem się linii podczas dostosowywania odstępów między liniami, pamiętaj o wybraniu odpowiednich wartości odstępów. Przetestuj także ostateczne renderowanie dokumentu, aby upewnić się, że tekst pozostaje czytelny i dobrze sformatowany.