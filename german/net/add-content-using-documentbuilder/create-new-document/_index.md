---
title: Neues Dokument erstellen
linktitle: Neues Dokument erstellen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein neues Word-Dokument erstellen und Inhalte hinzufügen. Schritt für Schritt Anleitung.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/create-new-document/
---

In diesem Schritt-für-Schritt-Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET ein neues Word-Dokument von Grund auf erstellen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Handbuchs werden Sie in der Lage sein, mithilfe der DocumentBuilder-Klasse ein neues Dokument zu generieren und diesem Inhalte hinzuzufügen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse:

```csharp
Document doc = new Document();
```

## Schritt 2: Inhalte zum Dokument hinzufügen
Als nächstes verwenden Sie ein DocumentBuilder-Objekt, um dem Dokument Inhalte hinzuzufügen. Initialisieren Sie den DocumentBuilder mit dem neu erstellten Dokument:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");
```

## Schritt 3: Speichern Sie das Dokument
Nachdem Sie den gewünschten Inhalt hinzugefügt haben, speichern Sie das Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Beispielquellcode zum Erstellen eines neuen Dokuments mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Erstellen eines neuen Dokuments mit Aspose.Words für .NET:

```csharp
Document doc = new Document();

// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET ein neues Word-Dokument erstellen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt programmgesteuert neue Dokumente generieren und ihnen mithilfe der DocumentBuilder-Klasse Inhalte hinzufügen.

Jetzt können Sie Word-Dokumente sicher erstellen und entsprechend Ihren spezifischen Anforderungen anpassen.

### Beispielquellcode zum Erstellen eines neuen Dokuments mit Aspose.Words für .NET:

```csharp
Document doc = new Document();

// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

Denken Sie daran, den Dateipfad und -namen im Code anzupassen, um das Dokument am gewünschten Speicherort auf Ihrem System zu speichern.

