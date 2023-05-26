---
title: Lesezeichen ausblenden anzeigen
linktitle: Lesezeichen ausblenden anzeigen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein bestimmtes Lesezeichen in einem Dokument ein- oder ausblenden.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/show-hide-bookmarks/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Lesezeichen anzeigen und ausblenden“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie ein bestimmtes Lesezeichen in einem Dokument ein- oder ausblenden.

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