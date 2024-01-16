---
title: obraz
linktitle: obraz
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vkládat a přizpůsobovat obrázek pomocí Aspose.Words for .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/image/
---

V tomto příkladu vysvětlíme, jak používat funkci obrázku s Aspose.Words pro .NET. Obrázky umožňují vkládat do dokumentu ilustrace a grafiku.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Vložení obrázku

 Můžeme vložit obrázek pomocí`Shape` třídu a specifikaci typu obrázku zde`ShapeType.Image` Nastavíme také typ obtékání obrázku na`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Krok 3: Přizpůsobení obrázku

 Obrázek přizpůsobíme například zadáním jeho celé cesty`"/attachment/1456/pic001.png"`a přidání názvu k obrázku.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Příklad zdrojového kódu pro obrázky s Aspose.Words pro .NET

```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

// Vložit obrázek.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

gratuluji! Nyní jste se naučili používat funkci obrázků s Aspose.Words pro .NET.


### FAQ

#### Otázka: Jak mohu vložit obrázek z místního souboru do Aspose.Words?

 A: Chcete-li vložit obrázek z místního souboru do Aspose.Words, můžete použít`Shape` třída a`InsertImage` metoda.

#### Otázka: Mohu vložit obrázek z adresy URL do Aspose.Words?

 Odpověď: Ano, do Aspose.Words můžete vložit obrázek z adresy URL. Můžete použít totéž`InsertImage` a místo cesty k místnímu souboru zadejte adresu URL obrázku.

#### Otázka: Jak mohu změnit velikost obrázku v Aspose.Words?

 A: Chcete-li změnit velikost obrázku v Aspose.Words, můžete použít`Width` a`Height` vlastnosti`Shape` objekt.

#### Otázka: Mohu použít filtry na obrázky v Aspose.Words?

Odpověď: Ano, můžete použít filtry na obrázky v Aspose.Words. Můžete například použít filtr rozostření na obrázek pomocí`ApplyGaussianBlur` metoda`Shape` objekt.

#### Otázka: Jak mohu v Aspose.Words nahradit jeden obrázek jiným?

 A: Chcete-li nahradit jeden obrázek jiným v Aspose.Words, můžete použít`Replace` metoda`Shape` třída. Tato metoda bere jako parametr`Shape` objekt obrázku, který má být nahrazen, a`Shape` objekt nového obrázku.