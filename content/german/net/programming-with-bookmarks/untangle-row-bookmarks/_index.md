---
title: Zeilenlesezeichen im Word-Dokument entwirren
linktitle: Zeilenlesezeichen im Word-Dokument entwirren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie verschachtelte Zeilenlesezeichen in einem Word-Dokument entwirren, um bestimmte Zeilen zu entfernen, ohne andere Lesezeichen zu beeinträchtigen.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/untangle-row-bookmarks/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion Untangle Row Bookmarks in der Aspose.Words-Bibliothek für .NET verwendet wird. Diese Funktion ermöglicht es, die Enden von Zeilenlesezeichen in dieselbe Zeile wie die Anfänge der Lesezeichen zu setzen.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Dokument einlegen

 Wir benutzen das`Document` Klasse zum Laden des vorhandenen Dokuments aus einer Datei:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Schritt 2: Zeilenlesezeichen entwirren

 Wir benutzen das`Untangle` Funktion zum Entwirren von Lesezeichen aus Zeilen. Diese Funktion führt die benutzerdefinierte Aufgabe aus, die Lesezeichenenden von Zeilen in dieselbe Zeile zu setzen, in der das Lesezeichen beginnt:

```csharp
Untangle(doc);
```

## Schritt 3: Zeile per Lesezeichen löschen

 Wir benutzen das`DeleteRowByBookmark` Funktion zum Löschen einer bestimmten Zeile anhand ihres Lesezeichens:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Schritt 4: Integrität anderer Lesezeichen prüfen

Wir überprüfen, ob die anderen Lesezeichen nicht beschädigt wurden, indem wir prüfen, ob das Ende des Lesezeichens noch vorhanden ist:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Beispielquellcode für Untangle Row Bookmarks mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zum Entwirren von Lesezeichen aus Zeilen mit Aspose.Words für .NET:


```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Dadurch wird die benutzerdefinierte Aufgabe ausgeführt, die Zeilenenden des Lesezeichens in dieselbe Zeile wie die Anfänge des Lesezeichens einzufügen.
	Untangle(doc);

	// Jetzt können wir problemlos Zeilen anhand eines Lesezeichens löschen, ohne die Lesezeichen anderer Zeilen zu beschädigen.
	DeleteRowByBookmark(doc, "ROW2");

	// Dies dient nur zur Überprüfung, dass das andere Lesezeichen nicht beschädigt wurde.
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
                // Holen Sie sich die übergeordnete Zeile des Lesezeichens und des Lesezeichen-Endknotens.
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                // Wenn beide Zeilen in Ordnung sind und der Anfang und das Ende des Lesezeichens in benachbarten Zeilen liegen,
                // Verschieben Sie den Lesezeichen-Endknoten an das Ende des letzten Absatzes in der letzten Zelle der obersten Zeile.
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

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Zeilenlesezeichen entwirren“ von Aspose.Words für .NET verwendet wird. Wir sind einer Schritt-für-Schritt-Anleitung gefolgt, um Zeilenlesezeichen zu entwirren und eine bestimmte Zeile zu löschen, ohne andere Lesezeichen zu beschädigen.

### FAQs zum Entwirren von Zeilenlesezeichen in Word-Dokumenten

#### F: Funktioniert „Zeilenlesezeichen entschlüsseln“ nur mit Zeilenlesezeichen in Tabellen?

A: Ja, die Funktion „Zeilenlesezeichen entwirren“ ist speziell dafür gedacht, Zeilenlesezeichen in Tabellen zu entwirren. Mit dieser Funktion können Zeilenlesezeichen in Arrays verarbeitet werden und sichergestellt werden, dass die Lesezeichenenden in derselben Zeile stehen wie die Lesezeichenanfänge.

#### F: Ändert die Funktion „Zeilenlesezeichen entschlüsseln“ den Inhalt des Originaldokuments?

A: Ja, die Funktion Zeilenlesezeichen entschlüsseln ändert das Originaldokument, indem sie die Enden der Zeilenlesezeichen so verschiebt, dass sie in derselben Zeile wie deren Anfänge stehen. Stellen Sie sicher, dass Sie eine Sicherungskopie des Dokuments speichern, bevor Sie diese Funktion anwenden.

#### F: Wie kann ich Zeilenlesezeichen in meinem Word-Dokument identifizieren?

A: Zeilenlesezeichen werden normalerweise in Tabellen verwendet, um bestimmte Abschnitte zu markieren. Sie können Zeilenlesezeichen identifizieren, indem Sie die Lesezeichen im Dokument durchsuchen und prüfen, ob sich die Lesezeichen in Tabellenzeilen befinden.

#### F: Ist es möglich, Zeilenlesezeichen in nicht benachbarten Tabellen zu entwirren?

A: Die in diesem Artikel vorgestellte Funktion „Zeilenlesezeichen entwirren“ ist dazu gedacht, Zeilenlesezeichen in benachbarten Tabellen zu entwirren. Um Zeilenlesezeichen in nicht benachbarten Tabellen zu entwirren, können je nach Struktur des Dokuments zusätzliche Anpassungen am Code erforderlich sein.

#### F: Welche anderen Manipulationen kann ich an Zeilenlesezeichen durchführen, nachdem sie aufgelöst wurden?

A: Sobald die Zeilenlesezeichen aufgelöst sind, können Sie je nach Bedarf verschiedene Manipulationen durchführen. Dazu können das Bearbeiten, Löschen oder Hinzufügen von Inhalt zu mit Lesezeichen versehenen Zeilen gehören. Gehen Sie mit Zeilenlesezeichen vorsichtig um, um unerwünschte Auswirkungen auf den Rest des Dokuments zu vermeiden.