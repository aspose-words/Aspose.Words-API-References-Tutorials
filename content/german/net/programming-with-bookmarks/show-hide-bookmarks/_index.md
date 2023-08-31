---
title: Lesezeichen im Word-Dokument ausblenden anzeigen
linktitle: Lesezeichen im Word-Dokument ausblenden anzeigen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein bestimmtes Lesezeichen in einem Word-Dokument ein- oder ausblenden.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/show-hide-bookmarks/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Lesezeichen anzeigen und ausblenden“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie ein bestimmtes Lesezeichen in einem Word-Dokument ein- oder ausblenden.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Laden des Dokuments

 Wir benutzen das`Document` Klasse zum Laden des vorhandenen Dokuments aus einer Datei:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Schritt 2: Ein bestimmtes Lesezeichen ein- oder ausblenden

 Wir benutzen das`ShowHideBookmarkedContent` Funktion zum Ein- oder Ausblenden eines bestimmten Lesezeichens im Dokument. Diese Funktion verwendet als Parameter das Dokument, den Namen des Lesezeichens und einen booleschen Wert, der angibt, ob das Lesezeichen angezeigt oder ausgeblendet werden soll:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Schritt 3: Speichern des geänderten Dokuments

 Wir benutzen das`Save` Methode zum Speichern des geänderten Dokuments in einer Datei:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Beispielquellcode für „Lesezeichen anzeigen und ausblenden“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um das Ein- und Ausblenden eines bestimmten Lesezeichens mit Aspose.Words für .NET zu demonstrieren:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Lesezeichen anzeigen und ausblenden“ von Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um ein bestimmtes Lesezeichen in einem Dokument ein- oder auszublenden.

### FAQs zum Anzeigen und Ausblenden von Lesezeichen in Word-Dokumenten

#### F: Kann ich mehrere Lesezeichen im selben Dokument ein- oder ausblenden?

A: Ja, Sie können mehrere Lesezeichen im selben Dokument ein- oder ausblenden, indem Sie die Schritte 2 und 3 für jedes Lesezeichen wiederholen, das Sie verarbeiten möchten.

#### F: Funktioniert der bereitgestellte Code mit anderen Word-Dokumentformaten wie .doc oder .docm?

A: Ja, der bereitgestellte Code funktioniert mit verschiedenen Word-Dokumentformaten, die von Aspose.Words unterstützt werden, wie z. B. .doc und .docm. Achten Sie nur darauf, beim Laden und Speichern des Dokuments den richtigen Dateinamen und Pfad zu verwenden.

#### F: Wie kann ich ein ausgeblendetes Lesezeichen wieder anzeigen?

 A: Um ein ausgeblendetes Lesezeichen wieder anzuzeigen, müssen Sie dasselbe verwenden`ShowHideBookmarkedContent` Funktion, die den Wert übergibt`true`für den booleschen Parameter, der angibt, ob das Lesezeichen angezeigt oder ausgeblendet werden soll.

#### F: Kann ich Bedingungen verwenden, um Lesezeichen basierend auf Briefvorlagenfeldwerten im Dokument anzuzeigen oder auszublenden?

 A: Ja, Sie können Bedingungen und Werte von Zusammenführungsfeldern verwenden, um zu bestimmen, ob ein Lesezeichen angezeigt oder ausgeblendet werden soll. Sie können den Code des anpassen`ShowHideBookmarkedContent` Funktion, um die entsprechenden Bedingungen und Werte zu berücksichtigen.

#### F: Wie kann ich mit Aspose.Words für .NET ein Lesezeichen in einem Word-Dokument löschen?

A: Um ein Lesezeichen in einem Word-Dokument mit Aspose.Words für .NET zu entfernen, können Sie das verwenden`RemoveBookmarks` Methode der`Document`Klasse. Hier ist ein Beispielcode:

```csharp
doc.RemoveBookmarks("BookmarkName");
```