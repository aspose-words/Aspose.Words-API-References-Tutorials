---
title: Bereinigen Sie nicht verwendete Stile und Listen
linktitle: Bereinigen Sie nicht verwendete Stile und Listen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Bereinigen nicht verwendeter Stile und Listen in einem Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um nicht verwendete Stile und Listen mit Aspose.Words für .NET zu bereinigen. Mit dieser Funktion können Sie Stile und Listen entfernen, die in einem Dokument nicht verwendet werden.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

In diesem Schritt laden wir das Word-Dokument, das die nicht verwendeten Stile und Listen enthält, die wir bereinigen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Zählen Sie Stile und Listen vor dem Bereinigen

Vor der Bereinigung zählen wir die Anzahl der im Dokument vorhandenen Stile und Listen. Verwenden Sie den folgenden Code, um die Zähler anzuzeigen:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Diese Anweisungen zeigen die Anzahl der im Dokument vorhandenen Stile und Listen vor der Bereinigung.

## Schritt 4: Bereinigen Sie nicht verwendete Stile und Listen

Lassen Sie uns nun nicht verwendete Stile und Listen aus dem Dokument bereinigen. Verwenden Sie den folgenden Code, um die Bereinigung durchzuführen:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Dieser Code bereinigt mithilfe der angegebenen Optionen nicht verwendete Stile und Listen aus dem Dokument. In diesem Beispiel haben wir das aktiviert`UnusedStyles` Option zum Entfernen nicht verwendeter Stile und Deaktivieren der`UnusedLists` Option, die Listen auch dann beizubehalten, wenn sie nicht verwendet werden.

## Schritt 5: Zählen Sie Stile und Listen nach dem Bereinigen

Nach der Bereinigung zählen wir die Stile und Listen erneut, um zu überprüfen, ob sie reduziert wurden. Verwenden Sie den folgenden Code, um die neuen Zähler anzuzeigen:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Diese Anweisungen zeigen die Anzahl der nach der Reinigung verbleibenden Stile und Listen.

### Beispielquellcode für die Bereinigung nicht verwendeter Stile und Listen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// In Kombination mit den integrierten Stilen verfügt das Dokument nun über acht Stile.
	// Ein benutzerdefinierter Stil wird als „verwendet“ markiert, solange Text im Dokument vorhanden ist
	// in diesem Stil formatiert. Das bedeutet, dass die 4 von uns hinzugefügten Stile derzeit nicht verwendet werden.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Bereinigt nicht verwendete Stile und Listen aus dem Dokument, abhängig von den angegebenen CleanupOptions.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben`dataDir` Variable.

Sie haben jetzt gelernt, wie Sie mit Aspose.Words für .NET ungenutzte Stile und Listen aus einem Dokument bereinigen. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie diese Funktion problemlos auf Ihre eigenen Dokumente anwenden.

