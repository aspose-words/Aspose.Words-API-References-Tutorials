---
title: Link zum Inhalt konfigurieren
linktitle: Link zum Inhalt konfigurieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Einrichten einer Verknüpfung mit Inhalten in einem Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-properties/configuring-link-to-content/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um die Verknüpfung mit Inhalten mit Aspose.Words für .NET einzurichten. Mit dieser Funktion können Sie auf bestimmte Inhalte in einem Dokument verlinken.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Erstellen des Dokuments und des Konstruktors

In diesem Schritt erstellen wir ein neues Dokument und initialisieren den Konstruktor. Verwenden Sie den folgenden Code:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Lesezeichen erstellen

Jetzt erstellen wir ein Lesezeichen im Dokument. Verwenden Sie den folgenden Code, um ein Lesezeichen mit Text darin zu erstellen:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Dieser Code erstellt ein Lesezeichen namens „MyBookmark“ und fügt etwas Text hinzu.

## Schritt 4: Einrichten des Inhaltslinks

Nun konfigurieren wir den Link zum Inhalt mithilfe der Dokumenteigenschaften. Verwenden Sie den folgenden Code, um den Link zum Inhalt hinzuzufügen und abzurufen:

```csharp
// Rufen Sie die Liste aller benutzerdefinierten Eigenschaften im Dokument ab.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Fügen Sie eine inhaltsgebundene Eigenschaft hinzu.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Dieser Code fügt eine inhaltsbezogene Eigenschaft namens „Bookmark“ mit dem Lesezeichen „MyBookmark“ hinzu. Anschließend ruft er inhaltsbezogene Eigenschaftsinformationen wie Linkstatus, Linkquelle und Eigenschaftswert ab.

### Beispielquellcode zum Konfigurieren eines Links zum Inhalt mit Aspose.Words für .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Rufen Sie eine Liste aller benutzerdefinierten Dokumenteigenschaften aus der Datei ab.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Verknüpfte Eigenschaft zum Inhalt hinzufügen.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Sie haben nun gelernt, wie Sie mit Aspose.Words für .NET den Link zum Inhalt eines Dokuments konfigurieren. Indem Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie ganz einfach Links zu bestimmten Inhalten in Ihren eigenen Dokumenten erstellen und konfigurieren.