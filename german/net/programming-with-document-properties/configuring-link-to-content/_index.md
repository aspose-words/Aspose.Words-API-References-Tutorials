---
title: Link zum Inhalt konfigurieren
linktitle: Link zum Inhalt konfigurieren
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Einrichten der Verknüpfung mit Inhalten in einem Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-properties/configuring-link-to-content/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um die Verknüpfung zu Inhalten mit Aspose.Words für .NET einzurichten. Mit dieser Funktion können Sie einen Link zu bestimmten Inhalten in einem Dokument erstellen.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Dokument und Konstruktor erstellen

In diesem Schritt erstellen wir ein neues Dokument und initialisieren den Konstruktor. Verwenden Sie den folgenden Code:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Erstellen Sie ein Lesezeichen

Jetzt erstellen wir ein Lesezeichen im Dokument. Verwenden Sie den folgenden Code, um ein Lesezeichen mit Text darin zu erstellen:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Dieser Code erstellt ein Lesezeichen namens „MyBookmark“ und fügt darin Text hinzu.

## Schritt 4: Einrichten des Inhaltslinks

Nun konfigurieren wir den Link zum Inhalt über die Dokumenteigenschaften. Verwenden Sie den folgenden Code, um den Link zum Inhalt hinzuzufügen und abzurufen:

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

Dieser Code fügt eine inhaltsbezogene Eigenschaft namens „Bookmark“ mit dem Lesezeichen „MyBookmark“ hinzu. Anschließend werden inhaltsbezogene Eigenschaftsinformationen wie Linkstatus, Linkquelle und Eigenschaftswert abgerufen.

### Beispielquellcode für die Konfiguration von Links zu Inhalten mit Aspose.Words für .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Rufen Sie eine Liste aller benutzerdefinierten Dokumenteigenschaften aus der Datei ab.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Mit Inhalt verknüpfte Eigenschaft hinzufügen.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Sie haben nun gelernt, wie Sie mit Aspose.Words für .NET den Link zu Inhalten in einem Dokument konfigurieren. Indem Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie ganz einfach Links zu bestimmten Inhalten in Ihren eigenen Dokumenten erstellen und konfigurieren.