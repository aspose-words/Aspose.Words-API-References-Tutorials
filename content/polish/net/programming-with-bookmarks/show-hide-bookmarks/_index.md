---
title: Pokaż Ukryj zakładki w dokumencie programu Word
linktitle: Pokaż Ukryj zakładki w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak pokazać lub ukryć określoną zakładkę w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-bookmarks/show-hide-bookmarks/
---

W tym artykule omówimy powyższy kod źródłowy C#, aby zrozumieć, jak używać funkcji Pokaż ukryj zakładki w bibliotece Aspose.Words dla .NET. Ta funkcja umożliwia pokazanie lub ukrycie określonej zakładki w dokumencie programu Word.

## Warunki wstępne

- Podstawowa znajomość języka C#.
- Środowisko programistyczne .NET z zainstalowaną biblioteką Aspose.Words.

## Krok 1: Ładowanie dokumentu

 Używamy`Document` klasa, aby załadować istniejący dokument z pliku:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Krok 2: Pokaż lub ukryj konkretną zakładkę

 Używamy`ShowHideBookmarkedContent` funkcja umożliwiająca pokazanie lub ukrycie określonej zakładki w dokumencie. Ta funkcja przyjmuje jako parametry dokument, nazwę zakładki i wartość logiczną wskazującą, czy pokazać, czy ukryć zakładkę:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Krok 3: Zapisanie zmodyfikowanego dokumentu

 Używamy`Save` metoda zapisania zmodyfikowanego dokumentu do pliku:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Przykładowy kod źródłowy opcji Pokaż ukryj zakładki przy użyciu Aspose.Words dla .NET

Oto pełny przykładowy kod źródłowy demonstrujący pokazywanie lub ukrywanie określonej zakładki przy użyciu Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### Kod źródłowy ShowHideBookmarkedContent

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
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
        }
		
```
## Wniosek

W tym artykule zbadaliśmy kod źródłowy C#, aby zrozumieć, jak korzystać z funkcji Pokaż ukryj zakładki w Aspose.Words dla .NET. Postępowaliśmy zgodnie z przewodnikiem krok po kroku, jak pokazać lub ukryć określoną zakładkę w dokumencie.

### Często zadawane pytania dotyczące pokazywania i ukrywania zakładek w dokumencie programu Word

#### P: Czy mogę pokazać lub ukryć wiele zakładek w tym samym dokumencie?

O: Tak, możesz pokazać lub ukryć wiele zakładek w tym samym dokumencie, powtarzając kroki 2 i 3 dla każdej zakładki, którą chcesz przetworzyć.

#### P: Czy dostarczony kod działa z innymi formatami dokumentów programu Word, takimi jak .doc lub .docm?

Odp.: Tak, dostarczony kod działa z różnymi formatami dokumentów Word obsługiwanymi przez Aspose.Words, takimi jak .doc i .docm. Pamiętaj tylko, aby podczas ładowania i zapisywania dokumentu użyć prawidłowej nazwy pliku i ścieżki.

#### P: Jak mogę ponownie wyświetlić ukrytą zakładkę?

 Odp.: Aby ponownie wyświetlić ukrytą zakładkę, musisz jej użyć`ShowHideBookmarkedContent` funkcja przekazująca wartość`true` dla parametru logicznego wskazującego, czy pokazać, czy ukryć zakładkę.

#### P: Czy mogę używać warunków, aby pokazywać lub ukrywać zakładki na podstawie wartości pól scalania w dokumencie?

 O: Tak, możesz użyć warunków i wartości pól scalających, aby określić, czy zakładka ma być pokazana, czy ukryta. Możesz dostosować kod pliku`ShowHideBookmarkedContent` funkcję uwzględniającą odpowiednie warunki i wartości.

#### P: Jak mogę usunąć zakładkę w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

 Odp.: Aby usunąć zakładkę w dokumencie programu Word za pomocą programu Aspose.Words dla .NET, możesz użyć metody`RemoveBookmarks` metoda`Document` klasa. Oto przykładowy kod:

```csharp
doc.RemoveBookmarks("BookmarkName");
```