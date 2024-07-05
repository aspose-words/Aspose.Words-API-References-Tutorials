---
title: Hinzufügen Entfernen Kommentar Antworten
linktitle: Hinzufügen Entfernen Kommentar Antworten
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kommentarantworten in Word-Dokumenten hinzufügen und entfernen.
type: docs
weight: 10
url: /de/net/working-with-comments/add-remove-comment-reply/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Kommentarantworten in einem Word-Dokument hinzufügen und entfernen. Wir führen Sie durch den Prozess und stellen Ihnen die erforderlichen C#-Codeausschnitte zur Verfügung. Am Ende dieses Handbuchs können Sie Kommentarantworten verwalten und sie Ihren Anforderungen entsprechend anpassen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Auf Ihrem System ist die Bibliothek Aspose.Words für .NET installiert.

## Schritt 1: Dokument laden
Laden Sie zunächst das Dokument, das die Kommentare enthält, mithilfe der Klasse „Document“:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Schritt 2: Auf den Kommentar zugreifen und Antworten verwalten
Greifen Sie als Nächstes mithilfe der Methode GetChild und dem Parameter NodeType.Comment auf den Kommentar im Dokument zu:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Um eine Antwort aus dem Kommentar zu entfernen, verwenden Sie die Methode RemoveReply und geben Sie den gewünschten Antwortindex an:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Um eine neue Antwort auf den Kommentar hinzuzufügen, verwenden Sie die Methode AddReply und geben Sie den Namen des Autors, die Initialen des Autors, Datum und Uhrzeit sowie den Antworttext ein:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Schritt 3: Speichern Sie das Dokument
Nachdem Sie Kommentarantworten hinzugefügt oder entfernt haben, speichern Sie das Dokument mit der Methode Save der Klasse Document in einer Datei:

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
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET Kommentarantworten in einem Word-Dokument hinzufügen und entfernen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt Kommentarantworten verwalten und sie nach Ihren Anforderungen anpassen.

Kommentarantworten ermöglichen gemeinsame Diskussionen und Feedback innerhalb eines Dokuments. Experimentieren Sie mit verschiedenen Antwortautoren, Initialen, Daten und Texten, um die Zusammenarbeit und Kommunikation innerhalb Ihrer Dokumente zu verbessern.

### Häufig gestellte Fragen

#### F: Wie kann ich in Aspose.Words für .NET einen Kommentar hinzufügen?

 A: Um einen Kommentar in Aspose.Words für .NET hinzuzufügen, können Sie den`Comment.AddComment` Methode, die den Text des Kommentars angibt und wo Sie ihn im Dokument hinzufügen möchten.

#### F: Wie kann ich einen Kommentar in Aspose.Words für .NET entfernen?

A: Um einen Kommentar in Aspose.Words für .NET zu entfernen, können Sie den`Comment.Remove` Methode zur Angabe der`Comment` Objekt, das Sie entfernen möchten.

#### F: Kann ich in Aspose.Words für .NET auf einen Kommentar antworten?

 A: Ja, Sie können auf einen Kommentar in Aspose.Words für .NET antworten, indem Sie`Comment.AddReply` Methode, die den Antworttext angibt und wo Sie ihn im Dokument hinzufügen möchten.

#### F: Wie kann ich in Aspose.Words für .NET auf vorhandene Kommentare zugreifen?

 A: Sie können auf vorhandene Kommentare in Aspose.Words für .NET zugreifen, indem Sie`CommentCollection` Eigentum der`Document` Objekt. Dadurch können Sie alle im Dokument vorhandenen Kommentare durchsuchen.

#### F: Kann ich Kommentartext in Aspose.Words für .NET bearbeiten?

 A: Ja, Sie können den Text eines Kommentars in Aspose.Words für .NET bearbeiten, indem Sie auf die`Comment.Text` Eigentum des entsprechenden`Comment` Objekt und ändern Sie den Text nach Bedarf.