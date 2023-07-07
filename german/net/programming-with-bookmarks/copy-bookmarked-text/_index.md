---
title: Mit Lesezeichen versehenen Text kopieren
linktitle: Mit Lesezeichen versehenen Text kopieren
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Lesezeichentext aus einem Quelldokument in ein anderes Dokument kopieren.
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

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Lesezeichentext aus Aspose.Words für .NET kopieren“ verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um den Inhalt eines Lesezeichens von einem Quelldokument in ein anderes Dokument zu kopieren.