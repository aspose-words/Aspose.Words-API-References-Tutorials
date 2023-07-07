---
title: Ankerkommentar
linktitle: Ankerkommentar
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kommentarantworten zu bestimmtem Text in Word-Dokumenten verankern.
type: docs
weight: 10
url: /de/net/working-with-comments/anchor-comment/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie Kommentarantworten mit Aspose.Words für .NET an einem bestimmten Text in einem Word-Dokument verankern. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Leitfadens werden Sie in der Lage sein, Kommentare mit bestimmtem Text in Ihren Dokumenten zu verknüpfen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und fügen Sie Text hinzu
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und fügen Sie den gewünschten Text hinzu:

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

## Schritt 2: Erstellen Sie einen Kommentar und fügen Sie einen Kommentarbereich hinzu
Erstellen Sie als Nächstes einen Kommentar und verknüpfen Sie ihn mithilfe der Objekte CommentRangeStart und CommentRangeEnd mit einem bestimmten Text:

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

## Schritt 3: Speichern Sie das Dokument
Nachdem Sie den Kommentar in einem bestimmten Text verankert haben, speichern Sie das Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Beispielquellcode für eine Ankerkommentarantwort mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Verankern einer Kommentarantwort mit Aspose.Words für .NET:

```csharp
// Erstellen Sie eine Instanz des Dokuments.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Erstellen Sie drei Run-Objekte.
//Die ersten beiden führen einen Text aus, während der dritte einen Kommentar ausgibt

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

// Jedes der Run-Objekte verfügt über ein zugehöriges CommentRangeStart- und CommentRangeEnd-Objekt.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### FAQs

#### F: Was ist ein Kommentaranker in Aspose.Words für .NET?

A: In Aspose.Words für .NET ist ein Kommentaranker eine Markierung, die einen Kommentar mit einer bestimmten Stelle in einem Dokument verbindet.

#### F: Wie kann ich einem Aspose.Words für .NET-Dokument einen Kommentaranker hinzufügen?

A: Um einen Kommentaranker in einem Aspose.Words für .NET-Dokument hinzuzufügen, befolgen Sie die im Tutorial genannten Schritte.

#### F: Wie greife ich auf einen vorhandenen Kommentaranker in Aspose.Words für .NET zu?

 A: Sie können mit dem auf einen vorhandenen Kommentaranker in Aspose.Words für .NET zugreifen`Comment.Anchor` Eigentum.

#### F: Kann ich einen Kommentaranker in Aspose.Words für .NET unterdrücken?

 A: Ja, Sie können einen Kommentaranker in Aspose.Words für .NET mithilfe von entfernen`Comment.Remove` Methode.

#### F: Wie kann ich den Text eines Kommentars bearbeiten, der mit einem Kommentaranker in Aspose.Words für .NET verknüpft ist?

A: Um den Text eines Kommentars zu ändern, der an einen Kommentaranker in Aspose.Words für .NET gebunden ist, können Sie auf Folgendes zugreifen`Comment.Text` Eigentum des entsprechenden`Comment` Objekt und ändern Sie den Text nach Bedarf.

