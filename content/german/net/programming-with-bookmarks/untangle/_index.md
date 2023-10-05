---
title: In Word-Dokument entwirren
linktitle: In Word-Dokument entwirren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET in Word-Dokumenten verschachtelte Lesezeichen in benachbarten Tabellenzeilen entwirren.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/untangle/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Untangle-Funktion in der Aspose.Words für .NET-Bibliothek verwendet wird. Diese Funktion entwirrt verschachtelte Lesezeichen, die sich in benachbarten Tabellenzeilen befinden.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Dokumentlesezeichen durchsuchen

Wir verwenden eine foreach-Schleife, um alle im Dokument vorhandenen Lesezeichen zu durchlaufen:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Code zum Umgang mit Lesezeichen finden Sie hier
}
```

## Schritt 2: Übergeordnete Zeilen aus Lesezeichen abrufen

 Wir benutzen das`GetAncestor` Methoden zum Abrufen der übergeordneten Zeilen der Start- und Endknoten des Lesezeichens:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Schritt 3: Verschachtelte Lesezeichen entwirren

Wenn beide übergeordneten Zeilen gefunden werden und das Lesezeichen in benachbarten Zeilen beginnt und endet, verschieben wir den Endknoten des Lesezeichens an das Ende des letzten Absatzes der letzten Zelle in der oberen Zeile:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Beispielquellcode für Untangle mit Aspose.Words für .NET

Hier ist das vollständige Quellcodebeispiel zum Entwirren verschachtelter Lesezeichen mit Aspose.Words für .NET:

```csharp

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

```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Untangle-Funktion von Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um verschachtelte Lesezeichen in benachbarten Tabellenzeilen zu entwirren.

### FAQs

#### F: Funktioniert die Untangle-Funktion nur mit verschachtelten Lesezeichen in benachbarten Tabellenzeilen?

A: Ja, die Entwirrungsfunktion wurde speziell dafür entwickelt, verschachtelte Lesezeichen zu entwirren, die sich in benachbarten Tabellenzeilen befinden. Wenn sich die Lesezeichen nicht in benachbarten Zeilen befinden, ist diese Funktion nicht anwendbar.

#### F: Wie kann ich verschachtelte Lesezeichen in meinem Word-Dokument identifizieren?

A: Sie können verschachtelte Lesezeichen identifizieren, indem Sie die Lesezeichen im Dokument durchlaufen und prüfen, ob sich das Start-Lesezeichen und das End-Lesezeichen in benachbarten Tabellenzeilen befinden. Sie können den in diesem Artikel bereitgestellten Quellcode als Ausgangspunkt für die Implementierung dieser Funktionalität verwenden.

#### F: Ändert die Entschlüsselungsfunktion den Inhalt des Originaldokuments?

A: Ja, die Untangle-Funktion ändert das Originaldokument, indem sie den Endknoten des Lesezeichens an das Ende des letzten Absatzes der letzten Zelle in der obersten Zeile verschiebt. Stellen Sie sicher, dass Sie eine Sicherungskopie des Dokuments speichern, bevor Sie diese Funktion anwenden.

#### F: Wie kann ich verschachtelte Lesezeichen in anderen Dokumentelementtypen wie Abschnitten oder Absätzen entwirren?

A: Die in diesem Artikel vorgestellte Funktion „Untangle“ wurde speziell dafür entwickelt, verschachtelte Lesezeichen in benachbarten Tabellenzeilen zu entwirren. Wenn Sie verschachtelte Lesezeichen in anderen Dokumentelementen entwirren möchten, müssen Sie den Code entsprechend anpassen und geeignete Methoden verwenden, um auf die gewünschten Elemente zuzugreifen.

#### F: Gibt es andere Methoden, um verschachtelte Lesezeichen in einem Word-Dokument mithilfe von Aspose.Words für .NET zu entwirren?

 A: Die in diesem Artikel vorgestellte Methode ist eine gängige Methode zum Entwirren verschachtelter Lesezeichen in benachbarten Tabellenzeilen. Abhängig von den spezifischen Anforderungen Ihres Projekts kann es jedoch auch andere Ansätze oder Techniken geben. Sie können sich das ansehen[Aspose.Words für .NET-API-Referenzen](https://reference.aspose.com/words/net/) um die verfügbaren Funktionen weiter zu erkunden.