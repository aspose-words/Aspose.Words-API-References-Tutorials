---
title: Mehrstufige Listenformatierung
linktitle: Mehrstufige Listenformatierung
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine mehrstufige Liste erstellen und benutzerdefinierte Formatierungen anwenden.
type: docs
weight: 10
url: /de/net/document-formatting/multilevel-list-formatting/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie die Funktion zur mehrstufigen Listenformatierung mit Aspose.Words für .NET verwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und die Änderungen anzuwenden.

## Schritt 1: Dokument erstellen und konfigurieren

Erstellen Sie zunächst ein neues Dokument und ein zugehöriges DocumentBuilder-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Formatieren der mehrstufigen Liste

Wir wenden nun die mehrstufige Listenformatierung mit den im DocumentBuilder-Objekt verfügbaren Methoden an. Hier ist wie:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Schritt 3: Speichern des Dokuments

 Nachdem Sie das Texteingabeformularfeld eingefügt haben, speichern Sie das Dokument mithilfe von am gewünschten Ort`Save` Methode. Stellen Sie sicher, dass Sie den richtigen Dateipfad angeben:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Beispielquellcode für die mehrstufige Listenformatierung mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion zur mehrstufigen Listenformatierung mit Aspose.Words für .NET:


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ListFormat.ApplyNumberDefault();
	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.1");
	builder.Writeln("Item 2.2");
	
	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.2.1");
	builder.Writeln("Item 2.2.2");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 2.3");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 3");

	builder.ListFormat.RemoveNumbers();
	
	doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Mit diesem Code können Sie mit Aspose.Words für .NET eine Liste mit mehreren Ebenen erstellen und auf jede Ebene die richtige Formatierung anwenden.