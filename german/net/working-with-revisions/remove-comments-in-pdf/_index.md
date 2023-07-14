---
title: Entfernen Sie Kommentare in einer PDF-Datei
linktitle: Entfernen Sie Kommentare in einer PDF-Datei
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Entfernen Sie Kommentare in einer PDF-Datei mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-revisions/remove-comments-in-pdf/
---

In dieser Schritt-für-Schritt-Anleitung erklären wir Ihnen, wie Sie Kommentare in einer PDF-Datei mit Aspose.Words für .NET entfernen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Laden des Dokuments

Der erste Schritt besteht darin, das Dokument mit den Kommentaren zu laden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Schritt 2: Kommentare im PDF ausblenden

Wir werden die Layout-Option so konfigurieren, dass Kommentare beim Generieren der PDF-Datei ausgeblendet werden.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Schritt 3: Speichern Sie das Dokument als PDF

Abschließend speichern wir das Dokument im PDF-Format, indem wir die Kommentare löschen.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Markdown-Ausgabeformate

Die Ausgabe kann zur Verbesserung der Lesbarkeit im Markdown formatiert werden. Zum Beispiel :

```markdown
- Comments are hidden in the generated PDF.
```

### Beispielquellcode zum Entfernen von Kommentaren in PDF mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Entfernen von Kommentaren in einer PDF-Datei mit Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Kommentare im PDF ausblenden.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Kommentare aus einer PDF-Datei entfernt. Durch die Verwendung der entsprechenden Layoutoptionen konnten wir die Kommentare beim Generieren des PDFs ausblenden. Aspose.Words für .NET bietet große Flexibilität bei der Bearbeitung von Word-Dateien und deren Konvertierung in verschiedene Formate, einschließlich PDF. Sie können dieses Wissen jetzt anwenden, um Kommentare in Ihren eigenen PDF-Dateien mit Aspose.Words für .NET zu entfernen.

### FAQs zum Entfernen von Kommentaren in PDF-Dateien

#### F: Wie lade ich ein Dokument in Aspose.Words für .NET hoch?

 A: Benutzen Sie die`Document` Klasse von Aspose.Words für .NET zum Laden eines Dokuments aus einer Datei. Sie können den vollständigen Dokumentpfad angeben.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Wie verstecke ich Kommentare in PDFs, die mit Aspose.Words für .NET generiert wurden?

 A: Benutzen Sie die`CommentDisplayMode`Eigentum der`LayoutOptions` -Objekt, um zu konfigurieren, wie Kommentare beim Generieren der PDF-Datei angezeigt werden. Um Kommentare auszublenden, legen Sie diese Eigenschaft auf fest`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### F: Wie speichere ich ein Dokument als PDF mit Aspose.Words für .NET?

 A: Benutzen Sie die`Save` Methode der`Document` Objekt, um das Dokument im PDF-Format zu speichern. Geben Sie den vollständigen Pfad der PDF-Datei an.

```csharp
doc.Save("path/to/the/file.pdf");
```