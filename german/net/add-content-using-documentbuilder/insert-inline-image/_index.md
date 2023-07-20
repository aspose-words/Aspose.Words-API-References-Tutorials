---
title: Inline-Bild in Word-Dokument einfügen
linktitle: Inline-Bild in Word-Dokument einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

### FAQs zum Einfügen von Inline-Bildern in Word-Dokumente

#### F: Kann ich die Größe der Inline-Bilder im Word-Dokument ändern?

A: Ja, Sie können die Größe der Inline-Bilder mit Aspose.Words für .NET ändern. Nachdem Sie das Bild eingefügt haben, können Sie seine Größe manipulieren, indem Sie die Breiten- und Höheneigenschaften des Shape-Objekts anpassen, das das Bild darstellt.

#### F: Ist es aus Gründen der Barrierefreiheit möglich, Alternativtext zu Inline-Bildern hinzuzufügen?

A: Ja, Sie können Inline-Bildern Alternativtext hinzufügen, um die Barrierefreiheit zu verbessern. Aspose.Words für .NET unterstützt das Hinzufügen von Alternativtext zu Bildern, sodass Bildschirmlesegeräte und andere Hilfstechnologien den Bildinhalt für sehbehinderte Benutzer beschreiben können.

#### F: Kann ich Formatierungen oder Stile auf die Inline-Bilder anwenden?

A: Auf jeden Fall! Aspose.Words für .NET bietet umfangreiche Formatierungsoptionen für Inline-Bilder. Sie können verschiedene Stile, Rahmen, Effekte und andere Formatierungsattribute auf die Bilder anwenden, um sie an das visuelle Design Ihres Dokuments anzupassen.

#### F: Unterstützt Aspose.Words für .NET das Einfügen von Bildern aus einem Stream oder Byte-Array?

A: Ja, Sie können mit Aspose.Words für .NET Inline-Bilder aus Streams oder Byte-Arrays einfügen. Dadurch können Sie mit Bildern arbeiten, die von externen Quellen geladen wurden, oder mit dynamisch generierten Bildern.

#### F: Kann ich Bilder an bestimmten Positionen im Textinhalt einfügen?

A: Ja, die DocumentBuilder-Klasse in Aspose.Words für .NET bietet eine präzise Kontrolle über die Einfügeposition von Inline-Bildern. Sie können die genaue Stelle im Text angeben, an der das Bild eingefügt werden soll.