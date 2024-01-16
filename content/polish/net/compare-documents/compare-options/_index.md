---
title: Porównaj opcje w dokumencie programu Word
linktitle: Porównaj opcje w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku wyjaśniający kod źródłowy C# opcji porównywania w funkcji dokumentu tekstowego w Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/compare-documents/compare-options/
---
W tym samouczku wyjaśnimy, jak używać opcji porównywania w dokumencie programu Word w Aspose.Words dla .NET. Wykonaj poniższe kroki, aby zrozumieć kod źródłowy i zastosować zmiany.

## Krok 1: Porównaj dokumenty z opcjami niestandardowymi

 Aby rozpocząć, załaduj dwa dokumenty do porównania. W tym przykładzie użyjemy`Clone()` metoda tworzenia kopii oryginalnego dokumentu. Oto jak:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Krok 2: Konfiguracja opcji porównania

 Teraz skonfigurujemy opcje porównywania, tworząc plik`CompareOptions` obiekt i w razie potrzeby ustawiając różne właściwości. Oto jak:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Krok 3: Porównaj dokumenty z opcjami niestandardowymi

 Będziemy teraz korzystać z`Compare()` metoda przekazująca niestandardowe opcje w celu porównania dwóch dokumentów. Ta metoda zaznaczy zmiany w oryginalnym dokumencie. Oto jak:

```csharp
// Porównaj dokumenty z opcjami niestandardowymi
docA.Compare(docB, "user", DateTime.Now, options);

// Sprawdź, czy dokumenty są równe
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Przykładowy kod źródłowy opcji porównania przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy funkcji Porównaj opcje w Aspose.Words dla .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Za pomocą tego kodu możesz porównać dwa dokumenty przy użyciu niestandardowych opcji, aby zignorować określone elementy podczas porównywania z Aspose.Words dla .NET.

## Wniosek

tym samouczku nauczyliśmy się, jak używać opcji porównania w Aspose.Words dla .NET, aby dostosować proces porównywania podczas porównywania dwóch dokumentów. Określając różne opcje, możesz zignorować określone elementy i uelastycznić proces porównywania. Funkcja ta pozwala mieć większą kontrolę nad procesem porównywania, dostosowując go do konkretnych wymagań. Aspose.Words dla .NET zapewnia potężne możliwości porównywania dokumentów, ułatwiając identyfikację różnic między dokumentami, ignorując określone elementy w razie potrzeby.

### Często zadawane pytania

#### P: Jaki jest cel używania opcji porównania w Aspose.Words dla .NET?

Odp.: Opcje porównania w Aspose.Words dla .NET pozwalają dostosować proces porównywania podczas porównywania dwóch dokumentów. Dzięki tym opcjom możesz określić, które elementy mają być ignorowane podczas porównania, np. zmiany formatowania, nagłówki i stopki, tabele, pola, komentarze, pola tekstowe i przypisy.

#### P: Jak korzystać z opcji porównania w Aspose.Words dla .NET?

Odp.: Aby skorzystać z opcji porównania w Aspose.Words dla .NET, wykonaj następujące kroki:
1. Załaduj dwa dokumenty, które chcesz porównać, do oddzielnych obiektów Dokument.
2.  Użyj`Clone()` metoda tworzenia kopii oryginalnego dokumentu.
3.  Stwórz`CompareOptions` obiekt i ustaw jego właściwości, aby dostosować proces porównania. Możesz określić, które elementy mają być ignorowane podczas porównania.
4.  Użyj`Compare()` metodę na jednym z dokumentów i przekazać drugi dokument i`CompareOptions` obiekt jako parametry. Ta metoda porówna dokumenty na podstawie określonych opcji i zaznaczy zmiany w oryginalnym dokumencie.
5.  Sprawdź`Revisions` własność oryginalnego dokumentu. Jeśli liczba wynosi zero, oznacza to, że dokumenty są identyczne, biorąc pod uwagę określone opcje.

#### P: Jakie są typowe opcje dostępne w CompareOptions?

Odp.: Typowe opcje dostępne w CompareOptions obejmują:
- `IgnoreFormatting`: Ignoruje zmiany w formatowaniu.
- `IgnoreHeadersAndFooters`: Ignoruje zmiany w nagłówkach i stopkach.
- `IgnoreCaseChanges`: Ignoruje zmiany wielkości liter (wielkie/małe litery).
- `IgnoreTables`: Ignoruje zmiany w tabelach.
- `IgnoreFields`: Ignoruje zmiany w polach.
- `IgnoreComments`: Ignoruje zmiany w komentarzach.
- `IgnoreTextboxes`Ignoruje zmiany w polach tekstowych.
- `IgnoreFootnotes`: Ignoruje zmiany w przypisach.

#### P: Czy podczas porównywania dokumentów mogę używać niestandardowych opcji dla określonych elementów?

 Odp.: Tak, podczas porównywania dokumentów możesz używać niestandardowych opcji dla określonych elementów. Ustawiając właściwości pliku`CompareOptions` odpowiednio możesz wybrać, które elementy należy zignorować, a które wziąć pod uwagę podczas porównania.