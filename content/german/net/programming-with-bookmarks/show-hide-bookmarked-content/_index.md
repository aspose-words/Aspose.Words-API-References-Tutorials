---
title: Mit Lesezeichen versehene Inhalte im Word-Dokument ausblenden anzeigen
linktitle: Mit Lesezeichen versehene Inhalte im Word-Dokument ausblenden anzeigen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Lesezeicheninhalte in Word-Dokumenten ein- oder ausblenden.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Show Hide Bookmarked Content“ in der Aspose.Words for .NET-Bibliothek verwendet wird. Mit dieser Funktion können Sie den Inhalt eines Lesezeichens in einem Word-Dokument basierend auf einer bestimmten Bedingung beim Zusammenführen von Daten ein- oder ausblenden.

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

### FAQs zum Anzeigen und Ausblenden von mit Lesezeichen versehenen Inhalten in Word-Dokumenten

#### F: Kann ich dieselbe Bedingung für mehrere Lesezeichen im selben Dokument verwenden?

A: Ja, Sie können dieselbe Bedingung für mehrere Lesezeichen im selben Dokument verwenden. Wiederholen Sie einfach die Schritte 2 bis 5 für jedes Lesezeichen und passen Sie den Lesezeichennamen und optional den Wert des Lesezeichens an`showhide` je nach Bedarf variabel.

#### F: Wie kann ich weitere Bedingungen hinzufügen, um Lesezeicheninhalte anzuzeigen oder auszublenden?

 A: Um weitere Bedingungen hinzuzufügen, können Sie logische Operatoren verwenden, z`AND` Und`OR` im Code zum Einfügen der Zusammenführungsfelder in Schritt 2. Bearbeiten Sie die Bedingung im folgenden Code, um zusätzliche Bedingungen hinzuzufügen:

```csharp
builder. Write("\" = \"true\" ");
```

#### F: Wie kann ich mit Aspose.Words für .NET ein Lesezeichen in einem Word-Dokument löschen?

 A: Um ein Lesezeichen in einem Word-Dokument mit Aspose.Words für .NET zu entfernen, können Sie das verwenden`Remove` Methode aus der`Bookmarks` Sammlung des Dokumentenbereichs. Hier ist ein Beispielcode zum Löschen eines bestimmten Lesezeichens:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### F: Ist die Aspose.Words-Bibliothek kostenlos?

 A: Die Aspose.Words-Bibliothek ist eine kommerzielle Bibliothek und erfordert eine gültige Lizenz zur Verwendung in Ihren Projekten. Du kannst nachschauen[Aspose.Words für .NET-API-Referenzen](https://reference.aspose.com/words/net/) um mehr über Lizenzoptionen und Preise zu erfahren.

#### F: Gibt es andere Bibliotheken für die Textverarbeitung mit Word-Dokumenten in .NET?

A: Ja, es stehen andere Bibliotheken für die Textverarbeitung mit Word-Dokumenten in .NET zur Verfügung, z. B. Open XML SDK und GemBox.Document. Sie können diese Bibliotheken je nach Ihren spezifischen Anforderungen und Vorlieben als Alternativen zu Aspose.Words erkunden.