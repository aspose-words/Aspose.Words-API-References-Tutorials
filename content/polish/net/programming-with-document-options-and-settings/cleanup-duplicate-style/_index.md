---
title: Oczyść zduplikowany styl
linktitle: Oczyść zduplikowany styl
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący czyszczenia zduplikowanych stylów w dokumencie przy użyciu Aspose.Words dla .NET. Zawiera pełny kod źródłowy.
type: docs
weight: 10
url: /pl/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

W tym samouczku przeprowadzimy Cię krok po kroku przez kod źródłowy C#, aby oczyścić zduplikowane style za pomocą Aspose.Words dla .NET. Ta funkcja pomaga usunąć zduplikowane style z dokumentu.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

tym kroku załadujemy dokument programu Word, który chcemy wyczyścić. Aby załadować dokument, użyj poniższego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu, w którym znajduje się dokument.

## Krok 3: Policz style przed czyszczeniem

Przed przystąpieniem do czyszczenia policzymy liczbę stylów znajdujących się w dokumencie. Użyj poniższego kodu, aby wyświetlić liczbę stylów:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Ta instrukcja wyświetla liczbę stylów obecnych w dokumencie.

## Krok 4: Oczyść zduplikowane style

Teraz usuńmy z dokumentu zduplikowane style. Użyj poniższego kodu, aby przeprowadzić czyszczenie:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Ten kod czyści zduplikowane style z dokumentu przy użyciu określonych opcji. W tym przykładzie włączyliśmy`DuplicateStyle` opcja czyszczenia zduplikowanych stylów.

## Krok 5: Policz style po czyszczeniu

Po czyszczeniu ponownie policzymy liczbę stylów, aby sprawdzić, czy się zmniejszyła. Użyj poniższego kodu, aby wyświetlić liczbę nowych stylów:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

To zestawienie wyświetla liczbę stylów pozostałych po czyszczeniu.

### Przykładowy kod źródłowy dla stylu Cleanup Duplicate przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Liczba stylów przed czyszczeniem.
	Console.WriteLine(doc.Styles.Count);

	// Usuwa z dokumentu zduplikowane style.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	// Zmniejszono liczbę stylów po czyszczeniu.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```