---
title: Bild
linktitle: Bild
second_title: Aspose.Words Document Processing API
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


### FAQ's

#### F: Hur kan jag infoga en bild från en lokal fil i Aspose.Words?

 S: För att infoga en bild från en lokal fil i Aspose.Words kan du använda`Shape` klass och`InsertImage` metod.

#### F: Kan jag infoga en bild från en URL i Aspose.Words?

 S: Ja, du kan infoga en bild från en URL i Aspose.Words. Du kan använda samma`InsertImage` metod och ange bildens URL istället för den lokala filsökvägen.

#### F: Hur kan jag ändra storlek på en bild i Aspose.Words?

 S: För att ändra storlek på en bild i Aspose.Words kan du använda`Width` och`Height` egenskaper hos`Shape` objekt.

#### F: Kan jag använda filter på bilder i Aspose.Words?

S: Ja, du kan använda filter på bilder i Aspose.Words. Du kan till exempel använda ett oskärpafilter på en bild med hjälp av`ApplyGaussianBlur` metod för`Shape` objekt.

#### F: Hur kan jag ersätta en bild med en annan i Aspose.Words?

 S: För att ersätta en bild med en annan i Aspose.Words kan du använda`Replace` metod för`Shape` klass. Denna metod tar som parameter`Shape` objektet för bilden som ska ersättas och`Shape` objektet för den nya bilden.