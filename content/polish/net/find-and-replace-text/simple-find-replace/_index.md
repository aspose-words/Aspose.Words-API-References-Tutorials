---
title: Prosty tekst Znajdź i zamień w programie Word
linktitle: Prosty tekst Znajdź i zamień w programie Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wykonać proste wyszukiwanie i zamianę tekstu w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/find-and-replace-text/simple-find-replace/
---
W tym artykule omówimy powyższy kod źródłowy C#, aby zrozumieć, jak używać funkcji Znajdź i zamień prosty tekst w programie Word w bibliotece Aspose.Words dla .NET. Ta funkcja umożliwia proste zastępowanie tekstu poprzez wyszukiwanie określonego ciągu znaków i zastąpienie go innym ciągiem znaków w dokumencie programu Word.

## Warunki wstępne

- Podstawowa znajomość języka C#.
- Środowisko programistyczne .NET z zainstalowaną biblioteką Aspose.Words.

## Krok 1: Tworzenie nowego dokumentu

 Zanim zaczniemy używać prostego znajdowania i zamieniania, musimy utworzyć nowy dokument za pomocą Aspose.Words dla .NET. Można to zrobić poprzez utworzenie instancji a`Document` obiekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Krok 2: Wstaw tekst do dokumentu

 Kiedy już mamy dokument, możemy wstawić tekst za pomocą a`DocumentBuilder` obiekt. W naszym przykładzie używamy`Writeln` metodę wstawienia frazy „Hello_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Krok 3: Prosta zamiana tekstu

 Używamy`Range.Replace` metoda wykonywania prostej zamiany tekstu. W naszym przykładzie zastępujemy wszystkie wystąpienia ciągu „_ClientName_ " z "Jamesem Bondem" przy użyciu`FindReplaceOptions` opcja z`FindReplaceDirection.Forward` kierunek wyszukiwania:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Krok 4: Zapisanie edytowanego dokumentu

Na koniec zapisujemy zmodyfikowany dokument w określonym katalogu za pomocą pliku`Save` metoda:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Przykładowy kod źródłowy narzędzia Simple Find Zamień przy użyciu Aspose.Words dla .NET

Oto pełny przykładowy kod źródłowy demonstrujący użycie prostego wyszukiwania i zamiany na Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Zapisz zmodyfikowany dokument
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Wniosek

W tym artykule zbadaliśmy kod źródłowy C#, aby zrozumieć, jak korzystać z funkcji Simple Find Zamień w Aspose.Words dla .NET. Postępowaliśmy zgodnie z przewodnikiem krok po kroku, aby utworzyć dokument, wstawić tekst, wykonać prostą zamianę tekstu i zapisać edytowany dokument.

### Często zadawane pytania

#### P: Jaka jest funkcja Znajdź i zamień prosty tekst w Aspose.Words dla .NET?

Odp.: Funkcja Znajdź i zamień prosty tekst w Aspose.Words dla .NET umożliwia wykonanie prostej zamiany tekstu w dokumencie programu Word. Umożliwia wyszukanie określonego ciągu znaków i zastąpienie go innym ciągiem znaków. Może to być przydatne, gdy chcesz wprowadzić globalne zmiany w dokumencie, takie jak zastąpienie nazw, dat lub innych informacji.

#### P: Jak utworzyć nowy dokument w Aspose.Words dla .NET?

 Odp.: Przed użyciem funkcji Znajdź i zamień prosty tekst musisz utworzyć nowy dokument za pomocą Aspose.Words dla .NET. Można to zrobić poprzez utworzenie instancji a`Document` obiekt. Oto przykładowy kod umożliwiający utworzenie nowego dokumentu:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### P: Jak wstawić tekst do dokumentu za pomocą Aspose.Words dla .NET?

 Odp.: Gdy już masz dokument, możesz wstawić tekst za pomocą a`DocumentBuilder` obiekt. W naszym przykładzie używamy`Writeln` metodę wstawienia frazy „Hello_CustomerName_:":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### P: Jak wykonać prostą zamianę tekstu w dokumencie przy użyciu Aspose.Words dla .NET?

 Odp.: Aby wykonać prostą zamianę tekstu, możesz użyć metody`Range.Replace` metoda. W naszym przykładzie zastępujemy wszystkie wystąpienia ciągu „_ClientName_ " z "Jamesem Bondem" przy użyciu`FindReplaceOptions` opcja z`FindReplaceDirection.Forward` kierunek wyszukiwania:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### P: Jak zapisać edytowany dokument w Aspose.Words dla .NET?

 Odp.: Po dokonaniu zamiany tekstu możesz zapisać zmodyfikowany dokument w określonym katalogu za pomocą`Save` metoda:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```