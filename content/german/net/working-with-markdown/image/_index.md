---
title: Bild
linktitle: Bild
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET Bilder einfügen und anpassen.
type: docs
weight: 10
url: /de/net/working-with-markdown/image/
---

In diesem Beispiel erklären wir, wie Sie die Bildfunktion mit Aspose.Words für .NET verwenden. Mit Bildern können Sie Illustrationen und Grafiken in ein Dokument einfügen.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Bild einfügen

 Wir können ein Bild einfügen mit dem`Shape` Klasse und Angabe des Bildtyps, hier`ShapeType.Image` . Wir setzen auch den Wrap-Typ des Bildes auf`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Schritt 3: Bildanpassung

 Wir passen das Bild an, indem wir seinen vollständigen Pfad angeben, zum Beispiel`"/attachment/1456/pic001.png"`, und fügen Sie dem Bild einen Titel hinzu.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Beispiel-Quellcode für Bilder mit Aspose.Words für .NET

```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Bild einfügen.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Bilderfunktion mit Aspose.Words für .NET verwenden.


### Häufig gestellte Fragen

#### F: Wie kann ich ein Bild aus einer lokalen Datei in Aspose.Words einfügen?

 A: Um ein Bild aus einer lokalen Datei in Aspose.Words einzufügen, können Sie den`Shape` Klasse und die`InsertImage` Methode.

#### F: Kann ich in Aspose.Words ein Bild von einer URL einfügen?

 A: Ja, Sie können ein Bild von einer URL in Aspose.Words einfügen. Sie können dasselbe verwenden`InsertImage`Methode und geben Sie die Bild-URL anstelle des lokalen Dateipfads an.

#### F: Wie kann ich die Größe eines Bildes in Aspose.Words ändern?

 A: Um die Größe eines Bildes in Aspose.Words zu ändern, können Sie den`Width`Und`Height` Eigenschaften der`Shape` Objekt.

#### F: Kann ich in Aspose.Words Filter auf Bilder anwenden?

 A: Ja, Sie können Filter auf Bilder in Aspose.Words anwenden. Sie können beispielsweise einen Weichzeichnerfilter auf ein Bild anwenden, indem Sie`ApplyGaussianBlur` Methode der`Shape` Objekt.

#### F: Wie kann ich in Aspose.Words ein Bild durch ein anderes ersetzen?

 A: Um ein Bild durch ein anderes in Aspose.Words zu ersetzen, können Sie den`Replace` Methode der`Shape` Klasse. Diese Methode verwendet als Parameter die`Shape` Objekt des zu ersetzenden Bildes und die`Shape` Objekt des neuen Bildes.