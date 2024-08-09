---
title: Porównanie szczegółowości w dokumencie programu Word
linktitle: Porównanie szczegółowości w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak porównać ziarnistość w dokumencie tekstowym funkcji Aspose.Words dla .NET, która umożliwia porównywanie dokumentów znak po znaku i raportowanie wprowadzonych zmian.
type: docs
weight: 10
url: /pl/net/compare-documents/comparison-granularity/
---
Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje funkcję Porównaj ziarnistość w dokumencie tekstowym Aspose.Words dla .NET.

## Krok 1: Wprowadzenie

Funkcja Compare Granularity w Aspose.Words dla .NET umożliwia porównywanie dokumentów na poziomie znaków. Oznacza to, że każdy znak zostanie porównany, a zmiany zostaną odpowiednio zgłoszone.

## Krok 2: Konfigurowanie środowiska

Zanim zaczniesz, musisz skonfigurować środowisko programistyczne do pracy z Aspose.Words dla .NET. Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words i odpowiedni projekt C#, w którym możesz osadzić kod.

## Krok 3: Dodaj wymagane zespoły

Aby skorzystać z funkcji Compare Granularity w Aspose.Words dla .NET, musisz dodać niezbędne zespoły do swojego projektu. Upewnij się, że masz odpowiednie odniesienia do Aspose.Words w swoim projekcie.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Krok 4: Tworzenie dokumentów

W tym kroku utworzymy dwa dokumenty przy użyciu klasy DocumentBuilder. Dokumenty te zostaną wykorzystane do porównania.

```csharp
// Utwórz dokument A.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Utwórz dokument B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Krok 5: Konfigurowanie opcji porównania

W tym kroku skonfigurujemy opcje porównania, aby określić szczegółowość porównania. Tutaj użyjemy szczegółowości na poziomie znaku.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Krok 6: Porównanie dokumentów

Porównajmy teraz dokumenty za pomocą metody Compare klasy Document. Zmiany zostaną zapisane w dokumencie A.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 The`Compare`metoda porównuje dokument A z dokumentem B i zapisuje zmiany w dokumencie A. Można podać nazwisko autora i datę porównania w celach informacyjnych.

## Wniosek

W tym artykule zbadaliśmy funkcję Compare Granularity w Aspose.Words dla .NET. Funkcja ta umożliwia porównywanie dokumentów na poziomie znakowym i raportowanie zmian. Możesz wykorzystać tę wiedzę do wykonywania szczegółowych porównań dokumentów w swoich projektach.

### Przykładowy kod źródłowy dla szczegółowości porównania przy użyciu Aspose.Words dla .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## Wniosek

W tym samouczku zbadaliśmy funkcję ziarnistości porównania w Aspose.Words dla .NET. Ta funkcja pozwala określić poziom szczegółowości podczas porównywania dokumentów. Wybierając różne poziomy szczegółowości, możesz przeprowadzać szczegółowe porównania na poziomie znaku, słowa lub bloku, w zależności od konkretnych wymagań. Aspose.Words dla .NET zapewnia elastyczną i wydajną funkcję porównywania dokumentów, ułatwiając identyfikację różnic w dokumentach o różnym poziomie szczegółowości.

### Często zadawane pytania

#### P: Jaki jest cel używania ziarnistości porównania w Aspose.Words dla .NET?

Odp.: Szczegółowość porównania w Aspose.Words dla .NET pozwala określić poziom szczegółowości podczas porównywania dokumentów. Dzięki tej funkcji możesz porównywać dokumenty na różnych poziomach, np. na poziomie znaku, na poziomie słowa, a nawet na poziomie bloku. Każdy poziom szczegółowości zapewnia inny poziom szczegółowości wyników porównania.

#### P: Jak używać szczegółowości porównania w Aspose.Words dla .NET?

O: Aby użyć szczegółowości porównania w Aspose.Words dla .NET, wykonaj następujące kroki:
1. Skonfiguruj środowisko programistyczne za pomocą biblioteki Aspose.Words.
2. Dodaj niezbędne zespoły do swojego projektu, odwołując się do Aspose.Words.
3.  Utwórz dokumenty, które chcesz porównać, korzystając z narzędzia`DocumentBuilder` klasa.
4.  Skonfiguruj opcje porównania, tworząc plik`CompareOptions` obiekt i ustawienie`Granularity` właściwość do pożądanego poziomu (np.`Granularity.CharLevel` dla porównania na poziomie postaci).
5.  Skorzystaj z`Compare`metodę na jednym dokumencie, przekazując drugi dokument i`CompareOptions` obiekt jako parametry. Ta metoda porówna dokumenty na podstawie określonej szczegółowości i zapisze zmiany w pierwszym dokumencie.

#### P: Jakie są dostępne poziomy szczegółowości porównania w Aspose.Words dla .NET?

Odp.: Aspose.Words dla .NET zapewnia trzy poziomy szczegółowości porównania:
- `Granularity.CharLevel`: porównuje dokumenty na poziomie znaków.
- `Granularity.WordLevel`: porównuje dokumenty na poziomie słów.
- `Granularity.BlockLevel`: Porównuje dokumenty na poziomie bloku.

#### P: Jak mogę zinterpretować wyniki porównania ze szczegółowością na poziomie znaku?

Odpowiedź: Dzięki szczegółowości na poziomie znaku każdy znak w porównywanych dokumentach jest analizowany pod kątem różnic. Wyniki porównania pokażą zmiany na poziomie poszczególnych postaci, w tym dodatki, usunięcia i modyfikacje.