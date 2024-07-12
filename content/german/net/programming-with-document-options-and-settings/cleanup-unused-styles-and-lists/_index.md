---
title: Unbenutzte Stile und Listen bereinigen
linktitle: Unbenutzte Stile und Listen bereinigen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Bereinigen nicht verwendeter Stile und Listen in einem Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um nicht verwendete Stile und Listen mit Aspose.Words für .NET zu bereinigen. Mit dieser Funktion können Sie Stile und Listen entfernen, die in einem Dokument nicht verwendet werden.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das Word-Dokument mit den unbenutzten Stilen und Listen, die wir bereinigen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Stile und Listen vor dem Bereinigen zählen

Vor der Bereinigung zählen wir die Anzahl der im Dokument vorhandenen Stile und Listen. Verwenden Sie den folgenden Code, um die Zähler anzuzeigen:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Diese Anweisungen zeigen die Anzahl der im Dokument vor der Bereinigung vorhandenen Stile und Listen.

## Schritt 4: Nicht verwendete Stile und Listen bereinigen

Lassen Sie uns nun nicht verwendete Stile und Listen aus dem Dokument entfernen. Verwenden Sie den folgenden Code, um die Bereinigung durchzuführen:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Dieser Code entfernt nicht verwendete Stile und Listen aus dem Dokument unter Verwendung der angegebenen Optionen. In diesem Beispiel haben wir die`UnusedStyles` Option zum Entfernen nicht verwendeter Stile und deaktivierte die`UnusedLists` Option zum Aufbewahren der Listen, auch wenn sie nicht verwendet werden.

## Schritt 5: Stile und Listen nach der Bereinigung zählen

Nach der Bereinigung zählen wir die Stile und Listen erneut, um zu prüfen, ob sie reduziert wurden. Verwenden Sie den folgenden Code, um die neuen Zähler anzuzeigen:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Diese Anweisungen zeigen die Anzahl der Stile und Listen, die nach der Bereinigung übrig bleiben.

### Beispielquellcode zum Bereinigen nicht verwendeter Stile und Listen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// Zusammen mit den integrierten Stilen verfügt das Dokument nun über acht Stile.
	// Ein benutzerdefinierter Stil wird als „verwendet“ markiert, solange sich im Dokument Text befindet
	// in diesem Stil formatiert. Das bedeutet, dass die 4 Stile, die wir hinzugefügt haben, derzeit nicht verwendet werden.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	// Löscht nicht verwendete Stile und Listen aus dem Dokument, abhängig von den angegebenen CleanupOptions.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Achten Sie darauf, den korrekten Dokumentpfad im`dataDir` Variable.

Sie haben nun gelernt, wie Sie mit Aspose.Words für .NET ungenutzte Stile und Listen aus einem Dokument entfernen. Indem Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie diese Funktion ganz einfach auf Ihre eigenen Dokumente anwenden.

