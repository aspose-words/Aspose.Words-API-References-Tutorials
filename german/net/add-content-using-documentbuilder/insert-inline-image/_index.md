---
title: Inline-Bild einfügen
linktitle: Inline-Bild einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Inline-Bilder in Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-inline-image/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Inline-Bilder in ein Word-Dokument einfügen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieser Anleitung werden Sie in der Lage sein, Bilder direkt in den Text Ihrer Dokumente einzufügen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Fügen Sie ein Inline-Bild ein
Als nächstes verwenden Sie die Methode „InsertImage“ der Klasse „DocumentBuilder“, um ein Inline-Bild in das Dokument einzufügen. Geben Sie den Pfad der Bilddatei als Parameter an:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Schritt 3: Speichern Sie das Dokument
Speichern Sie das Dokument nach dem Einfügen des Inline-Bilds mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Beispielquellcode zum Einfügen eines Inline-Bildes mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Einfügen eines Inline-Bildes mit Aspose.Words für .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET Inline-Bilder in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie nun Bilder nahtlos in den Text Ihrer Dokumente einfügen.

Inline-Bilder sind für verschiedene Szenarien nützlich, z. B. das Hinzufügen von Illustrationen, Logos oder anderen visuellen Elementen direkt in den Dokumentfluss.
