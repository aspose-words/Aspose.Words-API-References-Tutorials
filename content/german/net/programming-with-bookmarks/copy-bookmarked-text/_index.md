---
title: Mit Lesezeichen versehenen Text in Word-Dokument kopieren
linktitle: Mit Lesezeichen versehenen Text in Word-Dokument kopieren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Lesezeichentext in einem Word-Dokument in ein anderes Dokument kopieren.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/copy-bookmarked-text/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Text mit Lesezeichen kopieren“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie den Inhalt eines bestimmten Lesezeichens von einem Quelldokument in ein anderes Dokument kopieren.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Quelldokument laden

 Bevor wir den Lesezeichentext kopieren, müssen wir das Quelldokument in ein laden`Document` Objekt mithilfe des Dateipfads:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Schritt 2: Quell-Lesezeichen abrufen

 Wir benutzen das`Bookmarks` Eigenschaft des Quelldokumentbereichs, um das spezifische Lesezeichen abzurufen, das wir kopieren möchten:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Schritt 3: Erstellen des Zieldokuments

Wir erstellen ein neues Dokument, das als Zieldokument zum Kopieren des Lesezeicheninhalts dient:

```csharp
Document dstDoc = new Document();
```

## Schritt 4: Angeben des Kopierspeicherorts

Wir geben den Ort an, an dem wir den kopierten Text hinzufügen möchten. In unserem Beispiel fügen wir den Text am Ende des Hauptteils des letzten Abschnitts des Zieldokuments hinzu:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Schritt 5: Lesezeichentext importieren und kopieren

 Wir benutzen ein`NodeImporter`Objekt zum Importieren und Kopieren von Lesezeichentext aus einem Quelldokument in das Zieldokument:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Beispielquellcode für das Kopieren von mit Lesezeichen versehenem Text mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um das Kopieren von Text aus einem Lesezeichen mit Aspose.Words für .NET zu demonstrieren:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Dies ist das Lesezeichen, dessen Inhalt wir kopieren möchten.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Wir werden dieses Dokument ergänzen.
	Document dstDoc = new Document();

	// Nehmen wir an, wir werden am Ende des Hauptteils des letzten Abschnitts angehängt.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Wenn Sie mehrmals ohne einen einzigen Kontext importieren, werden viele Stile erstellt.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### AppendBookmarkedText-Quellcode

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
            // Dies ist der Absatz, der den Anfang des Lesezeichens enthält.
            Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

            // Dies ist der Absatz, der das Ende des Lesezeichens enthält.
            Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

            if (startPara == null || endPara == null)
                throw new InvalidOperationException(
                    "Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

            // Beschränken wir uns auf ein einigermaßen einfaches Szenario.
            if (startPara.ParentNode != endPara.ParentNode)
                throw new InvalidOperationException(
                    "Start and end paragraphs have different parents, cannot handle this scenario yet.");

            // Wir möchten alle Absätze vom Anfangsabsatz bis zum Endabsatz (einschließlich) kopieren.
            // Daher ist der Knoten, an dem wir aufhören, einer nach dem letzten Absatz.
            Node endNode = endPara.NextSibling;

            for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
            {
                //Dadurch wird eine Kopie des aktuellen Knotens erstellt und in den Kontext importiert (gültig gemacht).
                // des Zieldokuments. Importieren bedeutet, Stile und Listenkennungen korrekt anzupassen.
                Node newNode = importer.ImportNode(curNode, true);

                dstNode.AppendChild(newNode);
            }
        }

```
## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Lesezeichentext aus Aspose.Words für .NET kopieren“ verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um den Inhalt eines Lesezeichens von einem Quelldokument in ein anderes Dokument zu kopieren.

### FAQs zum Kopieren von mit Lesezeichen versehenem Text in ein Word-Dokument

#### F: Was sind die Voraussetzungen, um die Funktion „Text mit Lesezeichen kopieren“ in Aspose.Words für .NET zu verwenden?

A: Um die Funktion „Text mit Lesezeichen kopieren“ in Aspose.Words für .NET verwenden zu können, müssen Sie über Grundkenntnisse der C#-Sprache verfügen. Sie benötigen außerdem eine .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

#### F: Wie lade ich ein Quelldokument in Aspose.Words für .NET?

 A: Um ein Quelldokument in Aspose.Words für .NET zu laden, können Sie das verwenden`Document` Klasse durch Angabe des Dateipfads des Dokuments. Hier ist ein Beispielcode:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### F: Wie erhalte ich mit Aspose.Words für .NET den Inhalt eines bestimmten Lesezeichens in einem Quelldokument?

 A: Um den Inhalt eines bestimmten Lesezeichens in einem Quelldokument mit Aspose.Words für .NET abzurufen, können Sie auf das zugreifen`Bookmarks` Eigenschaft des Quelldokumentbereichs und verwenden Sie den Lesezeichennamen, um das spezifische Lesezeichen abzurufen. Hier ist ein Beispielcode:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### F: Wie kann ich mit Aspose.Words für .NET den Speicherort der Lesezeichentextkopie in einem Zieldokument angeben?

 A: Um anzugeben, wo Sie mit Aspose.Words für .NET kopierten Lesezeichentext in einem Zieldokument hinzufügen möchten, können Sie zum Hauptteil des letzten Abschnitts des Zieldokuments navigieren. Du kannst den ... benutzen`LastSection` Eigenschaft für den Zugriff auf den letzten Abschnitt und die`Body` -Eigenschaft, um auf den Hauptteil dieses Abschnitts zuzugreifen. Hier ist ein Beispielcode:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### F: Wie importiere und kopiere ich Lesezeichentext aus dem Quelldokument in das Zieldokument mit Aspose.Words für .NET?

 A: Um mit Aspose.Words für .NET Lesezeichentext aus einem Quelldokument in ein Zieldokument zu importieren und zu kopieren, können Sie Folgendes verwenden`NodeImporter` Klasse, die das Quelldokument, das Zieldokument und den beizubehaltenden Formatierungsmodus angibt. Dann können Sie das verwenden`AppendBookmarkedText` Methode zum Hinzufügen des Lesezeichentexts zum Zieldokument. Hier ist ein Beispielcode:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### F: Wie speichere ich ein Zieldokument, nachdem ich Lesezeichentext mit Aspose.Words für .NET kopiert habe?

A: Um ein Zieldokument zu speichern, nachdem Sie mit Aspose.Words für .NET Text aus einem Lesezeichen kopiert haben, können Sie Folgendes verwenden`Save` Methode der`Document` Objekt, das den Zieldateipfad angibt. Hier ist ein Beispielcode:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```