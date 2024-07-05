---
title: Holen Sie sich tatsächliche Formbegrenzungspunkte
linktitle: Holen Sie sich tatsächliche Formbegrenzungspunkte
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die tatsächlichen Grenzen einer Form in Punkten (Maßeinheit) in einem Word-Dokument abrufen.
type: docs
weight: 10
url: /de/net/programming-with-shapes/get-actual-shape-bounds-points/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET die tatsächlichen Grenzen einer Form in Punkten (Maßeinheit) in einem Word-Dokument abrufen. Die Grenzen stellen die Größe und Position der Form innerhalb des Dokuments dar.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Neues Dokument und DocumentBuilder erstellen
 Erstellen Sie eine neue Instanz des`Document` Klasse und eine`DocumentBuilder`Objekt, um mit dem Dokument zu arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Einfügen einer Bildform
 Verwenden Sie die`InsertImage` Methode der`DocumentBuilder` Objekt, um eine Bildform in das Dokument einzufügen. Geben Sie den Pfad zur Bilddatei als Parameter an.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Schritt 3: Tatsächliche Formbegrenzungspunkte abrufen
 Zugriff auf die Shapes`ShapeRenderer` Verwendung der`GetShapeRenderer` Methode. Dann ermitteln Sie die tatsächlichen Grenzen der Form in Punkten mit der`BoundsInPoints` Eigentum.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Beispielquellcode zum Abrufen tatsächlicher Formbegrenzungspunkte mit Aspose.Words für .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

Das ist es! Sie haben die tatsächlichen Grenzen einer Form in Punkten in Ihrem Word-Dokument erfolgreich mit Aspose.Words für .NET abgerufen.