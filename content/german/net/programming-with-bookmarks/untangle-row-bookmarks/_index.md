---
title: Zeilenlesezeichen im Word-Dokument entwirren
linktitle: Zeilenlesezeichen im Word-Dokument entwirren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie verschachtelte Zeilenlesezeichen in einem Word-Dokument entwirren, um bestimmte Zeilen zu entfernen, ohne dass sich dies auf andere Lesezeichen auswirkt.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/untangle-row-bookmarks/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Zeilenlesezeichen entwirren“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Diese Funktion ermöglicht es, die Enden von Lesezeichen von Zeilen in die gleiche Zeile wie die Anfänge von Lesezeichen zu setzen.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Laden des Dokuments

 Wir benutzen das`Document` Klasse zum Laden des vorhandenen Dokuments aus einer Datei:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Schritt 2: Linien-Lesezeichen entwirren

 Wir benutzen das`Untangle` Funktion zum Entwirren von Lesezeichen aus Zeilen. Diese Funktion führt die benutzerdefinierte Aufgabe aus, die Enden der Lesezeichenzeilen in derselben Zeile zu platzieren, in der das Lesezeichen beginnt:

```csharp
Untangle(doc);
```

## Schritt 3: Zeile per Lesezeichen löschen

 Wir benutzen das`DeleteRowByBookmark` Funktion zum Löschen einer bestimmten Zeile anhand ihres Lesezeichens:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Schritt 4: Überprüfen Sie die Integrität anderer Lesezeichen

Wir stellen sicher, dass die anderen Lesezeichen nicht beschädigt wurden, indem wir prüfen, ob das Ende des Lesezeichens noch vorhanden ist:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Beispielquellcode für Untangle Row Bookmarks mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zum Entwirren von Lesezeichen aus Zeilen mithilfe von Aspose.Words für .NET:


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Dadurch wird die benutzerdefinierte Aufgabe ausgeführt, die Enden der Zeilenlesezeichen in derselben Zeile wie die Lesezeichenanfänge zu platzieren.
	Untangle(doc);

	// Jetzt können wir ganz einfach Zeilen mit einem Lesezeichen löschen, ohne die Lesezeichen einer anderen Zeile zu beschädigen.
	DeleteRowByBookmark(doc, "ROW2");

	// Dies dient lediglich der Überprüfung, ob das andere Lesezeichen nicht beschädigt wurde.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### Quellcode entwirren
```csharp

private void Untangle(Document doc)
        {
            foreach (Bookmark bookmark in doc.Range.Bookmarks)
            {
                // Rufen Sie die übergeordnete Zeile sowohl des Lesezeichens als auch des Lesezeichen-Endknotens ab.
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                // Wenn beide Zeilen in Ordnung sind und der Anfang und das Ende des Lesezeichens in benachbarten Zeilen enthalten sind,
                // Verschieben Sie den Endknoten des Lesezeichens an das Ende des letzten Absatzes in der letzten Zelle der oberen Zeile.
                if (row1 != null && row2 != null && row1.NextSibling == row2)
                    row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
            }
        }

```

#### DeleteRowByBookmark-Quellcode
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Zeilenlesezeichen entwirren“ von Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um Zeilenlesezeichen zu entwirren und eine bestimmte Zeile zu löschen, ohne andere Lesezeichen zu beschädigen.

### FAQs zum Entwirren von Zeilenlesezeichen in Word-Dokumenten

#### F: Funktioniert „Zeilenlesezeichen entschlüsseln“ nur mit Zeilenlesezeichen in Tabellen?

A: Ja, die Funktion „Zeilenlesezeichen entwirren“ wurde speziell zum Entwirren von Zeilenlesezeichen in Tabellen entwickelt. Mit dieser Funktion können Zeilenlesezeichen in Arrays verarbeitet und sichergestellt werden, dass sich die Enden der Lesezeichen in derselben Zeile wie die Anfänge der Lesezeichen befinden.

#### F: Ändert die Funktion „Zeilenlesezeichen entschlüsseln“ den Inhalt des Originaldokuments?

A: Ja, die Funktion „Zeilenlesezeichen entschlüsseln“ ändert das Originaldokument, indem sie die Enden der Zeilenlesezeichen verschiebt, um sie in derselben Zeile wie die Anfänge der Lesezeichen zu platzieren. Stellen Sie sicher, dass Sie eine Sicherungskopie des Dokuments speichern, bevor Sie diese Funktion anwenden.

#### F: Wie kann ich Zeilenlesezeichen in meinem Word-Dokument identifizieren?

A: Zeilenlesezeichen werden normalerweise in Tabellen verwendet, um bestimmte Abschnitte zu markieren. Sie können Zeilenlesezeichen identifizieren, indem Sie die Lesezeichen im Dokument durchsuchen und prüfen, ob sich die Lesezeichen in Tabellenzeilen befinden.

#### F: Ist es möglich, Zeilenlesezeichen in nicht benachbarten Tabellen zu entwirren?

A: Die in diesem Artikel vorgestellte Funktion „Zeilenlesezeichen entwirren“ dient dazu, Zeilenlesezeichen in benachbarten Tabellen zu entwirren. Um Zeilenlesezeichen in nicht benachbarten Tabellen zu entwirren, können je nach Struktur des Dokuments zusätzliche Anpassungen am Code erforderlich sein.

#### F: Welche anderen Manipulationen kann ich an Zeilenlesezeichen vornehmen, nachdem sie entschlüsselt wurden?

A: Sobald die Zeilen-Lesezeichen entschlüsselt sind, können Sie je nach Bedarf verschiedene Manipulationen durchführen. Dies kann das Bearbeiten, Löschen oder Hinzufügen von Inhalten zu mit Lesezeichen versehenen Zeilen umfassen. Gehen Sie mit Zeilenlesezeichen vorsichtig um, um unerwünschte Auswirkungen auf den Rest des Dokuments zu vermeiden.