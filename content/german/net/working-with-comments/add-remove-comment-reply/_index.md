---
title: Kommentarantwort hinzufügen und entfernen
linktitle: Kommentarantwort hinzufügen und entfernen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kommentarantworten in Word-Dokumenten hinzufügen und entfernen.
type: docs
weight: 10
url: /de/net/working-with-comments/add-remove-comment-reply/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Kommentarantworten in einem Word-Dokument hinzufügen und entfernen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Leitfadens werden Sie in der Lage sein, Kommentarantworten zu verwalten und sie entsprechend Ihren Anforderungen anzupassen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Laden Sie das Dokument
Laden Sie zunächst das Dokument, das die Kommentare enthält, mithilfe der Document-Klasse:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Schritt 2: Greifen Sie auf den Kommentar zu und verwalten Sie die Antworten
Greifen Sie als Nächstes über die GetChild-Methode mit dem NodeType.Comment-Parameter auf den Kommentar aus dem Dokument zu:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Um eine Antwort aus dem Kommentar zu entfernen, verwenden Sie die RemoveReply-Methode und geben Sie den gewünschten Antwortindex an:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Um dem Kommentar eine neue Antwort hinzuzufügen, verwenden Sie die AddReply-Methode und geben Sie den Namen des Autors, die Initialen des Autors, Datum und Uhrzeit sowie den Antworttext an:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Schritt 3: Speichern Sie das Dokument
Nachdem Sie Kommentarantworten hinzugefügt oder entfernt haben, speichern Sie das Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Beispielquellcode zum Hinzufügen und Entfernen von Kommentarantworten mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Hinzufügen und Entfernen von Kommentarantworten mit Aspose.Words für .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET Kommentarantworten in einem Word-Dokument hinzufügen und entfernen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie nun Kommentarantworten verwalten und sie entsprechend Ihren Anforderungen anpassen.

Kommentarantworten ermöglichen gemeinsame Diskussionen und Feedback innerhalb eines Dokuments. Experimentieren Sie mit verschiedenen Antwortautoren, Initialen, Daten und Texten, um die Zusammenarbeit und Kommunikation in Ihren Dokumenten zu verbessern.

### FAQs

#### F: Wie kann ich in Aspose.Words für .NET einen Kommentar hinzufügen?

 A: Um einen Kommentar in Aspose.Words für .NET hinzuzufügen, können Sie die verwenden`Comment.AddComment` -Methode, die den Text des Kommentars und die Stelle angibt, an der Sie ihn im Dokument hinzufügen möchten.

#### F: Wie kann ich einen Kommentar in Aspose.Words für .NET entfernen?

A: Um einen Kommentar in Aspose.Words für .NET zu entfernen, können Sie Folgendes verwenden`Comment.Remove` Methode, die die angibt`Comment` Objekt, das Sie entfernen möchten.

#### F: Kann ich auf einen Kommentar in Aspose.Words für .NET antworten?

 A: Ja, Sie können in Aspose.Words für .NET auf einen Kommentar antworten`Comment.AddReply` Methode, die den Antworttext angibt und angibt, wo Sie ihn im Dokument hinzufügen möchten.

#### F: Wie kann ich auf vorhandene Kommentare in Aspose.Words für .NET zugreifen?

 A: Sie können mit dem auf vorhandene Kommentare in Aspose.Words für .NET zugreifen`CommentCollection` Eigentum der`Document` Objekt. Auf diese Weise können Sie alle im Dokument vorhandenen Kommentare durchsuchen.

#### F: Kann ich Kommentartext in Aspose.Words für .NET bearbeiten?

 A: Ja, Sie können den Text eines Kommentars in Aspose.Words für .NET bearbeiten, indem Sie auf zugreifen`Comment.Text` Eigentum des entsprechenden`Comment` Objekt und ändern Sie den Text nach Bedarf.