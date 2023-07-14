---
title: Bereinigen Sie den doppelten Stil
linktitle: Bereinigen Sie den doppelten Stil
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Bereinigen doppelter Stile in einem Dokument mit Aspose.Words für .NET. Vollständiger Quellcode enthalten.
type: docs
weight: 10
url: /de/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den C#-Quellcode, um doppelte Stile mit Aspose.Words für .NET zu bereinigen. Mit dieser Funktion können Sie doppelte Stile aus einem Dokument entfernen.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

In diesem Schritt laden wir das Word-Dokument, das wir bereinigen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Zählen Sie die Stile vor der Reinigung

Bevor wir mit der Bereinigung fortfahren, zählen wir die Anzahl der im Dokument vorhandenen Stile. Verwenden Sie den folgenden Code, um die Stilanzahl anzuzeigen:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Diese Anweisung zeigt die Anzahl der im Dokument vorhandenen Stile an.

## Schritt 4: Bereinigen Sie doppelte Stile

Lassen Sie uns nun doppelte Stile aus dem Dokument bereinigen. Verwenden Sie den folgenden Code, um die Bereinigung durchzuführen:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Dieser Code bereinigt mithilfe der angegebenen Optionen doppelte Stile aus dem Dokument. In diesem Beispiel haben wir das aktiviert`DuplicateStyle` Option zum Bereinigen doppelter Stile.

## Schritt 5: Zählen Sie die Stile nach der Reinigung

Nach der Reinigung zählen wir die Anzahl der Styles erneut, um zu prüfen, ob sie abgenommen hat. Verwenden Sie den folgenden Code, um die Anzahl der neuen Stile anzuzeigen:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Diese Anweisung zeigt die Anzahl der nach der Reinigung verbleibenden Stile an.

### Beispielquellcode für Cleanup Duplicate Style mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Anzahl der Stile vor der Bereinigung.
	Console.WriteLine(doc.Styles.Count);

	// Bereinigt doppelte Stile aus dem Dokument.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//Die Anzahl der Stile nach der Bereinigung wurde verringert.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```