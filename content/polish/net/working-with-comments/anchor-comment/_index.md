---
title: Komentarz kotwicy
linktitle: Komentarz kotwicy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zakotwiczyć odpowiedzi na komentarze w określonym tekście w dokumentach programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-comments/anchor-comment/
---

W tym obszernym samouczku dowiesz się, jak zakotwiczyć odpowiedzi na komentarze w określonym tekście w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Przeprowadzimy Cię przez proces i udostępnimy niezbędne fragmenty kodu C#. Pod koniec tego przewodnika będziesz mógł powiązać komentarze z określonym tekstem w swoich dokumentach.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim systemie.

## Krok 1: Utwórz nowy dokument i dodaj tekst
Aby rozpocząć, utwórz nowy dokument za pomocą klasy Dokument i dodaj żądany tekst:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## Krok 2: Utwórz komentarz i dodaj zakres komentarzy
Następnie utwórz komentarz i powiąż go z konkretnym tekstem za pomocą obiektów CommentRangeStart i CommentRangeEnd:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## Krok 3: Zapisz dokument
Po zakotwiczeniu komentarza do określonego tekstu należy zapisać dokument do pliku, korzystając z metody Save klasy Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Przykładowy kod źródłowy odpowiedzi na komentarz zakotwiczenia przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy do zakotwiczenia odpowiedzi na komentarz przy użyciu Aspose.Words dla .NET:

```csharp
// Utwórz instancję dokumentu.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Utwórz trzy obiekty Run.
// Pierwsze dwa wyświetlają tekst, a trzeci uruchamia komentarz

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// Z każdym obiektem Run powiązany jest obiekt CommentRangeStart i CommentRangeEnd.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### Często zadawane pytania

#### P: Co to jest kotwica komentarza w Aspose.Words dla .NET?

O: W Aspose.Words dla .NET kotwica komentarza to znacznik, który łączy komentarz z określonym miejscem w dokumencie.

#### P: Jak mogę dodać kotwicę komentarza w dokumencie Aspose.Words dla .NET?

O: Aby dodać kotwicę komentarza w dokumencie Aspose.Words for .NET, wykonaj kroki opisane w samouczku.

#### P: Jak uzyskać dostęp do istniejącej kotwicy komentarzy w Aspose.Words dla .NET?

 O: Możesz uzyskać dostęp do istniejącej kotwicy komentarzy w Aspose.Words dla .NET za pomocą`Comment.Anchor` nieruchomość.

#### P: Czy mogę dodać kotwicę komentarza w Aspose.Words dla .NET?

 O: Tak, możesz usunąć kotwicę komentarza w Aspose.Words dla .NET za pomocą`Comment.Remove` metoda.

#### P: Jak mogę edytować tekst komentarza połączonego z kotwicą komentarza w Aspose.Words dla .NET?

 O: Aby zmodyfikować tekst komentarza powiązanego z kotwicą komentarza w Aspose.Words dla .NET, możesz uzyskać dostęp do`Comment.Text` właściwość odpowiedniego`Comment` obiekt i zmodyfikuj tekst według potrzeb.

