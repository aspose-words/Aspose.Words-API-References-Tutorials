---
title: Kommentare im PDF entfernen
linktitle: Kommentare im PDF entfernen
second_title: Aspose.Words für .NET API-Referenz
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