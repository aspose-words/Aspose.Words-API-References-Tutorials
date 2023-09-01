---
title: Mit Lesezeichen versehenen Text im Word-Dokument anhängen
linktitle: Mit Lesezeichen versehenen Text im Word-Dokument anhängen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Text aus einem Lesezeichen in ein Word-Dokument einfügen.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/append-bookmarked-text/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Append Bookmarked Text“ in der Aspose.Words for .NET-Bibliothek verwendet wird. Mit dieser Funktion können Sie den in einem bestimmten Lesezeichen eines Word-Dokuments enthaltenen Text zu einem anderen Dokument hinzufügen.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Absätze aus dem Lesezeichen abrufen

 Bevor wir mit dem Hinzufügen des Lesezeichentextes beginnen, müssen wir die Absätze abrufen, die den Anfang und das Ende des Lesezeichens enthalten. Dies kann durch Zugriff auf erfolgen`BookmarkStart` Und`BookmarkEnd` Eigenschaften des Lesezeichens:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Schritt 2: Überprüfen Sie die übergeordneten Absätze

Wir prüfen, ob der Anfangs- und der Endabsatz gültige Eltern haben, also wirklich zu einem Absatz gehören. Wenn nicht, generieren wir eine Ausnahme:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Schritt 3: Überprüfen Sie die übergeordneten Elemente der Absätze

Wir prüfen, ob der Anfangs- und der Endabsatz dasselbe übergeordnete Element haben. Wenn nicht, bedeutet das, dass die Absätze nicht im selben Abschnitt oder Dokument enthalten sind und wir eine Ausnahme auslösen:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Schritt 4: Absätze kopieren

Wir durchlaufen die Knoten (Absätze) vom Anfangsabsatz bis zum Endabsatz. Für jeden Knoten erstellen wir eine Kopie und importieren sie in den Kontext des Zieldokuments:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Beispielquellcode für „Append Bookmarked Text“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um das Hinzufügen von Text aus einem Lesezeichen mit Aspose.Words für .NET zu demonstrieren:

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

```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Append Bookmarked Text“ von Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung zum Abrufen von Absätzen aus einem Lesezeichen, zum Überprüfen der übergeordneten Elemente und zum Kopieren von Absätzen in ein anderes Dokument befolgt.

### FAQs zum Anhängen von mit Lesezeichen versehenem Text in Word-Dokumenten

#### F1: Was sind die Voraussetzungen, um die Funktion „Text mit Lesezeichen hinzufügen“ in Aspose.Words für .NET verwenden zu können?

A: Um die Funktion „Text mit Lesezeichen hinzufügen“ in Aspose.Words für .NET verwenden zu können, müssen Sie über Grundkenntnisse der C#-Sprache verfügen. Sie benötigen außerdem eine .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

#### F2: Wie erhalte ich die Absätze, die den Anfang und das Ende eines Lesezeichens in einem Word-Dokument enthalten?

A: Um die Absätze zu erhalten, die den Anfang und das Ende eines Lesezeichens in einem Word-Dokument enthalten, können Sie auf das zugreifen`BookmarkStart` Und`BookmarkEnd` Eigenschaften des Lesezeichens. Hier ist ein Beispielcode:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### F3: Was passiert, wenn die Anfangs- und Endabsätze keine gültigen übergeordneten Elemente haben?

A: Wenn die Anfangs- und Endabsätze keine gültigen übergeordneten Elemente haben, es sich also nicht um echte Absätze handelt, wird eine Ausnahme ausgelöst. Diese Situation kann derzeit nicht bewältigt werden.
