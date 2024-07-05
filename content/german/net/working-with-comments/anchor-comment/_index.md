---
title: Ankerkommentar
linktitle: Ankerkommentar
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kommentarantworten an bestimmten Text in Word-Dokumenten verankern.
type: docs
weight: 10
url: /de/net/working-with-comments/anchor-comment/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Kommentarantworten an bestimmten Text in einem Word-Dokument verankern. Wir führen Sie durch den Prozess und stellen Ihnen die erforderlichen C#-Codeausschnitte zur Verfügung. Am Ende dieses Leitfadens können Sie Kommentare mit bestimmten Texten in Ihren Dokumenten verknüpfen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Auf Ihrem System ist die Bibliothek Aspose.Words für .NET installiert.

## Schritt 1: Neues Dokument erstellen und Text hinzufügen
Erstellen Sie zunächst ein neues Dokument mit der Klasse „Document“ und fügen Sie den gewünschten Text hinzu:

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

## Schritt 2: Einen Kommentar erstellen und einen Kommentarbereich hinzufügen
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
Nachdem Sie den Kommentar an einem bestimmten Text verankert haben, speichern Sie das Dokument mit der Methode Save der Klasse Document in einer Datei:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Beispiel-Quellcode für Anchor Comment Reply mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Verankern einer Kommentarantwort mit Aspose.Words für .NET:

```csharp
// Erstellen Sie eine Instanz des Dokuments.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Erstellen Sie drei Run-Objekte.
//Die ersten beiden geben einen Text aus, während der dritte einen Kommentar ausgibt.

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

// Jedem Run-Objekt sind die Objekte CommentRangeStart und CommentRangeEnd zugeordnet.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### Häufig gestellte Fragen

#### F: Was ist ein Kommentaranker in Aspose.Words für .NET?

A: In Aspose.Words für .NET ist ein Kommentaranker ein Marker, der einen Kommentar mit einer bestimmten Stelle in einem Dokument verbindet.

#### F: Wie kann ich in einem Aspose.Words-Dokument für .NET einen Kommentaranker hinzufügen?

A: Um einen Kommentaranker in einem Aspose.Words-Dokument für .NET hinzuzufügen, befolgen Sie die im Tutorial beschriebenen Schritte.

#### F: Wie greife ich in Aspose.Words für .NET auf einen vorhandenen Kommentaranker zu?

 A: Sie können auf einen vorhandenen Kommentaranker in Aspose.Words für .NET zugreifen, indem Sie`Comment.Anchor` Eigentum.

#### F: Kann ich einen Kommentaranker in Aspose.Words für .NET unterdrücken?

 A: Ja, Sie können einen Kommentaranker in Aspose.Words für .NET entfernen, indem Sie`Comment.Remove` Methode.

#### F: Wie kann ich den Text eines Kommentars bearbeiten, der mit einem Kommentaranker in Aspose.Words für .NET verknüpft ist?

A: Um den Text eines Kommentars zu ändern, der an einen Kommentaranker in Aspose.Words für .NET gebunden ist, können Sie auf die`Comment.Text` Eigentum des entsprechenden`Comment` Objekt und ändern Sie den Text nach Bedarf.

