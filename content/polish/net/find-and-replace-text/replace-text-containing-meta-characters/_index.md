---
title: Słowo Zamień tekst zawierający znaki meta
linktitle: Słowo Zamień tekst zawierający znaki meta
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zastąpić tekst zawierający metaznaki w dokumentach programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/find-and-replace-text/replace-text-containing-meta-characters/
---
W tym artykule zbadamy powyższy kod źródłowy C#, aby zrozumieć, jak używać funkcji Word Zamień tekst zawierający metaznaki w bibliotece Aspose.Words dla .NET. Ta funkcja umożliwia zamianę fragmentów tekstu w dokumencie zawierających określone metaznaki.

## Warunki wstępne

- Podstawowa znajomość języka C#.
- Środowisko programistyczne .NET z zainstalowaną biblioteką Aspose.Words.

## Krok 1: Tworzenie nowego dokumentu

 Zanim zaczniemy używać zamiany tekstu metaznakowego, musimy utworzyć nowy dokument za pomocą Aspose.Words dla .NET. Można to zrobić poprzez utworzenie instancji a`Document` obiekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Krok 2: Wstaw tekst do dokumentu

 Kiedy już mamy dokument, możemy wstawić tekst za pomocą a`DocumentBuilder` obiekt. W naszym przykładzie używamy`Writeln` metoda wstawiania wielu akapitów tekstu w różnych sekcjach:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder. Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

## Krok 3: Konfigurowanie opcji Znajdź i zamień

 Teraz skonfigurujemy opcje wyszukiwania i zamiany za pomocą pliku`FindReplaceOptions` obiekt. W naszym przykładzie ustawiliśmy wyrównanie zastępowanych akapitów na „Wyśrodkowane”:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## Krok 4: Zastępowanie tekstu zawierającego metaznaki

 Używamy`Range.Replace`metoda zamiany tekstu zawierającego metaznaki. W naszym przykładzie każde wystąpienie słowa „sekcja”, po którym następuje podział akapitu, zastępujemy tym samym słowem, po którym następuje kilka myślników i nowy podział akapitu:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## Krok 5: Zastąpienie niestandardowego tagu tekstowego

 Używamy również`Range.Replace` metoda zastąpienia niestandardowego „{insert-section}" znacznik tekstowy z podziałem sekcji. W naszym przykładzie zastępujemy "{insert-section}" z "&b", aby wstawić podział sekcji:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## Krok 6: Zapisanie edytowanego dokumentu

Na koniec zapisujemy zmodyfikowany dokument w określonym katalogu za pomocą pliku`Save` metoda:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### Przykładowy kod źródłowy funkcji Zamień tekst zawierający znaki meta przy użyciu Aspose.Words dla .NET

Oto pełny przykładowy kod źródłowy demonstrujący użycie zamiany tekstu zawierającego metaznaki za pomocą Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Font.Name = "Arial";
	builder.Writeln("First section");
	builder.Writeln("  1st paragraph");
	builder.Writeln("  2nd paragraph");
	builder.Writeln("{insert-section}");
	builder.Writeln("Second section");
	builder.Writeln("  1st paragraph");

	FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
	findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;

	// Podwój każdy podział akapitu po słowie „sekcja”, dodaj rodzaj podkreślenia i wyśrodkuj.
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// Wstaw podział sekcji zamiast niestandardowego znacznika tekstowego.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## Wniosek

tym artykule zbadaliśmy kod źródłowy C#, aby zrozumieć, jak korzystać z funkcji Zamień tekst zawierający metaznaki w Aspose.Words dla .NET. Postępowaliśmy zgodnie z przewodnikiem krok po kroku, aby utworzyć dokument, wstawić tekst, zastąpić tekst zawierający metaznaki i zapisać zmodyfikowany dokument.

### Często zadawane pytania

#### P: Jaka jest funkcja Zamień tekst zawierający metaznaki w Aspose.Words dla .NET?

O: Funkcja Zamień tekst zawierający metaznaki w Aspose.Words dla .NET umożliwia zamianę fragmentów tekstu w dokumencie zawierającym określone metaznaki. Możesz użyć tej funkcji, aby dokonać zaawansowanych zamian w dokumencie, biorąc pod uwagę metaznaki.

#### P: Jak utworzyć nowy dokument w Aspose.Words dla .NET?

 Odp.: Przed użyciem funkcji Zamień tekst zawierający metaznaki musisz utworzyć nowy dokument przy użyciu Aspose.Words dla .NET. Można to zrobić poprzez utworzenie instancji a`Document` obiekt. Oto przykładowy kod umożliwiający utworzenie nowego dokumentu:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### P: Jak wstawić tekst do dokumentu za pomocą Aspose.Words dla .NET?

 Odp.: Gdy już masz dokument, możesz wstawić tekst za pomocą a`DocumentBuilder` obiekt. W naszym przykładzie używamy`Writeln` metoda wstawiania wielu akapitów tekstu w różnych sekcjach:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder.Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

#### P: Jak skonfigurować opcje wyszukiwania i zamiany w Aspose.Words dla .NET?

 Odp.: Teraz skonfigurujemy opcje wyszukiwania i zamiany za pomocą pliku a`FindReplaceOptions` obiekt. W naszym przykładzie ustawiliśmy wyrównanie zastępowanych akapitów na „Wyśrodkowane”:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### P: Jak zamienić tekst zawierający metaznaki w dokumencie przy użyciu Aspose.Words dla .NET?

 Odp.: Używamy`Range.Replace` metoda zastępowania tekstu zawierającego metaznaki. W naszym przykładzie każde wystąpienie słowa „sekcja”, po którym następuje podział akapitu, zastępujemy tym samym słowem, po którym następuje kilka myślników i nowy podział akapitu:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### P: Jak zamienić niestandardowy znacznik tekstowy zawierający znaki meta w dokumencie przy użyciu Aspose.Words dla .NET?

 Odp.: Używamy również`Range.Replace` metoda zastąpienia niestandardowego „{insert-section}" znacznik tekstowy z podziałem sekcji. W naszym przykładzie zastępujemy "{insert-section}" z "&b", aby wstawić podział sekcji:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### P: Jak zapisać edytowany dokument w Aspose.Words dla .NET?

 Odp.: Po wprowadzeniu zmian w dokumencie możesz zapisać go w określonym katalogu za pomocą`Save` metoda:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```