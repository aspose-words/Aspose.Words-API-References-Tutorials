---
title: Doppelten Stil bereinigen
linktitle: Doppelten Stil bereinigen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Bereinigen doppelter Stile in einem Dokument mit Aspose.Words für .NET. Vollständiger Quellcode enthalten.
type: docs
weight: 10
url: /de/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den C#-Quellcode, um doppelte Stile mit Aspose.Words für .NET zu bereinigen. Diese Funktion hilft, doppelte Stile aus einem Dokument zu entfernen.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das Word-Dokument, das wir bereinigen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Stile vor dem Reinigen zählen

Bevor wir mit der Bereinigung fortfahren, zählen wir die Anzahl der im Dokument vorhandenen Stile. Verwenden Sie den folgenden Code, um die Anzahl der Stile anzuzeigen:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Diese Anweisung zeigt die Anzahl der im Dokument vorhandenen Stile an.

## Schritt 4: Doppelte Stile bereinigen

Lassen Sie uns nun doppelte Stile aus dem Dokument entfernen. Verwenden Sie den folgenden Code, um die Bereinigung durchzuführen:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Dieser Code entfernt doppelte Stile aus dem Dokument unter Verwendung der angegebenen Optionen. In diesem Beispiel haben wir die`DuplicateStyle` Option zum Bereinigen doppelter Stile.

## Schritt 5: Stile nach der Reinigung zählen

Nach der Bereinigung zählen wir die Anzahl der Stile erneut, um zu prüfen, ob sie abgenommen hat. Verwenden Sie den folgenden Code, um die neue Anzahl der Stile anzuzeigen:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Diese Anweisung zeigt die Anzahl der nach der Bereinigung verbleibenden Stile an.

### Beispielquellcode für Cleanup Duplicate Style mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Anzahl der Stile vor der Bereinigung.
	Console.WriteLine(doc.Styles.Count);

	// Entfernt doppelte Stile aus dem Dokument.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//Die Anzahl der Stile nach der Bereinigung wurde verringert.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```