---
title: Mit Lesezeichen versehenen Text im Word-Dokument anhängen
linktitle: Mit Lesezeichen versehenen Text im Word-Dokument anhängen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET mit Lesezeichen versehenen Text in ein Word-Dokument einfügen. Perfekt für Entwickler.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/append-bookmarked-text/
---
## Einführung

Hallo! Haben Sie schon einmal versucht, Text aus einem mit Lesezeichen versehenen Abschnitt in einem Word-Dokument anzuhängen, und fanden es schwierig? Sie haben Glück! Dieses Tutorial führt Sie mit Aspose.Words für .NET durch den Vorgang. Wir unterteilen es in einfache Schritte, damit Sie es leicht nachvollziehen können. Lassen Sie uns loslegen und den mit Lesezeichen versehenen Text wie ein Profi anhängen!

## Voraussetzungen

Bevor wir beginnen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:

-  Aspose.Words für .NET: Stellen Sie sicher, dass Sie es installiert haben. Wenn nicht, können Sie[Laden Sie es hier herunter](https://releases.aspose.com/words/net/).
- Entwicklungsumgebung: Jede .NET-Entwicklungsumgebung wie Visual Studio.
- Grundkenntnisse in C#: Das Verständnis der grundlegenden C#-Programmierkonzepte ist hilfreich.
- Word-Dokument mit Lesezeichen: Ein Word-Dokument mit eingerichteten Lesezeichen, aus denen wir Text anhängen.

## Namespaces importieren

Als Erstes importieren wir die erforderlichen Namespaces. So stellen wir sicher, dass wir alle erforderlichen Tools zur Hand haben.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Importing;
```

Lassen Sie uns das Beispiel in detaillierte Schritte aufteilen.

## Schritt 1: Laden Sie das Dokument und initialisieren Sie die Variablen

Okay, beginnen wir mit dem Laden unseres Word-Dokuments und dem Initialisieren der benötigten Variablen.

```csharp
// Laden Sie die Quell- und Zieldokumente.
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");

// Initialisieren Sie den Dokumentimporter.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

// Suchen Sie das Lesezeichen im Quelldokument.
Bookmark srcBookmark = srcDoc.Range.Bookmarks["YourBookmarkName"];
```

## Schritt 2: Identifizieren Sie die Anfangs- und Endabsätze

Suchen wir nun die Absätze, in denen das Lesezeichen beginnt und endet. Dies ist wichtig, da wir den Text innerhalb dieser Grenzen verarbeiten müssen.

```csharp
// Dies ist der Absatz, der den Anfang des Lesezeichens enthält.
Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;

// Dies ist der Absatz, der das Ende des Lesezeichens enthält.
Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

if (startPara == null || endPara == null)
    throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");
```

## Schritt 3: Überprüfen Sie die übergeordneten Absätze

Wir müssen sicherstellen, dass Anfangs- und Endabsatz denselben übergeordneten Absatz haben. Dies ist ein einfaches Szenario, um die Dinge unkompliziert zu halten.

```csharp
// Beschränken wir uns auf ein einigermaßen einfaches Szenario.
if (startPara.ParentNode != endPara.ParentNode)
    throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");
```

## Schritt 4: Identifizieren des zu stoppenden Knotens

Als Nächstes müssen wir den Knoten bestimmen, an dem wir mit dem Kopieren des Textes aufhören. Dies ist der Knoten unmittelbar nach dem letzten Absatz.

```csharp
// Wir wollen alle Absätze vom Anfangsabsatz bis einschließlich zum Endabsatz kopieren,
// Daher ist der Knoten, bei dem wir aufhören, einer nach dem Endabsatz.
Node endNode = endPara.NextSibling;
```

## Schritt 5: Mit Lesezeichen versehenen Text an Zieldokument anhängen

Lassen Sie uns abschließend die Knoten vom Startabsatz bis zum Knoten nach dem Endabsatz durchlaufen und sie an das Zieldokument anhängen.

```csharp
for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
    // Dadurch wird eine Kopie des aktuellen Knotens erstellt und in den Kontext importiert (gültig gemacht).
    // des Zieldokuments. Beim Importieren werden Stile und Listenkennungen richtig angepasst.
    Node newNode = importer.ImportNode(curNode, true);

    // Hängen Sie den importierten Knoten an das Zieldokument an.
    dstDoc.FirstSection.Body.AppendChild(newNode);
}

// Speichern Sie das Zieldokument mit dem angehängten Text.
dstDoc.Save("appended_document.docx");
```

## Abschluss

Und da haben Sie es! Sie haben erfolgreich Text aus einem mit Lesezeichen versehenen Abschnitt in einem Word-Dokument mithilfe von Aspose.Words für .NET angehängt. Dieses leistungsstarke Tool macht die Dokumentbearbeitung zum Kinderspiel, und jetzt haben Sie noch einen weiteren Trick im Ärmel. Viel Spaß beim Programmieren!

## Häufig gestellte Fragen

### Kann ich Text aus mehreren Lesezeichen auf einmal anhängen?
Ja, Sie können den Vorgang für jedes Lesezeichen wiederholen und den Text entsprechend anhängen.

### Was passiert, wenn Anfangs- und Endabsatz unterschiedliche übergeordnete Elemente haben?
Im vorliegenden Beispiel wird davon ausgegangen, dass sie denselben übergeordneten Knoten haben. Bei unterschiedlichen übergeordneten Knoten ist eine komplexere Handhabung erforderlich.

### Kann ich die ursprüngliche Formatierung des angehängten Textes beibehalten?
 Absolut! Die`ImportFormatMode.KeepSourceFormatting` stellt sicher, dass die ursprüngliche Formatierung erhalten bleibt.

### Ist es möglich, Text an einer bestimmten Stelle im Zieldokument anzuhängen?
Ja, Sie können den Text an jeder beliebigen Stelle anfügen, indem Sie zum gewünschten Knoten im Zieldokument navigieren.

### Was ist, wenn ich Text aus einem Lesezeichen an einen neuen Abschnitt anhängen muss?
Sie können im Zieldokument einen neuen Abschnitt erstellen und den Text dort anhängen.