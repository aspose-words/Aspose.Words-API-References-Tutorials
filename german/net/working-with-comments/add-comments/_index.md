---
title: Füge Kommentare hinzu
linktitle: Füge Kommentare hinzu
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kommentare zu Word-Dokumenten hinzufügen.
type: docs
weight: 10
url: /de/net/working-with-comments/add-comments/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Kommentare zu einem Word-Dokument hinzufügen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Leitfadens werden Sie in der Lage sein, Kommentare einzufügen und deren Inhalt in Ihren Dokumenten anzupassen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Inhalte zum Dokument hinzufügen
Fügen Sie als Nächstes mithilfe des DocumentBuilder-Objekts den gewünschten Inhalt zum Dokument hinzu. In diesem Beispiel fügen wir etwas Text hinzu:

```csharp
builder.Write("Some text is added.");
```

## Schritt 3: Erstellen Sie einen Kommentar und fügen Sie Inhalte hinzu
Um einen Kommentar hinzuzufügen, erstellen Sie eine Instanz der Comment-Klasse und übergeben Sie das Document-Objekt, den Namen des Autors, die Initialen des Autors und das aktuelle Datum:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Als nächstes hängen Sie den Kommentar an den aktuellen Absatz an:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Fügen Sie dem Kommentar Inhalte hinzu, z. B. einen Absatz und Text:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Schritt 4: Speichern Sie das Dokument
Nachdem Sie den Kommentar und seinen Inhalt hinzugefügt haben, speichern Sie das Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Beispielquellcode für das Hinzufügen von Kommentaren mit Aspose.Words für .NET
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
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET Kommentare zu einem Word-Dokument hinzufügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt Kommentare einfügen und deren Inhalt in Ihren Dokumenten anpassen.

Kommentare sind nützlich für die Zusammenarbeit, für die Bereitstellung zusätzlicher Informationen oder für Notizen innerhalb eines Dokuments. Experimentieren Sie mit verschiedenen Autorennamen, Initialen und Kommentarinhalten, um Ihren spezifischen Anforderungen gerecht zu werden.