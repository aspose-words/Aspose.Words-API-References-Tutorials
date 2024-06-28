---
title: Dokument beim Ersetzen einfügen
linktitle: Dokument beim Ersetzen einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie in unserer detaillierten Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET nahtlos ein Word-Dokument in ein anderes einfügen. Perfekt für Entwickler, die die Dokumentenverarbeitung optimieren möchten.
type: docs
weight: 10
url: /de/net/clone-and-combine-documents/insert-document-at-replace/
---
## Einführung

Hallo, Dokumentenmaestros! Haben Sie sich schon einmal mitten im Code gefühlt und versucht herauszufinden, wie Sie ein Word-Dokument nahtlos in ein anderes einfügen können? Keine Angst, denn heute tauchen wir in die Welt von Aspose.Words für .NET ein, um diese Aufgabe zu einem Kinderspiel zu machen. Wir führen Sie durch eine detaillierte Schritt-für-Schritt-Anleitung zur Verwendung dieser leistungsstarken Bibliothek zum Einfügen von Dokumenten an bestimmten Stellen während eines Such- und Ersetzungsvorgangs. Sind Sie bereit, ein Aspose.Words-Assistent zu werden? Lass uns anfangen!

## Voraussetzungen

Bevor wir uns mit dem Code befassen, müssen Sie einige Dinge erledigen:

-  Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Wenn Sie es noch nicht haben, können Sie es hier herunterladen[Hier](https://visualstudio.microsoft.com/).
-  Aspose.Words für .NET: Sie benötigen die Aspose.Words-Bibliothek. Sie erhalten es von der[Aspose-Website](https://releases.aspose.com/words/net/).
- Grundlegende C#-Kenntnisse: Ein grundlegendes Verständnis von C# und .NET wird Ihnen beim Durcharbeiten dieses Tutorials helfen.

Okay, wenn das erledigt ist, machen wir uns mit etwas Code die Hände schmutzig!

## Namespaces importieren

Als Erstes müssen wir die notwendigen Namespaces importieren, um mit Aspose.Words arbeiten zu können. Das ist so, als würden Sie alle Ihre Werkzeuge zusammentragen, bevor Sie mit einem Projekt beginnen. Fügen Sie diese using-Anweisungen oben in Ihrer C#-Datei hinzu:

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

Nachdem wir nun alle Voraussetzungen geschaffen haben, unterteilen wir den Prozess in kleine Schritte. Jeder Schritt ist entscheidend und bringt uns unserem Ziel näher.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Zuerst müssen wir das Verzeichnis angeben, in dem unsere Dokumente gespeichert sind. Das ist, als würde man die Bühne vor dem großen Auftritt bereiten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu Ihrem Verzeichnis. Hier werden Ihre Dokumente leben und atmen.

## Schritt 2: Laden Sie das Hauptdokument

Als nächstes laden wir das Hauptdokument, in das wir ein weiteres Dokument einfügen möchten. Betrachten Sie dies als unsere Hauptbühne, auf der die ganze Action stattfinden wird.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

Dieser Code lädt das Hauptdokument aus dem angegebenen Verzeichnis.

## Schritt 3: Legen Sie die Such- und Ersetzungsoptionen fest

Um die spezifische Stelle zu finden, an der wir unser Dokument einfügen möchten, verwenden wir die Funktion „Suchen und Ersetzen“. Das ist, als würde man mithilfe einer Karte den genauen Standort für unseren Neuzugang finden.

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

Hier legen wir die Richtung auf „Rückwärts“ fest und geben einen benutzerdefinierten Callback-Handler an, den wir als Nächstes definieren.

## Schritt 4: Führen Sie den Ersetzungsvorgang durch

Jetzt weisen wir unser Hauptdokument an, nach einem bestimmten Platzhaltertext zu suchen und ihn durch nichts zu ersetzen, während wir unseren benutzerdefinierten Rückruf verwenden, um ein anderes Dokument einzufügen.

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

Dieser Code führt den Such- und Ersetzungsvorgang aus und speichert dann das aktualisierte Dokument.

## Schritt 5: Erstellen Sie einen benutzerdefinierten ersetzenden Callback-Handler

Unser benutzerdefinierter Callback-Handler ist der Ort, an dem die Magie geschieht. Dieser Handler definiert, wie das Einfügen des Dokuments während des Such- und Ersetzungsvorgangs durchgeführt wird.

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // Fügen Sie nach dem Absatz, der den passenden Text enthält, ein Dokument ein.
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // Entfernen Sie den Absatz mit dem passenden Text.
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

Hier laden wir das einzufügende Dokument und rufen dann eine Hilfsmethode auf, um das Einfügen durchzuführen.

## Schritt 6: Definieren Sie die Methode zum Einfügen von Dokumenten

Das letzte Teil unseres Puzzles ist die Methode, mit der das Dokument tatsächlich an der angegebenen Stelle eingefügt wird.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// Durchlaufen Sie alle Knoten auf Blockebene im Hauptteil des Abschnitts.
		// Klonen Sie dann jeden Knoten und fügen Sie ihn ein, der nicht der letzte leere Absatz eines Abschnitts ist.
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

Diese Methode sorgt dafür, dass Knoten aus dem einzufügenden Dokument importiert und an der richtigen Stelle im Hauptdokument platziert werden.

## Abschluss

Und da haben Sie es! Eine umfassende Anleitung zum Einfügen eines Dokuments in ein anderes mithilfe von Aspose.Words für .NET. Wenn Sie diese Schritte befolgen, können Sie Aufgaben zur Dokumentzusammenstellung und -bearbeitung problemlos automatisieren. Egal, ob Sie ein Dokumentenmanagementsystem aufbauen oder einfach nur Ihren Dokumentenverarbeitungs-Workflow optimieren müssen, Aspose.Words ist Ihr treuer Begleiter.

## FAQs

### Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum programmgesteuerten Bearbeiten von Word-Dokumenten. Damit können Sie ganz einfach Word-Dokumente erstellen, ändern, konvertieren und verarbeiten.

### Kann ich mehrere Dokumente gleichzeitig einfügen?
Ja, Sie können den Callback-Handler so ändern, dass er mehrere Einfügungen verarbeitet, indem er eine Sammlung von Dokumenten durchläuft.

### Gibt es eine kostenlose Testversion?
 Absolut! Sie können eine kostenlose Testversion herunterladen unter[Hier](https://releases.aspose.com/).

### Wie erhalte ich Unterstützung für Aspose.Words?
Sie können Unterstützung erhalten, indem Sie die besuchen[Aspose.Words-Forum](https://forum.aspose.com/c/words/8).

### Kann ich die Formatierung des eingefügten Dokuments beibehalten?
 Ja das`NodeImporter`Mit der Klasse können Sie angeben, wie die Formatierung beim Importieren von Knoten aus einem Dokument in ein anderes gehandhabt wird.