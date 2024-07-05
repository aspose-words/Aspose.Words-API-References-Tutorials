---
title: Kommentar gelöst und Antworten
linktitle: Kommentar gelöst und Antworten
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kommentare und deren Antworten in Word-Dokumenten auflösen.
type: docs
weight: 10
url: /de/net/working-with-comments/comment-resolved-and-replies/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie Kommentare und deren Antworten in einem Word-Dokument mit Aspose.Words für .NET auflösen. Wir führen Sie durch den Prozess und stellen Ihnen die erforderlichen C#-Codeausschnitte zur Verfügung. Am Ende dieses Handbuchs können Sie die Kommentarauflösung verwalten und den Status von Kommentaren und deren Antworten aktualisieren.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Auf Ihrem System ist die Bibliothek Aspose.Words für .NET installiert.

## Schritt 1: Laden Sie das Dokument und greifen Sie auf Kommentare zu
Laden Sie zunächst das Dokument, das die Kommentare enthält, mithilfe der Klasse „Document“ und greifen Sie auf die Kommentarsammlung zu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Schritt 2: Kommentare und deren Antworten auflösen
Gehen Sie als Nächstes die Kommentare und die dazugehörigen Antworten durch, um sie als gelöst zu markieren:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

Im obigen Code greifen wir auf den übergeordneten Kommentar zu und durchlaufen seine Antworten. Wir können die ID des übergeordneten Kommentars und seinen Lösungsstatus abrufen. Anschließend aktualisieren wir die Markierung „Erledigt“ jeder Kommentarantwort, um die Lösung anzuzeigen.

## Schritt 3: Speichern Sie das Dokument
Nachdem Sie die Kommentare aufgelöst und ihren Status aktualisiert haben, speichern Sie das geänderte Dokument mit der Methode Save der Klasse Document in einer Datei:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Beispiel-Quellcode zum Auflösen von Kommentaren und deren Antworten mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Auflösen von Kommentaren und ihren Antworten mit Aspose.Words für .NET:

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
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie Kommentare und ihre Antworten in einem Word-Dokument mit Aspose.Words für .NET auflösen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt die Kommentarauflösung verwalten und den Status von Kommentaren und ihren Antworten entsprechend Ihren Anforderungen aktualisieren.

Die Kommentarauflösung hilft beim Verfolgen und Verwalten von Feedback innerhalb eines Dokuments. Experimentieren Sie mit verschiedenen Kommentarstatus und passen Sie sie an, um die Zusammenarbeit und die Überprüfungsprozesse in Ihren Dokumenten zu verbessern.

### Häufig gestellte Fragen

#### F: Wie löse ich einen Kommentar in Aspose.Words für .NET auf?

 A: Um einen Kommentar in Aspose.Words für .NET aufzulösen, können Sie den`Comment.Resolve` Methode zur Angabe der`Comment` Objekt, das Sie auflösen möchten. Dadurch wird der Kommentar als aufgelöst markiert und im endgültigen Dokument ausgeblendet.

#### F: Wie füge ich in Aspose.Words für .NET eine Antwort zu einem aufgelösten Kommentar hinzu?

 A: Obwohl gelöste Kommentare standardmäßig im endgültigen Dokument ausgeblendet sind, können Sie dennoch eine Antwort auf einen gelösten Kommentar hinzufügen, indem Sie das`Comment.AddReply`Methode, die den Antworttext angibt und wo Sie ihn hinzufügen möchten.

#### F: Wie kann ich aufgelöste Kommentare in Aspose.Words für .NET anzeigen?

 A: Standardmäßig sind gelöste Kommentare im endgültigen Dokument ausgeblendet. Sie können sie jedoch anzeigen, indem Sie das`CommentOptions.ShowResolvedComments` Eigentum der`Document` Objekt und setzen Sie es auf`true`.

#### F: Wie kann ich alle Kommentare, einschließlich Antworten, in Aspose.Words für .NET ausblenden?

 A: Um alle Kommentare, einschließlich Antworten, in Aspose.Words für .NET auszublenden, können Sie den`CommentOptions.CommentDisplayMode` Eigentum der`Document` Objekt und setzen Sie es auf`CommentDisplayMode.None`.

#### F: Kann ich den Text eines aufgelösten Kommentars in Aspose.Words für .NET bearbeiten?

 A: Ja, Sie können den Text eines aufgelösten Kommentars in Aspose.Words für .NET bearbeiten, indem Sie auf die`Comment.Text` Eigentum des entsprechenden`Comment` Objekt und ändern Sie den Text nach Bedarf.