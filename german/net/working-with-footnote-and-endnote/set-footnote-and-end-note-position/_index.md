---
title: Legen Sie die Fußnoten- und Endnotenposition fest
linktitle: Legen Sie die Fußnoten- und Endnotenposition fest
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Position von Fußnoten und Endnoten in Word-Dokumenten festlegen.
type: docs
weight: 10
url: /de/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET die Position von Fußnoten und Endnoten in einem Word-Dokument festlegen. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst die`Document` Objekt, indem Sie den Pfad zu Ihrem Quelldokument angeben:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Schritt 2: Fußnoten- und Endnotenposition festlegen

 Als nächstes greifen Sie auf zu`FootnoteOptions` Und`EndnoteOptions` Eigenschaften des Dokuments, um die Position von Fußnoten und Endnoten festzulegen. In diesem Beispiel legen wir die Position der Fußnoten unter dem Text und die Position der Endnoten am Ende des Abschnitts fest:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Schritt 3: Speichern des Dokuments

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Das ist es! Sie haben die Position von Fußnoten und Endnoten in einem Word-Dokument mit Aspose.Words für .NET erfolgreich festgelegt.

### Beispielquellcode für „Fußnoten- und Endnotenposition festlegen“ mit Aspose.Words für .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.

### FAQs

#### F: Wie kann ich Fußnoten und Endnoten in Aspose.Words positionieren?

 A: Um Fußnoten und Endnoten in Aspose.Words zu positionieren, müssen Sie die verwenden`FootnoteOptions` Klasse und die`Position` Eigentum. Sie können diese Eigenschaft auf einen beliebigen Wert festlegen, z`BottomOfPage` (am Ende der Seite) oder`EndOfSection`(am Ende des Abschnitts).

#### F: Ist es möglich, die Position von Fußnoten und Endnoten für jede Seite oder jeden Abschnitt des Dokuments anzupassen?

A: Ja, es ist möglich, die Position von Fußnoten und Endnoten für jede Seite oder jeden Abschnitt des Dokuments anzupassen. Sie können die Abschnitts- und Seitenbearbeitungsmethoden von Aspose.Words verwenden, um bestimmte Positionen für Fußnoten und Endnoten zu definieren.

#### F: Wie entferne ich Fußnoten oder Endnoten aus einem Dokument?

 A: Um Fußnoten oder Endnoten aus einem Dokument in Aspose.Words zu entfernen, können Sie entsprechende Methoden verwenden, z`RemoveAllFootnotes` um alle Fußnoten zu entfernen oder`RemoveAllEndnotes` um alle Endnoten zu entfernen. Stellen Sie sicher, dass Sie das Dokument speichern, nachdem Sie diese Vorgänge ausgeführt haben.

#### F: Können Fußnoten und Endnoten außerhalb der Seitenränder positioniert werden?

Nein, standardmäßig können Fußnoten und Endnoten in Aspose.Words nicht außerhalb der Seitenränder positioniert werden. Sie können jedoch die Dokumentränder anpassen, um bei Bedarf mehr Platz für Fußnoten und Endnoten zu schaffen.

#### F: Können Fußnoten und Endnoten mit bestimmten Schriftarten oder Formatierungsstilen angepasst werden?

A: Ja, Sie können Fußnoten und Endnoten in Aspose.Words mit bestimmten Schriftarten oder Formatierungsstilen anpassen. Sie können die verfügbaren Methoden und Eigenschaften verwenden, um Schriftstile, Farben, Schriftgrößen usw. auf Fußnoten und Endnoten anzuwenden.