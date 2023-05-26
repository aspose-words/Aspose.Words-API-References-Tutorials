---
title: Endnotenoptionen festlegen
linktitle: Endnotenoptionen festlegen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Endnotenoptionen in Word-Dokumenten festlegen. Schritt-für-Schritt-Anleitung mit Beispielquellcode.
type: docs
weight: 10
url: /de/net/working-with-footnote-and-endnote/set-endnote-options/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Endnotenoptionen in einem Word-Dokument festlegen. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst die`Document` Objekt, indem Sie den Pfad zu Ihrem Quelldokument angeben:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Schritt 2: Initialisieren des DocumentBuilder-Objekts

 Als nächstes initialisieren Sie die`DocumentBuilder` Objekt zum Ausführen von Vorgängen am Dokument:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Text und Endnote hinzufügen

 Benutzen Sie die`Write` Methode der`DocumentBuilder` Objekt, um dem Dokument Text hinzuzufügen, und das`InsertFootnote` Methode zum Einfügen einer Endnote:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Schritt 4: Endnotenoptionen festlegen

 Greife auf ... zu`EndnoteOptions` Eigenschaft des Dokuments, um Endnotenoptionen zu ändern. In diesem Beispiel legen wir die Neustartregel so fest, dass auf jeder Seite neu gestartet wird, und setzen die Position auf das Ende des Abschnitts:

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

### Beispielquellcode für „Set Endnote Options“ mit Aspose.Words für .NET

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

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.
