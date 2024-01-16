---
title: Ignoruj tekst wewnątrz Usuń poprawki
linktitle: Ignoruj tekst wewnątrz Usuń poprawki
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak korzystać z funkcji „Ignoruj tekst wewnątrz Usuń wersje” w Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

tym artykule omówimy powyższy kod źródłowy C#, aby zrozumieć, jak korzystać z funkcji „Ignoruj tekst w środku Usuń wersje” w bibliotece Aspose.Words dla .NET. Ta funkcja jest przydatna, gdy chcemy zignorować tekst znajdujący się w wersjach usuniętych podczas przetwarzania tekstu w dokumentach.

## Przegląd biblioteki Aspose.Words dla .NET

Zanim zagłębię się w szczegóły kodu, pozwólcie, że pokrótce przedstawię bibliotekę Aspose.Words dla .NET. Jest to potężna biblioteka, która umożliwia tworzenie, modyfikowanie i konwertowanie dokumentów Word w aplikacjach .NET. Oferuje wiele zaawansowanych funkcji do przetwarzania tekstu w dokumentach, w tym zarządzanie wersjami.

## Zrozumienie funkcji „Ignoruj tekst w środku Usuń wersje”.

Funkcja „Ignoruj tekst wewnątrz usuwania wersji” w Aspose.Words dla .NET pozwala określić, czy tekst wewnątrz usuwania wersji powinien być ignorowany podczas niektórych operacji, takich jak wyszukiwanie i zastępowanie tekstu. Gdy ta funkcja jest włączona, usunięty tekst wewnątrz wersji nie jest uwzględniany podczas operacji.

## Krok 1: Tworzenie nowego dokumentu przy użyciu Aspose.Words dla .NET

 Zanim zaczniemy manipulować tekstem w dokumencie, musimy utworzyć nowy dokument za pomocą Aspose.Words dla .NET. Można to zrobić poprzez utworzenie instancji a`Document` obiekt:

```csharp
Document doc = new Document();
```

## Krok 2: Wstawienie do dokumentu niezmienionego tekstu

 Kiedy już mamy dokument, możemy wstawić niesprawdzony tekst za pomocą a`DocumentBuilder` obiekt. Na przykład, aby wstawić tekst „Usunięty tekst”, możemy użyć`Writeln` I`Write` metody:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Krok 3: Usuwanie akapitu ze śledzeniem poprawek

Aby zilustrować użycie funkcji „Ignoruj tekst w środku, usuń wersje”, usuniemy akapit z dokumentu za pomocą śledzenia wersji. Dzięki temu będziemy mogli zobaczyć jak ta funkcja wpływa na późniejsze operacje.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Krok 4: Zastosowanie funkcji „Ignoruj tekst w środku, usuń wersje”.

 Teraz, gdy przygotowaliśmy dokument poprzez usunięcie akapitu, możemy włączyć funkcję „Ignoruj tekst w środku, usuń wersje” za pomocą`FindReplaceOptions` obiekt. Ustalimy`IgnoreDeleted`własność do`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Krok 5: Używanie wyrażeń regularnych do wyszukiwania i zamiany

Aby wykonać operacje wyszukiwania i zamiany na tekście dokumentu, użyjemy wyrażeń regularnych. W naszym przykładzie wyszukamy wszystkie wystąpienia litery „e” i zastąpimy je gwiazdką „* ". .INTERNET`Regex` klasa służy do tego:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Krok 6: Wyświetlanie zmodyfikowanego wyniku dokumentu

 Po zastosowaniu wyszukiwania i zamiany możemy wyświetlić zmienioną treść dokumentu za pomocą`GetText` metoda:

```csharp
Console.WriteLine(doc.GetText());
```

## Krok 7: Modyfikowanie opcji w celu uwzględnienia usuniętego tekstu

 Jeśli chcemy uwzględnić usunięty tekst w wyniku wyjściowym, możemy zmienić opcje, aby nie ignorować usuniętego tekstu. W tym celu ustawimy`IgnoreDeleted`własność do`false`:

```csharp
options. IgnoreDeleted = false;
```

## Krok 8: Wyprowadzenie zmodyfikowanego dokumentu z usuniętym tekstem

Po zmianie opcji możemy ponownie przeprowadzić wyszukiwanie i zamianę, aby uzyskać wynik z uwzględnieniem usuniętego tekstu:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Przykładowy kod źródłowy opcji Ignoruj tekst w środku Usuń wersje przy użyciu Aspose.Words dla .NET

Oto pełny przykładowy kod źródłowy demonstrujący użycie funkcji „Ignoruj tekst w środku Usuń wersje” w Aspose.Words dla .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Wstaw nie poprawiony tekst.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Usuń pierwszy akapit ze śledzeniem poprawek.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Wniosek

tym artykule zbadaliśmy kod źródłowy C#, aby zrozumieć, jak korzystać z funkcji „Ignoruj tekst w środku Usuń wersje” w Aspose.Words dla .NET. Ta funkcja jest przydatna do ignorowania tekstu zawartego w wersjach usuniętych podczas manipulowania dokumentami. Postępowaliśmy zgodnie z przewodnikiem krok po kroku, aby utworzyć dokument, wstawić tekst, usunąć akapit ze śledzeniem wersji, zastosować funkcję „Ignoruj tekst w środku, Usuń wersje” oraz wykonać operacje wyszukiwania i zamiany.

### Często zadawane pytania

#### P: Do czego służy funkcja „Ignoruj tekst wewnątrz Usuń wersje” w Aspose.Words dla .NET?

Odp.: Funkcja „Ignoruj tekst wewnątrz usuwania wersji” w Aspose.Words dla .NET pozwala określić, czy tekst wewnątrz usuwania wersji powinien być ignorowany podczas niektórych operacji, takich jak wyszukiwanie i zastępowanie tekstu. Gdy ta funkcja jest włączona, usunięty tekst wewnątrz wersji nie jest uwzględniany podczas operacji.

#### P: Co to jest Aspose.Words dla .NET?

O: Aspose.Words dla .NET to potężna biblioteka do tworzenia, edytowania i konwertowania dokumentów programu Word do aplikacji .NET. Oferuje wiele zaawansowanych funkcji do przetwarzania tekstu w dokumentach, w tym zarządzanie wersjami.

#### P: Jak utworzyć nowy dokument w Aspose.Words dla .NET?

 Odp.: Zanim zaczniesz manipulować tekstem w dokumencie, musisz utworzyć nowy dokument za pomocą Aspose.Words dla .NET. Można to zrobić poprzez utworzenie instancji a`Document` obiekt. Oto przykładowy kod umożliwiający utworzenie nowego dokumentu:

```csharp
Document doc = new Document();
```

#### P: Jak wstawić nieedytowany tekst do dokumentu za pomocą Aspose.Words dla .NET?

 Odp.: Gdy już masz dokument, możesz wstawić niesprawdzony tekst za pomocą a`DocumentBuilder` obiekt. Na przykład, aby wstawić tekst „Usunięty tekst”, możesz użyć metody`Writeln` I`Write` metody:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### P: Jak usunąć akapit ze śledzeniem wersji w Aspose.Words dla .NET?

Odpowiedź: Aby zilustrować użycie funkcji „Ignoruj tekst w środku, usuń wersje”, usuniemy akapit z dokumentu za pomocą śledzenia wersji. Dzięki temu będziemy mogli zobaczyć jak ta funkcja wpływa na kolejne operacje.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### P: Jak włączyć funkcję „Ignoruj tekst wewnątrz Usuń wersje” w Aspose.Words dla .NET?

 O: Teraz, gdy przygotowaliśmy dokument poprzez usunięcie akapitu, możemy włączyć funkcję „Ignoruj tekst w środku, usuń wersje” za pomocą`FindReplaceOptions` obiekt. Ustalimy`IgnoreDeleted`własność do`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### P: Jak wyszukiwać i zamieniać przy użyciu wyrażeń regularnych w Aspose.Words dla .NET?

Odp.: Aby wykonać operacje wyszukiwania i zamiany na tekście dokumentu, użyjemy wyrażeń regularnych. W naszym przykładzie wyszukamy wszystkie wystąpienia litery „e” i zastąpimy je gwiazdką „* „. Będziemy używać platformy .NET`Regex` klasa do tego:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### P: Jak wyświetlić zmienioną treść dokumentu w Aspose.Words dla .NET?

Odp.: Po zastosowaniu wyszukiwania i zamiany możemy wyświetlić zmienioną treść dokumentu za pomocą`GetText` metoda:

```csharp
Console.WriteLine(doc.GetText());
```

#### P: Jak uwzględnić usunięty tekst w wynikach wyjściowych w Aspose.Words dla .NET?

 Odp.: Jeśli chcemy uwzględnić usunięty tekst w wynikach wyjściowych, możemy zmienić opcje, aby nie ignorować usuniętego tekstu. W tym celu ustawimy`IgnoreDeleted`własność do`false`:

```csharp
options. IgnoreDeleted = false;
```

#### P: Jak wyświetlić edytowany dokument z usuniętym tekstem w Aspose.Words dla .NET?

Odp.: Po zmianie opcji możemy przeprowadzić nowe wyszukiwanie i zastąpić, aby uzyskać wynik zawierający usunięty tekst:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
