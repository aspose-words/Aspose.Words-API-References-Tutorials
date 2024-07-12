---
title: Kommentare in PDF-Datei entfernen
linktitle: Kommentare in PDF-Datei entfernen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Entfernen Sie Kommentare in einer PDF-Datei mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-revisions/remove-comments-in-pdf/
---

In dieser Schritt-für-Schritt-Anleitung erklären wir Ihnen, wie Sie mit Aspose.Words für .NET Kommentare aus einer PDF-Datei entfernen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Dokument einlegen

Der erste Schritt besteht darin, das Dokument mit den Kommentaren zu laden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Schritt 2: Kommentare im PDF ausblenden

Wir werden die Layoutoption so konfigurieren, dass Kommentare beim Generieren des PDF ausgeblendet werden.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Schritt 3: Speichern Sie das Dokument als PDF

Abschließend speichern wir das Dokument im PDF-Format, indem wir die Kommentare löschen.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Markdown-Ausgabeformate

Die Ausgabe kann zur besseren Lesbarkeit in Markdown formatiert werden. Beispiel:

```markdown
- Comments are hidden in the generated PDF.
```

### Beispielquellcode zum Entfernen von Kommentaren in PDFs mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Entfernen von Kommentaren in einer PDF-Datei mit Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Kommentare im PDF ausblenden.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Kommentare aus einer PDF-Datei entfernt. Durch die Verwendung der entsprechenden Layoutoptionen konnten wir die Kommentare beim Generieren des PDFs ausblenden. Aspose.Words für .NET bietet große Flexibilität beim Bearbeiten von Word-Dateien und Konvertieren in verschiedene Formate, einschließlich PDF. Sie können dieses Wissen jetzt anwenden, um mit Aspose.Words für .NET Kommentare in Ihren eigenen PDF-Dateien zu entfernen.

### FAQs zum Entfernen von Kommentaren in PDF-Dateien

#### F: Wie lade ich ein Dokument in Aspose.Words für .NET hoch?

 A: Verwenden Sie die`Document` Klasse von Aspose.Words für .NET, um ein Dokument aus einer Datei zu laden. Sie können den vollständigen Dokumentpfad angeben.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Wie verstecke ich Kommentare in einer mit Aspose.Words für .NET erstellten PDF-Datei?

 A: Verwenden Sie die`CommentDisplayMode` Eigentum der`LayoutOptions` Objekt, um zu konfigurieren, wie Kommentare beim Generieren der PDF angezeigt werden. Um Kommentare auszublenden, setzen Sie diese Eigenschaft auf`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### F: Wie speichere ich ein Dokument mit Aspose.Words für .NET als PDF?

 A: Verwenden Sie die`Save` Methode der`Document` Objekt, um das Dokument im PDF-Format zu speichern. Geben Sie den vollständigen Pfad der PDF-Datei an.

```csharp
doc.Save("path/to/the/file.pdf");
```