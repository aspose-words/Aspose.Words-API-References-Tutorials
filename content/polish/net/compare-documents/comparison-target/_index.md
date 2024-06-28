---
title: Cel porównawczy w dokumencie programu Word
linktitle: Cel porównawczy w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak porównać cel w dokumencie programu Word w Aspose.Words dla .NET, który pozwala na porównywanie dokumentów i generowanie nowego dokumentu zawierającego wprowadzone zmiany.
type: docs
weight: 10
url: /pl/net/compare-documents/comparison-target/
---
Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje cel porównania w funkcjonalności dokumentu Word Aspose.Words dla .NET.

## Krok 1: Wprowadzenie

Funkcja porównywania obiektów docelowych Aspose.Words dla .NET umożliwia porównanie dwóch dokumentów i wygenerowanie nowego dokumentu zawierającego zmiany wprowadzone w dokumencie docelowym. Może to być przydatne do śledzenia zmian wprowadzonych pomiędzy różnymi wersjami dokumentu.

## Krok 2: Konfigurowanie środowiska

Zanim zaczniesz, musisz skonfigurować środowisko programistyczne do pracy z Aspose.Words dla .NET. Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words i odpowiedni projekt C#, w którym możesz osadzić kod.

## Krok 3: Dodaj wymagane zespoły

Aby skorzystać z docelowej funkcji porównania Aspose.Words dla .NET, musisz dodać niezbędne zespoły do swojego projektu. Upewnij się, że masz odpowiednie odniesienia do Aspose.Words w swoim projekcie.

```csharp
using Aspose.Words;
```

## Krok 4: Inicjalizacja dokumentu

Na tym etapie zainicjujemy dwa dokumenty do porównania. Musisz określić ścieżkę katalogu, w którym znajdują się Twoje dokumenty, a także nazwę dokumentu źródłowego.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Inicjalizacja dokumentu A do porównania.
Document docA = new Document(dataDir + "DocumentA.docx");

// Sklonuj dokument A, aby utworzyć identyczną kopię dokumentu B.
Document docB = docA.Clone();
```

## Krok 5: Konfigurowanie opcji porównania

W tym kroku skonfigurujemy opcje porównania, aby określić zachowanie porównania. Opcje obejmują możliwość ignorowania formatowania, a także cel porównania, czyli opcję „Pokaż zmiany w” w oknie dialogowym „Porównaj dokumenty” programu Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Krok 6: Porównanie dokumentów

Teraz porównamy dokumenty i wygenerujemy wynik w nowym dokumencie.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 The`Compare`metoda porównuje dokument A z dokumentem B i zapisuje zmiany w dokumencie A. Możesz podać nazwę użytkownika i datę porównania w celach informacyjnych.

### Przykładowy kod źródłowy narzędzia Compare Target przy użyciu Aspose.Words dla platformy .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Dotyczy opcji Microsoft Word „Pokaż zmiany w” w oknie dialogowym „Porównaj dokumenty”.
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Wniosek

W tym artykule zbadaliśmy funkcję celu różnicowego Aspose.Words dla .NET. Funkcja ta umożliwia porównanie dwóch dokumentów i wygenerowanie nowego dokumentu zawierającego wprowadzone zmiany. Możesz wykorzystać tę wiedzę do śledzenia zmian pomiędzy różnymi wersjami dokumentów.

### Często zadawane pytania

#### P: Jaki jest cel używania celu porównania w Aspose.Words dla .NET?

Odp.: Cel porównania w Aspose.Words dla .NET umożliwia porównanie dwóch dokumentów i wygenerowanie nowego dokumentu zawierającego zmiany wprowadzone w dokumencie docelowym. Ta funkcja jest przydatna do śledzenia zmian wprowadzonych pomiędzy różnymi wersjami dokumentu i wizualizacji różnic w osobnym dokumencie.

#### P: Jak używać celu porównania w Aspose.Words dla .NET?

O: Aby użyć celu porównania w Aspose.Words dla .NET, wykonaj następujące kroki:
1. Skonfiguruj środowisko programistyczne za pomocą biblioteki Aspose.Words.
2. Dodaj niezbędne zespoły do swojego projektu, odwołując się do Aspose.Words.
3.  Zainicjuj dokumenty, które chcesz porównać za pomocą`Document` klasa lub`DocumentBuilder` klasa.
4.  Skonfiguruj opcje porównania, tworząc plik`CompareOptions` obiektu i ustawiania właściwości, takich jak`IgnoreFormatting` I`Target` (np.,`ComparisonTargetType.New` dla celu porównania).
5.  Użyj`Compare` metodę na jednym dokumencie, przekazując drugi dokument i`CompareOptions` obiekt jako parametry. Ta metoda porówna dokumenty i zapisze zmiany w pierwszym dokumencie.

####  P: Jaki jest cel`Target` property in the `CompareOptions` class?

 O:`Target` nieruchomość w`CompareOptions` class umożliwia określenie celu porównania, co działa podobnie do opcji „Pokaż zmiany w” w oknie dialogowym „Porównaj dokumenty” programu Microsoft Word. Cel można ustawić`ComparisonTargetType.New` aby pokazać zmiany w nowym dokumencie,`ComparisonTargetType.Current` aby pokazać zmiany w bieżącym dokumencie, lub`ComparisonTargetType.Formatting` aby pokazać tylko zmiany formatowania.