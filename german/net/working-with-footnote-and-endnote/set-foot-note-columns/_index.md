---
title: Fußnotenspalten festlegen
linktitle: Fußnotenspalten festlegen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Anzahl der Spalten für Fußnoten in Word-Dokumenten festlegen.
type: docs
weight: 10
url: /de/net/working-with-footnote-and-endnote/set-foot-note-columns/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET die Anzahl der Spalten für Fußnoten in einem Word-Dokument festlegen. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst die`Document` Objekt, indem Sie den Pfad zu Ihrem Quelldokument angeben:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Schritt 2: Fußnotenspalten festlegen

 Als nächstes greifen Sie auf zu`FootnoteOptions`Eigenschaft des Dokuments und legen Sie die fest`Columns` Eigenschaft, um die Anzahl der Spalten für Fußnoten anzugeben. In diesem Beispiel legen wir es auf 3 Spalten fest:

```csharp
doc.FootnoteOptions.Columns = 3;
```

## Schritt 3: Speichern des Dokuments

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

Das ist es! Sie haben die Anzahl der Spalten für Fußnoten in einem Word-Dokument mit Aspose.Words für .NET erfolgreich festgelegt.

### Beispielquellcode für „Fußnotenspalten festlegen“ mit Aspose.Words für .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Document doc = new Document(dataDir + "Document.docx");

// Geben Sie die Anzahl der Spalten an, mit denen der Fußnotenbereich formatiert wird.
doc.FootnoteOptions.Columns = 3;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.