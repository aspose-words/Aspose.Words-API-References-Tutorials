---
title: Erhalten Sie tatsächliche Formbegrenzungspunkte
linktitle: Erhalten Sie tatsächliche Formbegrenzungspunkte
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die tatsächlichen Grenzen einer Form in Punkten (Maßeinheit) in einem Word-Dokument abrufen.
type: docs
weight: 10
url: /de/net/programming-with-shapes/get-actual-shape-bounds-points/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET die tatsächlichen Grenzen einer Form in Punkten (Maßeinheit) in einem Word-Dokument abrufen. Die Grenzen stellen die Größe und Position der Form innerhalb des Dokuments dar.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und der Arbeit mit Word-Dokumenten.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
 Erstellen Sie eine neue Instanz von`Document` Klasse und a`DocumentBuilder` Objekt, um mit dem Dokument zu arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Fügen Sie eine Bildform ein
 Benutzen Sie die`InsertImage` Methode der`DocumentBuilder` Objekt, um eine Bildform in das Dokument einzufügen. Geben Sie den Pfad zur Bilddatei als Parameter an.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Schritt 3: Abrufen der tatsächlichen Formbegrenzungspunkte
 Greifen Sie auf die Formen zu`ShapeRenderer` Verwendung der`GetShapeRenderer`Methode. Rufen Sie dann mithilfe von die tatsächlichen Grenzen der Form in Punkten ab`BoundsInPoints` Eigentum.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Beispielquellcode für „Get Actual Shape Bounds Points“ mit Aspose.Words für .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

Das ist es! Sie haben die tatsächlichen Grenzen einer Form in Punkten in Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich abgerufen.