---
title: Endnote-Optionen festlegen
linktitle: Endnote-Optionen festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Endnotenoptionen in Word-Dokumenten festlegen. Schritt-für-Schritt-Anleitung mit Beispiel-Quellcode.
type: docs
weight: 10
url: /de/net/working-with-footnote-and-endnote/set-endnote-options/
---

In diesem Schritt-für-Schritt-Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Endnotenoptionen in einem Word-Dokument festlegen. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

 Stellen Sie zunächst sicher, dass Sie Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet haben. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek herunter und installieren Sie sie von[[Originaltext von Aspose.Releases]https://releases.aspose.com/words/net/.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst den`Document` Objekt, indem Sie den Pfad zu Ihrem Quelldokument angeben:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Schritt 2: Initialisieren des DocumentBuilder-Objekts

 Als nächstes initialisieren Sie den`DocumentBuilder` Objekt, um Operationen am Dokument durchzuführen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Text und Endnote hinzufügen

 Verwenden Sie die`Write` Methode der`DocumentBuilder` Objekt, um Text zum Dokument hinzuzufügen, und das`InsertFootnote` Methode zum Einfügen einer Endnote:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Schritt 4: Endnote-Optionen festlegen

 Greife auf ... zu`EndnoteOptions`Eigenschaft des Dokuments, um Endnotenoptionen zu ändern. In diesem Beispiel legen wir die Neustartregel so fest, dass auf jeder Seite neu gestartet wird und die Position am Ende des Abschnitts:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Schritt 5: Speichern des Dokuments

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich Endnotenoptionen in einem Word-Dokument festgelegt.

### Beispielquellcode zum Festlegen von Endnote-Optionen mit Aspose.Words für .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und ihn entsprechend Ihren spezifischen Anforderungen ändern.

### Häufig gestellte Fragen

#### F: Wie kann ich Endnoten in Aspose.Words formatieren?

 A: Um Endnoten in Aspose.Words zu formatieren, können Sie die`EndnoteOptions` Klasse und die`SeparatorNoteTextStyle` Eigenschaft. Mit dieser Eigenschaft können Sie Schriftstil, Größe, Farbe usw. für Endnoten angeben.

#### F: Ist es möglich, die Nummerierung der Endnoten in einem Dokument anzupassen?

 A: Ja, es ist möglich, die Nummerierung von Endnoten in einem Dokument anzupassen. Sie können die`RestartRule` Und`NumberStyle` Eigenschaften der`EndnoteOptions` Klasse zum Definieren spezifischer Neustartregeln und Nummerierungsstile.

#### F: Wie kann ich Endnoten in einem Dokument positionieren?

A: Um Endnoten in einem Dokument zu positionieren, können Sie die`Position` Eigentum der`EndnoteOptions` Klasse. Sie können angeben, ob Endnoten am unteren Ende jeder Seite, am Ende jedes Abschnitts oder am Ende des Dokuments platziert werden sollen.

#### F: Kann ich das Nummerierungsformat der Endnoten anpassen?

 A: Ja, Sie können das Format der Endnotennummerierung in Aspose.Words anpassen. Verwenden Sie die`NumberFormat` Eigentum der`EndnoteOptions` Klasse, um das gewünschte Format festzulegen, beispielsweise arabische Ziffern, römische Ziffern, Buchstaben usw.

#### F: Ist es möglich, die Endnotennummerierung zwischen Abschnitten eines Dokuments fortzusetzen?

 A: Ja, es ist möglich, die Endnotennummerierung zwischen den Abschnitten eines Dokuments fortzusetzen. Verwenden Sie die`RestartRule` Eigentum der`EndnoteOptions` Klasse und setzen Sie sie auf`RestartContinuous` um die Nummerierung zwischen den Abschnitten fortzusetzen.