---
title: Eigenschaften aufzählen
linktitle: Eigenschaften aufzählen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Aufzählen von Dokumenteigenschaften mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-properties/enumerate-properties/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode zum Aufzählen von Dokumenteigenschaften mit Aspose.Words für .NET. Mit dieser Funktion können Sie auf integrierte und benutzerdefinierte Eigenschaften eines Dokuments zugreifen.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das Word-Dokument, dessen Eigenschaften wir auflisten möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Eigenschaften aufzählen

Lassen Sie uns nun die Dokumenteigenschaften auflisten, sowohl die integrierten als auch die benutzerdefinierten Eigenschaften. Verwenden Sie den folgenden Code:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Dieser Code zeigt den Dokumentnamen an und listet dann die integrierten und benutzerdefinierten Eigenschaften mit Anzeige ihres Namens und Werts auf.

### Beispielquellcode für Enumerate Properties mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Achten Sie darauf, den korrekten Dokumentpfad im`dataDir` Variable.

Sie haben nun gelernt, wie Sie Dokumenteigenschaften mit Aspose.Words für .NET aufzählen. Indem Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie problemlos auf die Eigenschaften Ihrer eigenen Dokumente zugreifen und diese anzeigen.

