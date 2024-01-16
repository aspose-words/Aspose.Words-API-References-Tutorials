---
title: Pokaż Ukryj zawartość dodaną do zakładek w dokumencie programu Word
linktitle: Pokaż Ukryj zawartość dodaną do zakładek w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak pokazać lub ukryć zawartość zakładek w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

tym artykule przeanalizujemy powyższy kod źródłowy C#, aby zrozumieć, jak używać funkcji Pokaż ukryj zawartość zakładek w bibliotece Aspose.Words dla .NET. Ta funkcja umożliwia pokazanie lub ukrycie zawartości zakładki w dokumencie programu Word w oparciu o określony warunek podczas łączenia danych.

## Warunki wstępne

- Podstawowa znajomość języka C#.
- Środowisko programistyczne .NET z zainstalowaną biblioteką Aspose.Words.

## Krok 1: Uzyskanie zakładki

 Używamy`Bookmarks` właściwość zakresu dokumentu, aby uzyskać konkretną zakładkę, na której chcemy pokazać lub ukryć treść:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Krok 2: Wstawianie pól scalających

 Korzystamy z kreatora dokumentów`DocumentBuilder` , aby wstawić niezbędne pola scalania. Te pola scalania ustawią warunek pokazania lub ukrycia zawartości zakładek w zależności od wartości`showHide` zmienny:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Krok 3: Przenoszenie zawartości zakładek

Przeglądamy zawartość zakładki i przesuwamy ją tak, aby się pojawiła

jest przed zakładką. Będzie to kontrolować wyświetlanie lub ukrywanie treści w oparciu o określony warunek:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## Krok 4: Przeniesienie pozostałej zawartości zakładki

Pozostałą zawartość zakładki przenosimy za zakładką, wykorzystując węzeł końcowy zakładki jako punkt wstawiania:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## Krok 5: Wykonanie scalania

 Używamy`Execute` sposób dokumentu`s `MailMerge` object to execute the merge using the bookmark name and the value of the `pokażUkryj zmienną:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Przykładowy kod źródłowy opcji Pokaż ukryj zawartość dodaną do zakładek przy użyciu Aspose.Words dla .NET

Oto pełny przykład kodu źródłowego demonstrujący pokazywanie lub ukrywanie zawartości zakładek przy użyciu Aspose.Words dla .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{Zakładka MERGEFIELD}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Wniosek

W tym artykule zbadaliśmy kod źródłowy C#, aby zrozumieć, jak korzystać z funkcji Pokaż ukryj zawartość zakładek w Aspose.Words dla .NET. Postępowaliśmy zgodnie z przewodnikiem krok po kroku, aby pokazać lub ukryć zawartość zakładki w oparciu o określony warunek podczas łączenia danych.

### Często zadawane pytania dotyczące pokazywania i ukrywania treści z zakładek w dokumencie programu Word

#### P: Czy mogę użyć tego samego warunku dla wielu zakładek w tym samym dokumencie?

Odpowiedź: Tak, możesz użyć tego samego warunku dla wielu zakładek w tym samym dokumencie. Po prostu powtórz kroki 2-5 dla każdej zakładki, dostosowując nazwę zakładki i opcjonalnie wartość`showhide` zmienna w zależności od potrzeb.

#### P: Jak mogę dodać więcej warunków, aby pokazać lub ukryć zawartość zakładek?

 O: Aby dodać więcej warunków, możesz użyć operatorów logicznych, takich jak`AND` I`OR` w kodzie służącym do wstawiania pól scalania w kroku 2. Edytuj warunek w poniższym kodzie, aby dodać dodatkowe warunki:

```csharp
builder. Write("\" = \"true\" ");
```

#### P: Jak mogę usunąć zakładkę w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

 Odp.: Aby usunąć zakładkę w dokumencie programu Word za pomocą programu Aspose.Words dla .NET, możesz użyć metody`Remove` metoda z`Bookmarks` zbiór zakresu dokumentów. Oto przykładowy kod usuwania określonej zakładki:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### P: Czy biblioteka Aspose.Words jest bezpłatna?

 O: Biblioteka Aspose.Words jest biblioteką komercyjną i wymaga ważnej licencji, aby móc jej używać w projektach. Możesz sprawdzić[Aspose.Words dla referencji .NET API](https://reference.aspose.com/words/net/) aby dowiedzieć się więcej o opcjach licencjonowania i cenach.

#### P: Czy są dostępne inne biblioteki do przetwarzania tekstu w dokumentach programu Word w platformie .NET?

O: Tak, dostępne są inne biblioteki do przetwarzania tekstu z dokumentami programu Word w platformie .NET, takie jak Open XML SDK i GemBox.Document. Możesz eksplorować te biblioteki jako alternatywę dla Aspose.Words w oparciu o Twoje specyficzne potrzeby i preferencje.