---
title: Kép
linktitle: Kép
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan lehet képeket beszúrni és testreszabni az Aspose.Words for .NET segítségével Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/image/
---

Ebben a példában elmagyarázzuk, hogyan kell használni a képfunkciót az Aspose.Words for .NET-hez. A képek lehetővé teszik illusztrációk és grafikák beillesztését a dokumentumba.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. lépés: Kép beszúrása

 Képet a segítségével szúrhatunk be`Shape` osztályba, és itt adja meg a kép típusát`ShapeType.Image` . Beállítjuk a kép tördelési típusát is`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## 3. lépés: Kép testreszabása

 Testreszabjuk a képet például a teljes elérési út megadásával`"/attachment/1456/pic001.png"`, és adjon hozzá egy címet a képhez.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Példa forráskódhoz képekhez Aspose.Words for .NET

```csharp
// Használjon dokumentumkészítőt, hogy tartalmat adjon a dokumentumhoz.
DocumentBuilder builder = new DocumentBuilder();

// Kép beszúrása.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Gratulálok ! Most már megtanulta, hogyan kell használni a képek funkciót az Aspose.Words for .NET-hez.


### GYIK

#### K: Hogyan illeszthetek be képet egy helyi fájlból az Aspose.Words fájlba?

 V: Ha egy helyi fájlból szeretne képet beszúrni az Aspose.Wordsbe, használja a`Shape` osztály és a`InsertImage` módszer.

#### K: Beszúrhatok képet az Aspose.Words URL-ből?

 V: Igen, beszúrhat egy képet az Aspose.Words-ben található URL-ből. Ugyanazt használhatod`InsertImage`módszert, és adja meg a kép URL-címét a helyi fájl elérési útja helyett.

#### K: Hogyan méretezhetek át egy képet az Aspose.Words programban?

 V: Az Aspose.Words képének átméretezéséhez használhatja a`Width` és`Height` tulajdonságai a`Shape` tárgy.

#### K: Alkalmazhatok szűrőket az Aspose.Words képeire?

 V: Igen, alkalmazhat szűrőket az Aspose.Words képeire. Például alkalmazhat elmosódási szűrőt egy képre a`ApplyGaussianBlur` módszere a`Shape` tárgy.

#### K: Hogyan cserélhetek le egy képet egy másikra az Aspose.Wordsben?

 V: Az Aspose.Words egyik képének másikra cseréléséhez használhatja a`Replace` módszere a`Shape` osztály. Ez a módszer paraméterként a`Shape` a cserélendő kép objektuma és a`Shape` az új kép tárgya.