---
title: Bild
linktitle: Bild
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar och anpassar en bild med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/image/
---

I det här exemplet kommer vi att förklara hur man använder bildfunktionen med Aspose.Words för .NET. Med bilder kan du infoga illustrationer och grafik i ett dokument.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Infoga en bild

 Vi kan infoga en bild med hjälp av`Shape` klass och specificera typ av bild, här`ShapeType.Image` Vi ställer också in bildens wrap-typ till`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Steg 3: Bildanpassning

 Vi anpassar till exempel bilden genom att ange hela sökvägen`"/attachment/1456/pic001.png"`, och lägga till en titel till bilden.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Exempel på källkod för bilder med Aspose.Words för .NET

```csharp
// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
DocumentBuilder builder = new DocumentBuilder();

// Infoga bild.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Grattis! Du har nu lärt dig hur du använder bildfunktionen med Aspose.Words för .NET.

