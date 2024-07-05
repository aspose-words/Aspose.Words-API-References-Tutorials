---
title: Zeile nach Lesezeichen im Word-Dokument löschen
linktitle: Zeile nach Lesezeichen im Word-Dokument löschen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabellenzeile basierend auf einem bestimmten Lesezeichen in einem Word-Dokument löschen.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/delete-row-by-bookmark/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Zeile nach Lesezeichen löschen“ in der Aspose.Words-Bibliothek für .NET verwendet wird. Mit dieser Funktion können Sie eine Tabellenzeile basierend auf einem bestimmten Lesezeichen im Word-Dokument löschen.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Das Lesezeichen erhalten

 Wir benutzen das`Bookmarks` -Eigenschaft des Dokumentbereichs, um das spezifische Lesezeichen abzurufen, das wir zum Löschen der Tabellenzeile verwenden möchten:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Schritt 2: Tabellenzeile löschen

 Wir benutzen das`GetAncestor` Methode zum Erhalten der`Row` Typ übergeordnetes Element des Lesezeichens. Als nächstes verwenden wir die`Remove` Methode zum Entfernen der Tabellenzeile:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Beispielquellcode für „Zeile nach Lesezeichen löschen“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, der das Löschen einer Tabellenzeile basierend auf einem bestimmten Lesezeichen mit Aspose.Words für .NET demonstriert:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Zeile nach Lesezeichen löschen“ von Aspose.Words für .NET verwendet wird. Wir sind einer Schritt-für-Schritt-Anleitung gefolgt, um eine Tabellenzeile basierend auf einem bestimmten Lesezeichen in einem Dokument zu löschen.

### FAQs zum Löschen von Zeilen nach Lesezeichen in Word-Dokumenten

#### F: Kann ich mit demselben Lesezeichen mehrere Zeilen löschen?

A: Ja, Sie können mehrere Zeilen mit demselben Lesezeichen löschen. Sie müssen jedoch die Logik in Ihrem Code bearbeiten, um die Anzahl der zu löschenden Zeilen zu bestimmen und die erforderlichen Anpassungen am bereitgestellten Codeausschnitt vorzunehmen.

#### F: Was passiert, wenn das Lesezeichen im Dokument nicht vorhanden ist?

A: Wenn das angegebene Lesezeichen im Dokument nicht vorhanden ist, gibt der Codeausschnitt einen Nullwert für das Lesezeichenobjekt zurück. Daher müssen Sie dieses Szenario in Ihrem Code behandeln, indem Sie entsprechende Prüfungen hinzufügen, bevor Sie versuchen, die Tabellenzeile zu löschen.

#### F: Ist die Nutzung der Aspose.Words-Bibliothek kostenlos?

 A: Die Aspose.Words-Bibliothek ist eine kommerzielle Bibliothek und Sie benötigen möglicherweise eine gültige Lizenz, um sie in Ihren Projekten zu verwenden. Sie können die[Aspose.Words für .NET API-Referenzen](https://reference.aspose.com/words/net/) um mehr über ihre Lizenzoptionen und Preise zu erfahren.

#### F: Kann ich Zeilen aus einer Tabelle in einem bestimmten Abschnitt des Word-Dokuments löschen?

A: Ja, Sie können Zeilen aus einer Tabelle in einem bestimmten Abschnitt eines Word-Dokuments löschen. Sie können den bereitgestellten Codeausschnitt ändern, um einen bestimmten Abschnitt anzusprechen, indem Sie den entsprechenden Bereich oder das entsprechende Lesezeichen innerhalb dieses Abschnitts verwenden.