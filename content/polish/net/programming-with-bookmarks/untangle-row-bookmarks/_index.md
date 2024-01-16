---
title: Rozplątaj zakładki wierszy w dokumencie programu Word
linktitle: Rozplątaj zakładki wierszy w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak rozplątać zagnieżdżone zakładki wierszy w dokumencie programu Word, aby usunąć określone wiersze bez wpływu na inne zakładki.
type: docs
weight: 10
url: /pl/net/programming-with-bookmarks/untangle-row-bookmarks/
---

tym artykule zbadamy powyższy kod źródłowy C#, aby zrozumieć, jak używać funkcji Rozplątuj zakładki wierszy w bibliotece Aspose.Words dla .NET. Funkcja ta umożliwia umieszczenie końców zakładek linii w jednej linii z początkami zakładek.

## Warunki wstępne

- Podstawowa znajomość języka C#.
- Środowisko programistyczne .NET z zainstalowaną biblioteką Aspose.Words.

## Krok 1: Ładowanie dokumentu

 Używamy`Document` klasa, aby załadować istniejący dokument z pliku:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Krok 2: Rozwikłaj zakładki liniowe

 Używamy`Untangle` funkcja rozplątywania zakładek z wierszy. Ta funkcja wykonuje niestandardowe zadanie polegające na umieszczeniu końcówek linii w tej samej linii, w której zaczyna się zakładka:

```csharp
Untangle(doc);
```

## Krok 3: Usuń linię po zakładce

 Używamy`DeleteRowByBookmark` funkcja usuwania określonego wiersza według jego zakładki:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Krok 4: Sprawdź integralność innych zakładek

Sprawdzamy, czy pozostałe zakładki nie zostały uszkodzone, sprawdzając, czy końcówka zakładki jest nadal obecna:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Przykładowy kod źródłowy dla zakładek Untangle Row przy użyciu Aspose.Words dla .NET

Oto pełny przykładowy kod źródłowy umożliwiający rozplątanie zakładek z linii za pomocą Aspose.Words dla .NET:


```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Wykonuje niestandardowe zadanie polegające na umieszczeniu końców zakładek wiersza w tym samym wierszu, w którym rozpoczyna się zakładka.
	Untangle(doc);

	// Teraz możemy łatwo usuwać wiersze według zakładek, nie uszkadzając zakładek innych wierszy.
	DeleteRowByBookmark(doc, "ROW2");

	// Ma to na celu jedynie sprawdzenie, czy druga zakładka nie została uszkodzona.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### Rozwikłaj kod źródłowy
```csharp

private void Untangle(Document doc)
        {
            foreach (Bookmark bookmark in doc.Range.Bookmarks)
            {
                // Pobierz wiersz nadrzędny zarówno zakładki, jak i węzła końcowego zakładki.
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                // Jeśli oba wiersze zostaną znalezione prawidłowo, a początek i koniec zakładki znajdują się w sąsiednich wierszach,
                // przesuń węzeł końcowy zakładki na koniec ostatniego akapitu w ostatniej komórce górnego wiersza.
                if (row1 != null && row2 != null && row1.NextSibling == row2)
                    row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
            }
        }

```

#### Kod źródłowy DeleteRowByBookmark
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## Wniosek

W tym artykule zbadaliśmy kod źródłowy C#, aby zrozumieć, jak korzystać z funkcji Rozplątuj zakładki wierszy w Aspose.Words dla .NET. Postępowaliśmy zgodnie z przewodnikiem krok po kroku, jak rozplątać zakładki wierszy i usunąć określony wiersz bez uszkodzenia innych zakładek.

### Często zadawane pytania dotyczące rozplątywania zakładek wierszy w dokumencie programu Word

#### P: Czy rozszyfrowanie zakładek wierszy działa tylko z zakładkami wierszy w tabelach?

O: Tak, funkcja Rozplątuj zakładki wierszy została specjalnie zaprojektowana do rozplątywania zakładek wierszy znajdujących się w tabelach. Tej funkcji można używać do przetwarzania zakładek linii w tablicach i zapewniania, że końce zakładek znajdują się w tej samej linii, co początki zakładek.

#### P: Czy funkcja Rozszyfruj zakładki linii modyfikuje zawartość oryginalnego dokumentu?

O: Tak, funkcja Rozszyfruj zakładki linii modyfikuje oryginalny dokument, przesuwając końce zakładek linii, aby umieścić je w tej samej linii, co początki zakładek. Przed zastosowaniem tej funkcji pamiętaj o zapisaniu kopii zapasowej dokumentu.

#### P: Jak mogę zidentyfikować zakładki liniowe w dokumencie programu Word?

Odp.: Zakładki wierszy są zwykle używane w tabelach do oznaczania określonych sekcji. Zakładki wierszy można zidentyfikować, przeglądając zakładki w dokumencie i sprawdzając, czy zakładki znajdują się w wierszach tabeli.

#### P: Czy można rozplątać zakładki wierszy w tabelach, które nie sąsiadują ze sobą?

O: Funkcja Rozwikłaj zakładki wierszy przedstawiona w tym artykule ma na celu rozplątanie zakładek wierszy w sąsiednich tabelach. Aby rozdzielić zakładki wierszy w niesąsiadujących ze sobą tabelach, mogą być wymagane dodatkowe poprawki w kodzie, w zależności od struktury dokumentu.

#### P: Jakie inne manipulacje mogę wykonać na zakładkach wierszy po ich rozwikłaniu?

Odp.: Po rozwikłaniu zakładek linii możesz w razie potrzeby wykonać różne manipulacje. Może to obejmować edycję, usuwanie lub dodawanie treści do zakładek. Z zakładkami liniowymi należy obchodzić się ostrożnie, aby uniknąć niepożądanego wpływu na resztę dokumentu.