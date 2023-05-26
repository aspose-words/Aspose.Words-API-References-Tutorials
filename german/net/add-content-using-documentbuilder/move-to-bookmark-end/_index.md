---
title: Zum Ende des Lesezeichens verschieben
linktitle: Zum Ende des Lesezeichens verschieben
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET zum Ende eines Lesezeichens in Word-Dokumenten wechseln.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/move-to-bookmark-end/
---

In diesem Beispiel untersuchen wir die Funktion „Zum Ende des Lesezeichens verschieben“ von Aspose.Words für .NET. Aspose.Words ist eine leistungsstarke Dokumentbearbeitungsbibliothek, die es Entwicklern ermöglicht, Word-Dokumente programmgesteuert zu erstellen, zu ändern und zu konvertieren. Mit der Funktion „Zum Ende des Lesezeichens verschieben“ können wir zum Ende eines bestimmten Lesezeichens in einem Dokument navigieren und danach Inhalte hinzufügen.

## Einrichten der Umgebung

Bevor wir uns mit den Implementierungsdetails befassen, stellen wir sicher, dass wir die erforderliche Umgebung für die Arbeit mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie Folgendes haben:

- Eine funktionierende Installation der Aspose.Words für .NET-Bibliothek
- Grundkenntnisse der Programmiersprache C#
- Zugriff auf eine .NET-Entwicklungsumgebung

## Grundlegendes zur Funktion „An Lesezeichenende verschieben“ von Aspose.Words für .NET

Mit der Funktion „Zum Ende des Lesezeichens verschieben“ können Sie mit Aspose.Words für .NET zum Ende eines Lesezeichens in einem Word-Dokument navigieren. Diese Funktion ist nützlich, wenn Sie Inhalte nach einem bestimmten Lesezeichen in Ihrem Dokument programmgesteuert hinzufügen möchten.

## Den Quellcode Schritt für Schritt erklären

Lassen Sie uns den bereitgestellten Quellcode Schritt für Schritt aufschlüsseln, um zu verstehen, wie Sie die Funktion „An Lesezeichenende verschieben“ in Aspose.Words für .NET verwenden.

## Schritt 1: Initialisieren des Dokuments und des Dokument-Builders

 Zuerst müssen wir das initialisieren`Document` Und`DocumentBuilder` Objekte:

```csharp
Document doc = new Document(MyDir + "Bookmarks.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Zum Ende des Lesezeichens wechseln

 Um zum Ende eines Lesezeichens zu gelangen, verwenden Sie die`MoveToBookmark` Methode der`DocumentBuilder` Klasse:

```csharp
builder.MoveToBookmark("MyBookmark1", false, true);
```

 Der`MoveToBookmark` Die Methode benötigt drei Parameter:
- Lesezeichenname: Geben Sie den Namen des Lesezeichens an, zu dem Sie verschieben möchten.
-  IsBookmarkStart: Auf gesetzt`false` um zum Ende des Lesezeichens zu gelangen.
-  IsBookmarkEnd: Auf gesetzt`true` um anzuzeigen, dass Sie zum Ende des Lesezeichens wechseln möchten.

## Schritt 3: Inhalte am Ende des Lesezeichens hinzufügen

Sobald Sie zum Ende des Lesezeichens gelangt sind, können Sie mithilfe der verschiedenen von bereitgestellten Methoden Inhalte hinzufügen`DocumentBuilder` Klasse. In diesem Beispiel verwenden wir die`Writeln` Methode zum Schreiben einer Textzeile:

```csharp
builder.Writeln("This is a bookmark.");
```

 Der`Writeln` Die Methode hängt den angegebenen Text als neuen Absatz an der aktuellen Position an`DocumentBuilder`.

### Beispielquellcode für „Move To Bookmark End“ mit Aspose.Words für .NET

```csharp

	Document doc = new Document(MyDir + "Bookmarks.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.MoveToBookmark("MyBookmark1", false, true);
	builder.Writeln("This is a bookmark.");
	
```

## Abschluss

Wir haben die Funktion „An Lesezeichenende verschieben“ von Aspose.Words für .NET untersucht. Wir haben gelernt, wie man mithilfe des bereitgestellten Quellcodes zum Ende eines Lesezeichens navigiert und Inhalte programmgesteuert hinzufügt. Diese Funktion bietet Flexibilität bei der Bearbeitung von Word-Dokumenten mit Aspose.Words für .NET.

