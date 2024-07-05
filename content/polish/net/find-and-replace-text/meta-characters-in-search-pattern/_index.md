---
title: Meta znaki we wzorcu wyszukiwania
linktitle: Meta znaki we wzorcu wyszukiwania
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak używać metaznaków we wzorcu wyszukiwania za pomocą Aspose.Words dla .NET do manipulowania dokumentami programu Word.
type: docs
weight: 10
url: /pl/net/find-and-replace-text/meta-characters-in-search-pattern/
---
W tym artykule przeanalizujemy powyższy kod źródłowy C#, aby zrozumieć, jak używać funkcji Metaznaki we wzorcu wyszukiwania w bibliotece Aspose.Words dla .NET. Ta funkcja umożliwia używanie specjalnych metaznaków do wykonywania zaawansowanych wyszukiwań i zamian w dokumentach programu Word.

## Warunki wstępne

- Podstawowa znajomość języka C#.
- Środowisko programistyczne .NET z zainstalowaną biblioteką Aspose.Words.

## Krok 1: Tworzenie nowego dokumentu

 Zanim zaczniemy używać metaznaków we wzorcu wyszukiwania, musimy utworzyć nowy dokument za pomocą Aspose.Words dla .NET. Można to zrobić poprzez utworzenie instancji a`Document` obiekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Krok 2: Wstaw tekst do dokumentu

 Kiedy już mamy dokument, możemy wstawić tekst za pomocą a`DocumentBuilder` obiekt. W naszym przykładzie używamy`Writeln` I`Write` metody wstawiania dwóch linii tekstu:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## Krok 3: Znajdź i zamień tekst na metaznaki

 Teraz skorzystamy z`Range.Replace` funkcja wyszukiwania i zamiany tekstu przy użyciu wzorca wyszukiwania zawierającego specjalne metaznaki. W naszym przykładzie zastępujemy frazę „To jest linia 1 i pTo jest linia 2” na „Ta linia jest zastępowana” za pomocą`&p` metaznak reprezentujący podział akapitu:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Krok 4: Wstawienie podziału strony w dokumencie

 Aby zilustrować użycie innego metaznaku, wstawimy podział strony do dokumentu za pomocą`InsertBreak` metoda z`BreakType.PageBreak` parametr. Najpierw przesuwamy kursor z`DocumentBuilder` na koniec dokumentu, następnie wstawiamy podział strony i nową linijkę tekstu:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## Krok 5: Znajdź i zamień na inny metaznak

 Teraz przeprowadzimy kolejne wyszukiwanie i zamienimy za pomocą`&m` metaznak reprezentujący podział strony. Zastępujemy wyrażenie „To jest wiersz 1 i m. To jest wiersz 2” na „Podział strony zostaje zastąpiony nowym tekstem”. :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Krok 6: Zapisanie edytowanego dokumentu

Na koniec zapisujemy zmodyfikowany dokument w określonym katalogu za pomocą pliku`Save` metoda:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Przykładowy kod źródłowy metaznaków we wzorcu wyszukiwania przy użyciu Aspose.Words dla .NET

Oto pełny przykładowy kod źródłowy demonstrujący użycie metaznaków we wzorcu wyszukiwania w Aspose.Words dla .NET:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Wniosek

W tym artykule zbadaliśmy kod źródłowy C#, aby zrozumieć, jak używać metaznaków we wzorcu wyszukiwania Aspose.Words dla .NET. Postępowaliśmy zgodnie z przewodnikiem krok po kroku, aby utworzyć dokument, wstawić tekst, przeprowadzić wyszukiwanie i zamianę przy użyciu specjalnych metaznaków, wstawić podziały stron i zapisać edytowany dokument.

### Często zadawane pytania

#### P: Czym jest funkcja Meta Znaki we wzorcu wyszukiwania w Aspose.Words dla .NET?

Odp.: Funkcja Metaznaki we wzorcu wyszukiwania w Aspose.Words dla .NET umożliwia używanie specjalnych metaznaków do wykonywania zaawansowanych wyszukiwań i zamian w dokumentach programu Word. Te metaznaki umożliwiają reprezentowanie podziałów akapitów, podziałów sekcji, podziałów stron i innych specjalnych elementów we wzorcu wyszukiwania.

#### P: Jak utworzyć nowy dokument w Aspose.Words dla .NET?

 Odp.: Przed użyciem metaznaków w szablonie wyszukiwania musisz utworzyć nowy dokument za pomocą Aspose.Words dla .NET. Można to zrobić poprzez utworzenie instancji a`Document` obiekt. Oto przykładowy kod umożliwiający utworzenie nowego dokumentu:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### P: Jak wstawić tekst do dokumentu za pomocą Aspose.Words dla .NET?

 Odp.: Gdy już masz dokument, możesz wstawić tekst za pomocą a`DocumentBuilder` obiekt. W naszym przykładzie używamy`Writeln` I`Write` metody wstawiania dwóch linii tekstu:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### P: Jak wyszukiwać i zastępować tekst metaznakami w dokumencie przy użyciu Aspose.Words dla .NET?

 Odp.: Aby wyszukiwać i zamieniać tekst na metaznaki, możesz użyć metody`Range.Replace` metoda. W naszym przykładzie zastępujemy frazę „To jest linia 1 i pTo jest linia 2” na „Ta linia jest zastępowana” za pomocą`&p` metaznak reprezentujący podział akapitu:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### P: Jak wstawić podział strony w dokumencie przy użyciu Aspose.Words dla .NET?

O: Aby zilustrować użycie innego metaznaku, wstawimy podział strony do dokumentu za pomocą`InsertBreak` metoda z`BreakType.PageBreak` parametr. Najpierw przesuwamy kursor z`DocumentBuilder` na koniec dokumentu, następnie wstawiamy podział strony i nową linijkę tekstu:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### P: Jak wyszukiwać i zastępować inny metaznak w dokumencie przy użyciu Aspose.Words dla .NET?

 O: Teraz przeprowadzimy kolejne wyszukiwanie i zamianę przy użyciu metody`&m` metaznak reprezentujący podział strony. Zastępujemy wyrażenie „To jest wiersz 1 i m. To jest wiersz 2” na „Podział strony zostaje zastąpiony nowym tekstem”. :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### P: Jak zapisać edytowany dokument w Aspose.Words dla .NET?

 Odp.: Po wprowadzeniu zmian w dokumencie możesz zapisać go w określonym katalogu za pomocą`Save` metoda:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```