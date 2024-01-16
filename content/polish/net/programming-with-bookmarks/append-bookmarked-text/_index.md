---
title: Dołącz zaznaczony tekst do dokumentu programu Word
linktitle: Dołącz zaznaczony tekst do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodać tekst z zakładki w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-bookmarks/append-bookmarked-text/
---

W tym artykule przeanalizujemy powyższy kod źródłowy C#, aby zrozumieć, jak używać funkcji Dołącz tekst z zakładkami w bibliotece Aspose.Words dla .NET. Ta funkcja umożliwia dodanie tekstu zawartego w określonej zakładce dokumentu programu Word do innego dokumentu.

## Warunki wstępne

- Podstawowa znajomość języka C#.
- Środowisko programistyczne .NET z zainstalowaną biblioteką Aspose.Words.

## Krok 1: Pobieranie akapitów z zakładki

 Zanim zaczniemy dodawać tekst zakładki, musimy pozyskać akapity zawierające początek i koniec zakładki. Można tego dokonać poprzez dostęp do`BookmarkStart` I`BookmarkEnd` właściwości zakładki:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Krok 2: Sprawdź akapity nadrzędne

Sprawdzamy, czy akapity początkowy i końcowy mają prawidłowych rodziców, to znaczy, czy rzeczywiście należą do akapitu. Jeśli nie, generujemy wyjątek:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Krok 3: Sprawdź rodziców akapitów

Sprawdzamy, czy akapit początkowy i końcowy mają tego samego rodzica. Jeśli nie, oznacza to, że akapity nie znajdują się w tej samej sekcji lub dokumencie i zgłaszamy wyjątek:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Krok 4: Skopiuj akapity

Iterujemy po węzłach (akapitach) od akapitu początkowego do akapitu końcowego. Dla każdego węzła tworzymy kopię i importujemy ją w kontekście dokumentu docelowego:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Przykładowy kod źródłowy dodawania tekstu z zakładkami przy użyciu Aspose.Words dla .NET

Oto pełny przykładowy kod źródłowy demonstrujący dodawanie tekstu z zakładki przy użyciu Aspose.Words dla .NET:

```csharp

	// To jest akapit zawierający początek zakładki.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// To jest akapit zawierający koniec zakładki.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Ograniczmy się do w miarę prostego scenariusza.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Chcemy skopiować wszystkie akapity od akapitu początkowego do akapitu końcowego (włącznie),
	// dlatego węzeł, w którym się zatrzymujemy, znajduje się po akapicie końcowym.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//Tworzy to kopię bieżącego węzła i importuje ją (uważa) w kontekście
		// dokumentu docelowego. Importowanie oznacza prawidłowe dostosowanie stylów i identyfikatorów list.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Wniosek

W tym artykule zbadaliśmy kod źródłowy C#, aby zrozumieć, jak korzystać z funkcji Dołącz tekst z zakładkami w Aspose.Words dla .NET. Postępowaliśmy zgodnie z przewodnikiem krok po kroku dotyczącym pobierania akapitów z zakładki, weryfikowania elementów nadrzędnych i kopiowania akapitów do innego dokumentu.

### Często zadawane pytania dotyczące dodawania tekstu z zakładek w dokumencie programu Word

#### P1: Jakie są wymagania wstępne, aby móc korzystać z funkcji „Dodaj tekst z zakładkami” w Aspose.Words dla .NET?

O: Aby korzystać z funkcji „Dodaj tekst z zakładkami” w Aspose.Words dla .NET, musisz posiadać podstawową wiedzę o języku C#. Potrzebujesz także środowiska programistycznego .NET z zainstalowaną biblioteką Aspose.Words.

#### P2: Jak uzyskać akapity zawierające początek i koniec zakładki w dokumencie programu Word?

Odp.: Aby uzyskać akapity zawierające początek i koniec zakładki w dokumencie programu Word, możesz uzyskać dostęp do`BookmarkStart` I`BookmarkEnd` właściwości zakładki. Oto przykładowy kod:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### P3: Co się stanie, jeśli akapity początkowy i końcowy nie mają prawidłowych akapitów nadrzędnych?

O: Jeśli akapity początkowy i końcowy nie mają prawidłowych rodziców, tj. tak naprawdę nie są akapitami, zostanie zgłoszony wyjątek. W tej chwili nie da się opanować tej sytuacji.
