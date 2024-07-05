---
title: Position von Fußnote und Endnote festlegen
linktitle: Position von Fußnote und Endnote festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Position von Fußnoten und Endnoten in Word-Dokumenten festlegen.
type: docs
weight: 10
url: /de/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

In diesem Schritt-für-Schritt-Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET die Position von Fußnoten und Endnoten in einem Word-Dokument festlegen. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

 Stellen Sie zunächst sicher, dass Sie Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet haben. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek herunter und installieren Sie sie von[[Originaltext von Aspose.Releases]https://releases.aspose.com/words/net/.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst den`Document` Objekt, indem Sie den Pfad zu Ihrem Quelldokument angeben:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Schritt 2: Festlegen der Fußnoten- und Endnotenposition

 Als nächstes greifen Sie auf die`FootnoteOptions` Und`EndnoteOptions`Eigenschaften des Dokuments, um die Position von Fußnoten und Endnoten festzulegen. In diesem Beispiel legen wir die Position der Fußnoten unter dem Text und die Position der Endnoten am Ende des Abschnitts fest:

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

### Beispielquellcode zum Festlegen der Fußnoten- und Endnotenposition mit Aspose.Words für .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und ihn entsprechend Ihren spezifischen Anforderungen ändern.

### Häufig gestellte Fragen

#### F: Wie kann ich Fußnoten und Endnoten in Aspose.Words positionieren?

 A: Um Fußnoten und Endnoten in Aspose.Words zu positionieren, müssen Sie die`FootnoteOptions` Klasse und die`Position` Eigenschaft. Sie können diese Eigenschaft auf jeden beliebigen Wert setzen, beispielsweise`BottomOfPage` (unten auf der Seite) oder`EndOfSection` (am Ende des Abschnitts).

#### F: Ist es möglich, die Position von Fußnoten und Endnoten für jede Seite oder jeden Abschnitt des Dokuments anzupassen?

A: Ja, es ist möglich, die Position von Fußnoten und Endnoten für jede Seite oder jeden Abschnitt des Dokuments anzupassen. Sie können die Abschnitts- und Seitenbearbeitungsmethoden von Aspose.Words verwenden, um bestimmte Positionen für Fußnoten und Endnoten zu definieren.

#### F: Wie entferne ich Fußnoten oder Endnoten aus einem Dokument?

 A: Um Fußnoten oder Endnoten aus einem Dokument in Aspose.Words zu entfernen, können Sie entsprechende Methoden verwenden, wie zum Beispiel`RemoveAllFootnotes` alle Fußnoten zu entfernen oder`RemoveAllEndnotes` , um alle Endnoten zu entfernen. Denken Sie daran, das Dokument nach der Durchführung dieser Vorgänge zu speichern.

#### F: Können Fußnoten und Endnoten außerhalb der Seitenränder positioniert werden?

Nein, standardmäßig können Fußnoten und Endnoten in Aspose.Words nicht außerhalb der Seitenränder positioniert werden. Sie können jedoch die Dokumentränder anpassen, um bei Bedarf mehr Platz für Fußnoten und Endnoten zu schaffen.

#### F: Können Fußnoten und Endnoten mit bestimmten Schriftarten oder Formatierungsstilen angepasst werden?

A: Ja, Sie können Fußnoten und Endnoten mit bestimmten Schriftarten oder Formatierungsstilen in Aspose.Words anpassen. Sie können die verfügbaren Methoden und Eigenschaften verwenden, um Schriftarten, Farben, Schriftgrößen usw. auf Fußnoten und Endnoten anzuwenden.