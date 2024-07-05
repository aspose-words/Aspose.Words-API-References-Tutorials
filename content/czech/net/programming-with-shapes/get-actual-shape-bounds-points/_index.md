---
title: Získejte skutečné body za hranice tvaru
linktitle: Získejte skutečné body za hranice tvaru
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak získat skutečné hranice tvaru v bodech (jednotka měření) v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-shapes/get-actual-shape-bounds-points/
---

Tento tutoriál vysvětluje, jak získat skutečné hranice tvaru v bodech (jednotka měření) v dokumentu aplikace Word pomocí Aspose.Words for .NET. Hranice představují velikost a polohu tvaru v dokumentu.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Vytvořte nový dokument a DocumentBuilder
 Vytvořte novou instanci souboru`Document` třída a a`DocumentBuilder`objekt pracovat s dokumentem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Vložte obrazový tvar
 Použijte`InsertImage` metoda`DocumentBuilder` objekt pro vložení tvaru obrázku do dokumentu. Jako parametr zadejte cestu k souboru obrázku.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Krok 3: Načtěte skutečné body hranic tvaru
 Přístup k tvaru`ShapeRenderer` za použití`GetShapeRenderer` metoda. Poté načtěte skutečné hranice tvaru v bodech pomocí`BoundsInPoints` vlastnictví.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Příklad zdrojového kódu pro Get Actual Shape Bounds Points pomocí Aspose.Words for .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

A je to! Úspěšně jste získali skutečné hranice tvaru v bodech ve vašem dokumentu aplikace Word pomocí Aspose.Words for .NET.