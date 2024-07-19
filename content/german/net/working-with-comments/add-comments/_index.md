---
title: Füge Kommentare hinzu
linktitle: Füge Kommentare hinzu
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kommentare zu Word-Dokumenten hinzufügen.
type: docs
weight: 10
url: /de/net/working-with-comments/add-comments/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Kommentare zu einem Word-Dokument hinzufügen. Wir führen Sie durch den Prozess und stellen Ihnen die erforderlichen C#-Codeausschnitte zur Verfügung. Am Ende dieses Handbuchs können Sie Kommentare einfügen und deren Inhalt in Ihren Dokumenten anpassen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Auf Ihrem System ist die Bibliothek Aspose.Words für .NET installiert.

## Schritt 1: Neues Dokument und DocumentBuilder erstellen
Erstellen Sie zunächst ein neues Dokument mit der Klasse „Document“ und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Dem Dokument Inhalt hinzufügen
Als nächstes fügen Sie dem Dokument mit dem DocumentBuilder-Objekt den gewünschten Inhalt hinzu. In diesem Beispiel fügen wir Text hinzu:

```csharp
builder.Write("Some text is added.");
```

## Schritt 3: Kommentar erstellen und Inhalt hinzufügen
Um einen Kommentar hinzuzufügen, erstellen Sie eine Instanz der Klasse „Comment“ und übergeben Sie das Dokumentobjekt, den Namen des Autors, die Initialen des Autors und das aktuelle Datum:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Als nächstes fügen Sie den Kommentar an den aktuellen Absatz an:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Fügen Sie dem Kommentar Inhalte hinzu, beispielsweise einen Absatz und Text:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Schritt 4: Speichern Sie das Dokument
Nachdem Sie den Kommentar und seinen Inhalt hinzugefügt haben, speichern Sie das Dokument mit der Methode Save der Klasse Document in einer Datei:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Beispiel-Quellcode zum Hinzufügen von Kommentaren mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Hinzufügen von Kommentaren mit Aspose.Words für .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET Kommentare zu einem Word-Dokument hinzufügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt Kommentare einfügen und deren Inhalt in Ihren Dokumenten anpassen.

Kommentare sind nützlich für die Zusammenarbeit, um zusätzliche Informationen bereitzustellen oder Notizen in einem Dokument zu machen. Experimentieren Sie mit verschiedenen Autorennamen, Initialen und Kommentarinhalten, um Ihre spezifischen Anforderungen zu erfüllen.

### Häufig gestellte Fragen

#### F: Wie kann ich einem Aspose.Words-Dokument für .NET einen Kommentar hinzufügen?

A: Um einen Kommentar in ein Aspose.Words-Dokument für .NET einzufügen, müssen Sie die im Tutorial genannten Schritte befolgen.

#### F: Kann ich Kommentartext in Aspose.Words für .NET formatieren?

A: Ja, Sie können Kommentartext in Aspose.Words für .NET mit den verfügbaren Formatierungseigenschaften formatieren.

#### F: Wie kann ich alle in einem Dokument vorhandenen Kommentare abrufen?

 A: Sie können alle in einem Dokument vorhandenen Kommentare abrufen, indem Sie`Document.Comments` Eigentum.

#### F: Kann ich einen bestimmten Kommentar in Aspose.Words für .NET löschen?

 A: Ja, Sie können einen bestimmten Kommentar in Aspose.Words für .NET entfernen, indem Sie`Comment.Remove` Methode.

#### F: Wie kann ich den Text eines vorhandenen Kommentars in Aspose.Words für .NET ändern?

 A: Um den Text eines vorhandenen Kommentars in Aspose.Words für .NET zu ändern, können Sie auf die`Comment.Text` Eigentum des entsprechenden`Comment` Objekt und ändern Sie den Text nach Bedarf.