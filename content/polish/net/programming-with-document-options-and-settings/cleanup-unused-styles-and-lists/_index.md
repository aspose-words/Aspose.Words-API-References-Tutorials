---
title: Oczyść nieużywane style i listy
linktitle: Oczyść nieużywane style i listy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący czyszczenia nieużywanych stylów i list w dokumencie za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby wyczyścić nieużywane style i listy za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia usuwanie stylów i list, które nie są używane w dokumencie.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument programu Word zawierający nieużywane style i listy, które chcemy wyczyścić. Aby załadować dokument, użyj poniższego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu, w którym znajduje się dokument.

## Krok 3: Policz style i listy przed czyszczeniem

Przed czyszczeniem policzymy liczbę stylów i list występujących w dokumencie. Użyj poniższego kodu, aby wyświetlić liczniki:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Instrukcje te pokazują liczbę stylów i list znajdujących się w dokumencie przed czyszczeniem.

## Krok 4: Oczyść nieużywane style i listy

Teraz wyczyśćmy z dokumentu nieużywane style i listy. Użyj poniższego kodu, aby przeprowadzić czyszczenie:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Ten kod czyści nieużywane style i listy z dokumentu przy użyciu określonych opcji. W tym przykładzie włączyliśmy`UnusedStyles` opcję usunięcia nieużywanych stylów i wyłączyłam`UnusedLists` możliwość zachowania list, nawet jeśli nie są używane.

## Krok 5: Policz style i listy po czyszczeniu

Po oczyszczeniu ponownie policzymy style i listy, aby sprawdzić, czy nie zostały zwinięte. Użyj poniższego kodu, aby wyświetlić nowe liczniki:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Niniejsza instrukcja przedstawia liczbę stylów i list pozostałych po czyszczeniu.

### Przykładowy kod źródłowy do czyszczenia nieużywanych stylów i list przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// W połączeniu z wbudowanymi stylami dokument ma teraz osiem stylów.
	// Styl niestandardowy jest oznaczany jako „używany”, jeśli w dokumencie znajduje się jakikolwiek tekst
	// sformatowany w tym stylu. Oznacza to, że 4 dodane przez nas style są obecnie nieużywane.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	// Czyści nieużywane style i listy z dokumentu w zależności od podanych opcji czyszczenia.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Pamiętaj, aby określić poprawną ścieżkę dokumentu w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak wyczyścić nieużywane style i listy z dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz z łatwością zastosować tę funkcję do własnych dokumentów.

