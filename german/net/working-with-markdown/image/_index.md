---
title: Bild
linktitle: Bild
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie Bilder mit Aspose.Words für .NET einfügen und anpassen.
type: docs
weight: 10
url: /de/net/working-with-markdown/image/
---

In diesem Beispiel erklären wir, wie Sie die Bildfunktion mit Aspose.Words für .NET verwenden. Mit Bildern können Sie Illustrationen und Grafiken in ein Dokument einfügen.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Einfügen eines Bildes

 Wir können ein Bild mit einfügen`Shape` Klasse und geben Sie hier den Typ des Bildes an`ShapeType.Image` Wir stellen auch den Wrap-Typ des Bildes auf ein`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Schritt 3: Bildanpassung

 Wir passen das Bild an, indem wir beispielsweise seinen vollständigen Pfad angeben`"/attachment/1456/pic001.png"`und dem Bild einen Titel hinzufügen.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Beispielquellcode für Bilder mit Aspose.Words für .NET

```csharp
// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Bild einfügen.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Bilderfunktion mit Aspose.Words für .NET verwenden.

