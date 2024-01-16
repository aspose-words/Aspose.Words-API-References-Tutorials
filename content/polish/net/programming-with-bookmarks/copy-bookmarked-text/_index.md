---
title: Skopiuj tekst z zakładek do dokumentu programu Word
linktitle: Skopiuj tekst z zakładek do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak skopiować tekst zakładek z dokumentu programu Word do innego dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-bookmarks/copy-bookmarked-text/
---

tym artykule omówimy powyższy kod źródłowy C#, aby zrozumieć, jak używać funkcji Kopiuj tekst z zakładkami w bibliotece Aspose.Words dla .NET. Ta funkcja umożliwia skopiowanie zawartości określonej zakładki z dokumentu źródłowego do innego dokumentu.

## Warunki wstępne

- Podstawowa znajomość języka C#.
- Środowisko programistyczne .NET z zainstalowaną biblioteką Aspose.Words.

## Krok 1: Ładowanie dokumentu źródłowego

 Przed skopiowaniem tekstu zakładki musimy załadować dokument źródłowy do pliku`Document` obiekt przy użyciu ścieżki pliku:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Krok 2: Pobieranie zakładki źródłowej

 Używamy`Bookmarks` właściwość zakresu dokumentu źródłowego, aby uzyskać konkretną zakładkę, którą chcemy skopiować:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Krok 3: Tworzenie dokumentu docelowego

Tworzymy nowy dokument, który będzie dokumentem docelowym do skopiowania zawartości zakładki:

```csharp
Document dstDoc = new Document();
```

## Krok 4: Określanie lokalizacji kopii

Określamy lokalizację, w której chcemy dodać skopiowany tekst. W naszym przykładzie dodajemy tekst na końcu treści ostatniej sekcji dokumentu docelowego:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Krok 5: Zaimportuj i skopiuj tekst zakładki

 Używamy A`NodeImporter`obiekt, aby zaimportować i skopiować tekst zakładek z dokumentu źródłowego do dokumentu docelowego:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Przykładowy kod źródłowy kopiowania tekstu z zakładkami przy użyciu Aspose.Words dla .NET

Oto pełny przykładowy kod źródłowy demonstrujący kopiowanie tekstu z zakładki przy użyciu Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// To jest zakładka, której zawartość chcemy skopiować.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Będziemy uzupełniać ten dokument.
	Document dstDoc = new Document();

	// Powiedzmy, że zostaniemy dołączeni na końcu treści ostatniej sekcji.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Jeśli importujesz wiele razy bez jednego kontekstu, spowoduje to utworzenie wielu stylów.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### Dołącz kod źródłowy BookmarkedText

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
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
        }

```
## Wniosek

W tym artykule zbadaliśmy kod źródłowy C#, aby zrozumieć, jak korzystać z funkcji Kopiuj tekst z zakładkami z Aspose.Words dla .NET. Postępowaliśmy zgodnie z przewodnikiem krok po kroku, jak skopiować zawartość zakładki z dokumentu źródłowego do innego dokumentu.

### Często zadawane pytania dotyczące kopiowania tekstu z zakładek w dokumencie programu Word

#### P: Jakie są wymagania, aby korzystać z funkcji „Kopiuj tekst za pomocą zakładek” w Aspose.Words dla .NET?

Odp.: Aby korzystać z funkcji „Kopiuj tekst za pomocą zakładek” w Aspose.Words dla .NET, musisz mieć podstawową wiedzę o języku C#. Potrzebujesz także środowiska programistycznego .NET z zainstalowaną biblioteką Aspose.Words.

#### P: Jak załadować dokument źródłowy do Aspose.Words dla .NET?

 Odp.: Aby załadować dokument źródłowy do Aspose.Words dla .NET, możesz użyć metody`Document` class, określając ścieżkę pliku dokumentu. Oto przykładowy kod:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### P: Jak uzyskać zawartość określonej zakładki w dokumencie źródłowym przy użyciu Aspose.Words dla .NET?

 Odp.: Aby uzyskać zawartość określonej zakładki w dokumencie źródłowym przy użyciu Aspose.Words dla .NET, możesz uzyskać dostęp do`Bookmarks` właściwość zakresu dokumentu źródłowego i użyj nazwy zakładki, aby pobrać konkretną zakładkę. Oto przykładowy kod:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### P: Jak określić lokalizację kopii tekstu zakładki w dokumencie docelowym przy użyciu Aspose.Words dla .NET?

 O: Aby określić, gdzie chcesz dodać skopiowany tekst zakładek w dokumencie docelowym przy użyciu Aspose.Words dla .NET, możesz przejść do treści ostatniej sekcji dokumentu docelowego. Możesz skorzystać z`LastSection` aby uzyskać dostęp do ostatniej sekcji i pliku`Body` właściwość, aby uzyskać dostęp do treści tej sekcji. Oto przykładowy kod:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### P: Jak importować i kopiować tekst zakładek z dokumentu źródłowego do dokumentu docelowego przy użyciu Aspose.Words dla .NET?

 O: Aby zaimportować i skopiować tekst zakładek z dokumentu źródłowego do dokumentu docelowego za pomocą Aspose.Words dla .NET, możesz użyć`NodeImporter` class określająca dokument źródłowy, dokument docelowy i tryb formatowania, który ma zostać zachowany. Następnie możesz użyć`AppendBookmarkedText` metoda dodania tekstu zakładki w dokumencie docelowym. Oto przykładowy kod:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### P: Jak zapisać dokument docelowy po skopiowaniu tekstu zakładek przy użyciu Aspose.Words dla .NET?

Odp.: Aby zapisać dokument docelowy po skopiowaniu tekstu z zakładki przy użyciu Aspose.Words dla .NET, możesz użyć`Save` metoda`Document` obiekt określający ścieżkę pliku docelowego. Oto przykładowy kod:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```