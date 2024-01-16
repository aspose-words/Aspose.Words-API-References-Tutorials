---
title: Utwórz zakładkę w dokumencie programu Word
linktitle: Utwórz zakładkę w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak tworzyć zakładki w dokumencie programu Word i określać poziomy podglądu zakładek w pliku PDF przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-bookmarks/create-bookmark/
---

W tym artykule zbadamy powyższy kod źródłowy C#, aby zrozumieć, jak korzystać z funkcji Utwórz zakładkę w bibliotece Aspose.Words dla .NET. Ta funkcja umożliwia tworzenie zakładek w dokumencie i określanie poziomów podglądu zakładek w wyjściowym pliku PDF.

## Warunki wstępne

- Podstawowa znajomość języka C#.
- Środowisko programistyczne .NET z zainstalowaną biblioteką Aspose.Words.

## Krok 1: Tworzenie dokumentu i generatora

 Przed utworzeniem zakładek musimy utworzyć dokument i kreator dokumentów za pomocą`Document` I`DocumentBuilder` obiekty:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Tworzenie głównej zakładki

 Używamy`StartBookmark` metoda uruchamiania głównej zakładki i`EndBookmark` sposób, aby to zakończyć. W międzyczasie możemy dodać tekst i inne zakładki:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Dodaj tutaj więcej zakładek lub tekstu.

builder. EndBookmark("My Bookmark");
```

## Krok 3: Tworzenie zagnieżdżonych zakładek

Możemy także tworzyć zagnieżdżone zakładki wewnątrz głównej zakładki. Używamy tego samego`StartBookmark` I`EndBookmark` metody tworzenia i kończenia zagnieżdżonych zakładek:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Krok 4: Określanie poziomów podglądu zakładek w wyjściowym pliku PDF

 Używamy`PdfSaveOptions` obiekt, aby określić poziomy podglądu zakładek w wyjściowym pliku PDF. Używamy`BookmarksOutlineLevels` nieruchomość

  aby dodać zakładki główne i zagnieżdżone wraz z odpowiadającymi im poziomami:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Przykładowy kod źródłowy narzędzia Utwórz zakładkę przy użyciu Aspose.Words dla platformy .NET

Oto pełny przykładowy kod źródłowy demonstrujący tworzenie zakładek przy użyciu Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Wniosek

W tym artykule zbadaliśmy kod źródłowy C#, aby zrozumieć, jak korzystać z funkcji Utwórz zakładkę w Aspose.Words dla .NET. Postępowaliśmy zgodnie z przewodnikiem krok po kroku dotyczącym tworzenia zakładek w dokumencie i określania poziomów podglądu zakładek w wyjściowym pliku PDF.

### Często zadawane pytania

#### P: Jakie są wymagania wstępne, aby móc korzystać z funkcji „Utwórz zakładki” w Aspose.Words dla .NET?

Odp.: Aby skorzystać z funkcji „Utwórz zakładki” w Aspose.Words dla .NET, musisz posiadać podstawową wiedzę o języku C#. Potrzebujesz także środowiska programistycznego .NET z zainstalowaną biblioteką Aspose.Words.

#### P: Jak utworzyć dokument w Aspose.Words dla .NET?

 Odp.: Aby utworzyć dokument w Aspose.Words dla .NET, możesz użyć`Document` klasa. Oto przykładowy kod:

```csharp
Document doc = new Document();
```

#### P: Jak utworzyć główną zakładkę w dokumencie przy użyciu Aspose.Words dla .NET?

 Odp.: Aby utworzyć główną zakładkę w dokumencie przy użyciu Aspose.Words dla .NET, możesz użyć`StartBookmark` aby rozpocząć tworzenie zakładki, dodać do niej tekst lub inne zakładki, a następnie użyć metody` EndBookmark` aby to zakończyć. Oto przykładowy kod:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### P: Jak utworzyć zagnieżdżoną zakładkę wewnątrz głównej zakładki przy użyciu Aspose.Words dla .NET?

 Odp.: Aby utworzyć zagnieżdżoną zakładkę wewnątrz głównej zakładki przy użyciu Aspose.Words dla .NET, możesz użyć tego samego`StartBookmark` I`EndBookmark` metody rozpoczynania i kończenia zagnieżdżonej zakładki. Oto przykładowy kod:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### P: Jak określić poziomy podglądu zakładek w wyjściowym pliku PDF przy użyciu Aspose.Words dla .NET?

 O: Aby określić poziomy podglądu zakładek w wyjściowym pliku PDF za pomocą Aspose.Words dla .NET, możesz użyć`PdfSaveOptions` klasa i`BookmarksOutlineLevels` nieruchomość. Możesz dodawać zakładki główne i zagnieżdżone wraz z odpowiadającymi im poziomami. Oto przykładowy kod:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### P: Jak zapisać dokument po utworzeniu zakładek przy użyciu Aspose.Words dla .NET?

 Odp.: Aby zapisać dokument po utworzeniu zakładek przy użyciu Aspose.Words dla .NET, możesz użyć`Save` metoda`Document` obiekt określający ścieżkę pliku docelowego. Oto przykładowy kod:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### P: Jak określić poziomy podglądu zakładek w wyjściowym pliku PDF przy użyciu Aspose.Words dla .NET?

 O: Aby określić poziomy podglądu zakładek w wyjściowym pliku PDF za pomocą Aspose.Words dla .NET, możesz użyć`PdfSaveOptions` klasa i`BookmarksOutlineLevels` nieruchomość. Możesz dodawać zakładki główne i zagnieżdżone wraz z odpowiadającymi im poziomami. Oto przykładowy kod:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### P: Jak utworzyć zagnieżdżone zakładki wewnątrz głównej zakładki przy użyciu Aspose.Words dla .NET?

 Odp.: Aby utworzyć zagnieżdżone zakładki wewnątrz głównej zakładki przy użyciu Aspose.Words dla .NET, możesz użyć tego samego`StartBookmark` I`EndBookmark` metody rozpoczynania i kończenia zagnieżdżonych zakładek. Podczas wywoływania metody pamiętaj o określeniu zakładki nadrzędnej jako parametru`StartBookmark` metoda. Oto przykładowy kod:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### P: Jak dodać tekst do zakładki przy użyciu Aspose.Words dla .NET?

 Odp.: Aby dodać tekst do zakładki przy użyciu Aspose.Words dla .NET, możesz użyć metody`Write` metoda`DocumentBuilder`obiekt określający tekst do dodania. Oto przykładowy kod:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### P: Jak utworzyć główną zakładkę w dokumencie przy użyciu Aspose.Words dla .NET?

 Odp.: Aby utworzyć główną zakładkę w dokumencie przy użyciu Aspose.Words dla .NET, możesz użyć`StartBookmark` metoda uruchamiania zakładki i`EndBookmark` sposób, aby to zakończyć. Oto przykładowy kod:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```