---
title: Zeile nach Lesezeichen löschen
linktitle: Zeile nach Lesezeichen löschen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabellenzeile basierend auf einem bestimmten Lesezeichen in einem Dokument löschen.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/delete-row-by-bookmark/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Zeile nach Lesezeichen löschen“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie eine Tabellenzeile basierend auf einem bestimmten Lesezeichen in einem Dokument löschen.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Lesezeichen erhalten

 Wir benutzen das`Bookmarks`Eigenschaft des Dokumentbereichs, um das spezifische Lesezeichen abzurufen, das wir zum Löschen der Tabellenzeile verwenden möchten:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Schritt 2: Tabellenzeile löschen

 Wir benutzen das`GetAncestor` Methode, um die zu erhalten`Row` Geben Sie das übergeordnete Element des Lesezeichens ein. Als nächstes verwenden wir die`Remove` Methode zum Entfernen der Tabellenzeile:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Beispielquellcode für „Zeile nach Lesezeichen löschen“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um das Löschen einer Tabellenzeile basierend auf einem bestimmten Lesezeichen mit Aspose.Words für .NET zu demonstrieren:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Zeile nach Lesezeichen löschen“ von Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung zum Löschen einer Tabellenzeile basierend auf einem bestimmten Lesezeichen in einem Dokument befolgt.