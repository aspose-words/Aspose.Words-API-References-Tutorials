---
title: Mit Lesezeichen versehenen Text im Word-Dokument anhängen
linktitle: Mit Lesezeichen versehenen Text im Word-Dokument anhängen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Text aus einem Lesezeichen in ein Word-Dokument einfügen.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/append-bookmarked-text/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Lesezeichentext anhängen“ in der Aspose.Words-Bibliothek für .NET verwendet wird. Mit dieser Funktion können Sie den in einem bestimmten Lesezeichen eines Word-Dokuments enthaltenen Text zu einem anderen Dokument hinzufügen.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Absätze aus Lesezeichen abrufen

 Bevor wir mit dem Hinzufügen des Lesezeichentextes beginnen, müssen wir die Absätze abrufen, die den Anfang und das Ende des Lesezeichens enthalten. Dies können Sie tun, indem Sie auf`BookmarkStart` Und`BookmarkEnd` Eigenschaften des Lesezeichens:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Schritt 2: Übergeordnete Absätze prüfen

Wir prüfen, ob Anfangs- und Endabsatz gültige übergeordnete Elemente haben, also wirklich zu einem Absatz gehören. Wenn nicht, erzeugen wir eine Exception:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Schritt 3: Übergeordnete Absätze prüfen

Wir prüfen, ob Anfangs- und Endabsatz denselben übergeordneten Absatz haben. Wenn nicht, bedeutet das, dass die Absätze nicht im selben Abschnitt oder Dokument enthalten sind, und wir werfen eine Ausnahme:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Schritt 4: Absätze kopieren

Wir durchlaufen die Knoten (Absätze) vom Anfangsabsatz bis zum Endabsatz. Für jeden Knoten erstellen wir eine Kopie und importieren diese in den Kontext des Zieldokuments:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Beispielquellcode zum Anhängen von mit Lesezeichen versehenem Text mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, der das Hinzufügen von Text aus einem Lesezeichen mit Aspose.Words für .NET demonstriert:

```csharp

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

	// Wir wollen alle Absätze vom Anfangsabsatz bis einschließlich zum Endabsatz kopieren,
	// Daher ist der Knoten, bei dem wir aufhören, einer nach dem Endabsatz.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//Dadurch wird eine Kopie des aktuellen Knotens erstellt und in den Kontext importiert (gültig gemacht).
		// des Zieldokuments. Beim Importieren werden Stile und Listenkennungen richtig angepasst.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Lesezeichentext anhängen“ von Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um Absätze aus einem Lesezeichen abzurufen, übergeordnete Elemente zu überprüfen und Absätze in ein anderes Dokument zu kopieren.

### FAQs zum Anhängen von mit Lesezeichen versehenem Text in Word-Dokument

#### F1: Was sind die Voraussetzungen für die Verwendung der Funktion „Text mit Lesezeichen hinzufügen“ in Aspose.Words für .NET?

A: Um die Funktion „Text mit Lesezeichen hinzufügen“ in Aspose.Words für .NET zu verwenden, benötigen Sie Grundkenntnisse der Sprache C#. Sie benötigen außerdem eine .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

#### F2: Wie erhalte ich die Absätze, die den Anfang und das Ende eines Lesezeichens in einem Word-Dokument enthalten?

A: Um die Absätze zu erhalten, die den Anfang und das Ende eines Lesezeichens in einem Word-Dokument enthalten, können Sie auf die`BookmarkStart` Und`BookmarkEnd` Eigenschaften des Lesezeichens. Hier ist ein Beispielcode:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### F3: Was passiert, wenn die Anfangs- und Endabsätze keine gültigen übergeordneten Absätze haben?

A: Wenn die Anfangs- und Endabsätze keine gültigen übergeordneten Absätze haben, also keine echten Absätze sind, wird eine Ausnahme ausgelöst. Diese Situation kann derzeit nicht verwaltet werden.
