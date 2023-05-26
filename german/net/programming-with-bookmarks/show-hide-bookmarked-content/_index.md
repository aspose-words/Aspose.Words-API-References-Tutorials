---
title: Mit Lesezeichen versehene Inhalte anzeigen und ausblenden
linktitle: Mit Lesezeichen versehene Inhalte anzeigen und ausblenden
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Lesezeicheninhalte mit Aspose.Words für .NET ein- oder ausblenden.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Show Hide Bookmarked Content“ in der Aspose.Words for .NET-Bibliothek verwendet wird. Mit dieser Funktion können Sie den Inhalt eines Lesezeichens basierend auf einer bestimmten Bedingung beim Zusammenführen von Daten ein- oder ausblenden.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Lesezeichen erhalten

 Wir benutzen das`Bookmarks` Eigenschaft des Dokumentbereichs, um das spezifische Lesezeichen abzurufen, dessen Inhalt angezeigt oder ausgeblendet werden soll:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Schritt 2: Einfügen der Zusammenführungsfelder

 Wir verwenden einen Dokumenten-Builder`DocumentBuilder` um die erforderlichen Zusammenführungsfelder einzufügen. Diese Zusammenführungsfelder legen eine Bedingung fest, um den Inhalt des Lesezeichens je nach Wert anzuzeigen oder auszublenden`showHide` Variable:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Schritt 3: Lesezeicheninhalt verschieben

Wir durchlaufen den Inhalt des Lesezeichens und verschieben es so, dass es angezeigt wird

isse vor dem Lesezeichen. Dadurch wird das Ein- oder Ausblenden von Inhalten basierend auf der angegebenen Bedingung gesteuert:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## Schritt 4: Verschieben des restlichen Lesezeicheninhalts

Wir verschieben den Rest des Lesezeicheninhalts nach dem Lesezeichen und verwenden dabei den Endknoten des Lesezeichens als Einfügepunkt:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## Schritt 5: Durchführen der Zusammenführung

 Wir benutzen das`Execute` Methode des Dokuments`s `MailMerge` object to execute the merge using the bookmark name and the value of the `showHide`-Variable:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Beispielquellcode für „Show Hide Bookmarked Content“ mit Aspose.Words für .NET

Hier ist das vollständige Beispiel des Quellcodes, um das Ein- und Ausblenden von Lesezeicheninhalten mit Aspose.Words für .NET zu demonstrieren:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD bookmark}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Gemerkte Inhalte anzeigen und ausblenden“ von Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um den Inhalt eines Lesezeichens basierend auf einer bestimmten Bedingung beim Zusammenführen von Daten anzuzeigen oder auszublenden.