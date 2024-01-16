---
title: Usuń komentarze z pliku PDF
linktitle: Usuń komentarze z pliku PDF
second_title: Aspose.Words API do przetwarzania dokumentów
description: Usuń komentarze z pliku PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-revisions/remove-comments-in-pdf/
---

W tym przewodniku krok po kroku powiemy Ci, jak usunąć komentarze z pliku PDF za pomocą Aspose.Words dla .NET. Dostarczymy Ci pełny kod źródłowy i pokażemy, jak sformatować wynik przeceny.

## Krok 1: Ładowanie dokumentu

Pierwszym krokiem jest załadowanie dokumentu zawierającego komentarze.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Krok 2: Ukryj komentarze w formacie PDF

Skonfigurujemy opcję układu, aby ukryć komentarze podczas generowania pliku PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Krok 3: Zapisz dokument jako plik PDF

Na koniec zapiszemy dokument w formacie PDF, usuwając komentarze.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Formaty wyjściowe Markdown

Dane wyjściowe można sformatować w formacie przeceny, aby poprawić czytelność. Na przykład :

```markdown
- Comments are hidden in the generated PDF.
```

### Przykładowy kod źródłowy narzędzia Usuń komentarze w formacie PDF przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy do usuwania komentarzy w pliku PDF przy użyciu Aspose.Words dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Ukryj komentarze w pliku PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Wniosek

tym samouczku nauczyliśmy się, jak usuwać komentarze z pliku PDF za pomocą Aspose.Words dla .NET. Dzięki zastosowaniu odpowiednich opcji układu udało nam się ukryć komentarze podczas generowania pliku PDF. Aspose.Words dla .NET oferuje dużą elastyczność w manipulowaniu plikami Word i konwertowaniu ich do różnych formatów, w tym PDF. Możesz teraz zastosować tę wiedzę do usuwania komentarzy we własnych plikach PDF za pomocą Aspose.Words dla .NET.

### Często zadawane pytania dotyczące usuwania komentarzy w pliku pdf

#### P: Jak przesłać dokument do Aspose.Words dla .NET?

 O: Skorzystaj z`Document` klasa Aspose.Words dla .NET, aby załadować dokument z pliku. Można określić pełną ścieżkę dokumentu.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: Jak ukryć komentarze w formacie PDF wygenerowanym za pomocą Aspose.Words dla .NET?

 O: Skorzystaj z`CommentDisplayMode` własność`LayoutOptions` obiekt, aby skonfigurować sposób wyświetlania komentarzy podczas generowania pliku PDF. Aby ukryć komentarze, ustaw tę właściwość na`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### P: Jak zapisać dokument w formacie PDF za pomocą Aspose.Words dla .NET?

 O: Skorzystaj z`Save` metoda`Document` obiekt, aby zapisać dokument w formacie PDF. Określ pełną ścieżkę pliku PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```