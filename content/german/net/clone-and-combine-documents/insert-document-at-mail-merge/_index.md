---
title: Dokument beim Seriendruck einfügen
linktitle: Dokument beim Seriendruck einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie in diesem umfassenden Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.Words für .NET Dokumente in Seriendruckfelder einfügen.
type: docs
weight: 10
url: /de/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## Einführung

Willkommen in der Welt der Dokumentenautomatisierung mit Aspose.Words für .NET! Haben Sie sich jemals gefragt, wie Sie während eines Seriendruckvorgangs Dokumente dynamisch in bestimmte Felder innerhalb eines Hauptdokuments einfügen können? Dann sind Sie hier genau richtig. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess des Einfügens von Dokumenten in Serienbrieffelder mit Aspose.Words für .NET. Es ist, als würde man ein Puzzle zusammensetzen, bei dem jedes Teil perfekt zusammenpasst. Also, lasst uns eintauchen!

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1.  Aspose.Words für .NET: Das können Sie[Laden Sie die neueste Version hier](https://releases.aspose.com/words/net/) . Wenn Sie eine Lizenz erwerben müssen, können Sie dies tun[Hier](https://purchase.aspose.com/buy) . Alternativ erhalten Sie eine[temporäre Lizenz](https://purchase.aspose.com/temporary-license/) oder probieren Sie es mit einem aus[Kostenlose Testphase](https://releases.aspose.com/).
2. Entwicklungsumgebung: Visual Studio oder eine andere C#-IDE.
3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, wird dieses Tutorial zum Kinderspiel.

## Namespaces importieren

Als Erstes müssen Sie die erforderlichen Namespaces importieren. Dies sind sozusagen die Bausteine Ihres Projekts.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

Lassen Sie uns den Prozess in überschaubare Schritte unterteilen. Jeder Schritt baut auf dem vorherigen auf und führt Sie zu einer vollständigen Lösung.

## Schritt 1: Einrichten Ihres Verzeichnisses

Bevor Sie mit dem Einfügen von Dokumenten beginnen können, müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis definieren. Hier werden Ihre Dokumente gespeichert.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden des Hauptdokuments

Als Nächstes laden Sie das Hauptdokument. Dieses Dokument enthält die Zusammenführungsfelder, in die andere Dokumente eingefügt werden.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## Schritt 3: Festlegen des Rückrufs für die Feldzusammenführung

Um den Zusammenführungsprozess abzuwickeln, müssen Sie eine Rückruffunktion festlegen. Diese Funktion ist für das Einfügen von Dokumenten in die angegebenen Zusammenführungsfelder verantwortlich.

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Schritt 4: Ausführen des Seriendrucks

Jetzt ist es an der Zeit, den Serienbrief auszuführen. Hier geschieht die Magie. Sie geben das Zusammenführungsfeld und das Dokument an, das in dieses Feld eingefügt werden soll.

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## Schritt 5: Speichern des Dokuments

Nachdem der Seriendruck abgeschlossen ist, speichern Sie das geänderte Dokument. In diesem neuen Dokument wird der Inhalt genau dort eingefügt, wo Sie ihn haben möchten.

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## Schritt 6: Erstellen des Callback-Handlers

Der Callback-Handler ist eine Klasse, die eine spezielle Verarbeitung für das Zusammenführungsfeld durchführt. Es lädt das im Feldwert angegebene Dokument und fügt es in das aktuelle Seriendruckfeld ein.

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## Schritt 7: Einfügen des Dokuments

Diese Methode fügt das angegebene Dokument in den aktuellen Absatz oder die aktuelle Tabellenzelle ein.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
        foreach (Node srcNode in srcSection.Body)
        {
            if (srcNode.NodeType == NodeType.Paragraph)
            {
                Paragraph para = (Paragraph)srcNode;
                if (para.IsEndOfSection && !para.HasChildNodes)
                    continue;
            }

            Node newNode = importer.ImportNode(srcNode, true);
            destinationParent.InsertAfter(newNode, insertionDestination);
            insertionDestination = newNode;
        }
    }
    else
    {
        throw new ArgumentException("The destination node should be either a paragraph or table.");
    }
}
```

## Abschluss

Und da haben Sie es! Sie haben während eines Seriendruckvorgangs mit Aspose.Words für .NET erfolgreich Dokumente in bestimmte Felder eingefügt. Diese leistungsstarke Funktion kann Ihnen eine Menge Zeit und Mühe ersparen, insbesondere beim Umgang mit großen Dokumentenmengen. Stellen Sie sich das so vor, als hätten Sie einen persönlichen Assistenten, der Ihnen die ganze schwere Arbeit abnimmt. Probieren Sie es einfach aus. Viel Spaß beim Codieren!

## FAQs

### Kann ich mehrere Dokumente in verschiedene Zusammenführungsfelder einfügen?
 Ja, du kannst. Geben Sie einfach die entsprechenden Zusammenführungsfelder und entsprechenden Dokumentpfade im an`MailMerge.Execute` Methode.

### Ist es möglich, das eingefügte Dokument anders als das Hauptdokument zu formatieren?
 Absolut! Du kannst den ... benutzen`ImportFormatMode` Parameter in der`NodeImporter` um die Formatierung zu steuern.

### Was passiert, wenn der Name des Zusammenführungsfelds dynamisch ist?
Sie können dynamische Zusammenführungsfeldnamen verarbeiten, indem Sie sie als Parameter an den Callback-Handler übergeben.

### Kann ich diese Methode mit verschiedenen Dateiformaten verwenden?
Ja, Aspose.Words unterstützt verschiedene Dateiformate, darunter DOCX, PDF und mehr.

### Wie gehe ich mit Fehlern beim Einfügen des Dokuments um?
Implementieren Sie die Fehlerbehandlung in Ihrem Callback-Handler, um eventuell auftretende Ausnahmen zu verwalten.