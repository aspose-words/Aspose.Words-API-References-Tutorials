---
title: Kommentar gelöst und Antworten
linktitle: Kommentar gelöst und Antworten
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Kommentare und deren Antworten in Word-Dokumenten mit Aspose.Words für .NET auflösen.
type: docs
weight: 10
url: /de/net/working-with-comments/comment-resolved-and-replies/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie Kommentare und deren Antworten in einem Word-Dokument mit Aspose.Words für .NET auflösen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Leitfadens werden Sie in der Lage sein, die Kommentarauflösung zu verwalten und den Status von Kommentaren und deren Antworten zu aktualisieren.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Laden Sie das Dokument und greifen Sie auf Kommentare zu
Laden Sie zunächst das Dokument, das die Kommentare enthält, mithilfe der Document-Klasse und greifen Sie auf die Kommentarsammlung zu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Schritt 2: Kommentare und deren Antworten auflösen
Gehen Sie als Nächstes die Kommentare und ihre Antworten durch, um sie als gelöst zu markieren:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

Im obigen Code greifen wir auf den übergeordneten Kommentar zu und durchlaufen seine Antworten. Wir können die ID des übergeordneten Kommentars und seinen Lösungsstatus abrufen. Anschließend aktualisieren wir die „Fertig“-Markierung jeder Kommentarantwort, um die Lösung anzuzeigen.

## Schritt 3: Speichern Sie das Dokument
Nachdem Sie die Kommentare aufgelöst und ihren Status aktualisiert haben, speichern Sie das geänderte Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Beispielquellcode zum Auflösen von Kommentaren und deren Antworten mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Auflösen von Kommentaren und deren Antworten mit Aspose.Words für .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Denken Sie daran, den Code entsprechend Ihren spezifischen Anforderungen anzupassen, einschließlich des Dokumentdateipfads und zusätzlicher Anpassungen

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET Kommentare und deren Antworten in einem Word-Dokument auflösen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie nun die Kommentarauflösung verwalten und den Status von Kommentaren und deren Antworten entsprechend Ihren Anforderungen aktualisieren.

Die Kommentarauflösung hilft bei der Verfolgung und Verwaltung von Feedback innerhalb eines Dokuments. Experimentieren Sie mit verschiedenen Kommentarstatus und passen Sie diese an, um die Zusammenarbeit und Überprüfungsprozesse in Ihren Dokumenten zu verbessern.
