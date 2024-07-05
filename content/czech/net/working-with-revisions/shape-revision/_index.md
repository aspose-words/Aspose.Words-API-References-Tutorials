---
title: Revize tvaru
linktitle: Revize tvaru
second_title: Aspose.Words API pro zpracování dokumentů
description: Revidujte tvary v dokumentu aplikace Word pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/working-with-revisions/shape-revision/
---

tomto podrobném průvodci vás provedeme tím, jak provádět revize tvarů v dokumentu aplikace Word pomocí Aspose.Words for .NET. Poskytneme vám kompletní zdrojový kód a ukážeme vám, jak formátovat výstup markdown.

## Krok 1: Vytvoření dokumentu a přidání tvarů

Prvním krokem je vytvoření nového dokumentu a přidání tvarů.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Krok 2: Sledujte revize a přidejte další tvar

Zapneme sledování revizí a přidáme další tvar.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Krok 3: Získejte kolekci tvarů a zkontrolujte revize

Získáme kolekci tvarů z dokumentu a zkontrolujeme revize spojené s každým tvarem.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Krok 4: Kontrola revizí přesunu tvaru

Chystáme se načíst existující dokument obsahující revize posunutí tvaru a zkontrolovat související revize.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Příklad zdrojového kódu pro revizi tvaru pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro provádění revizí tvarů v dokumentu pomocí Aspose.Words pro .NET:

```csharp
Document doc = new Document();

//Vložte vložený tvar bez revizí sledování.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Začněte sledovat revize a poté vložte jiný tvar.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Získejte kolekci tvarů dokumentu, která obsahuje pouze dva tvary, které jsme přidali.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Odstraňte první tvar.
shapes[0].Remove();

// Protože jsme tento tvar odstranili během sledování změn, tvar se počítá jako odstraněná revize.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// A při sledování změn jsme vložili další tvar, takže tento tvar se bude počítat jako revize vložení.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// Dokument má jeden tvar, který byl přesunut, ale revize přesunu tvaru budou mít dvě instance tohoto tvaru.
// Jeden bude tvar v místě jeho příletu a druhý bude tvar v jeho původním umístění.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Toto je přechod na revizi, také tvar v místě příjezdu.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Toto je posun od revize, což je tvar na svém původním místě.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Závěr

tomto tutoriálu jsme se naučili, jak provádět revize tvarů v dokumentu aplikace Word pomocí Aspose.Words for .NET. Sledováním kroků vytvoření dokumentu, povolením sledování revizí, kontrolou revizí spojených s každým tvarem a kontrolou revizí pro přesun tvarů jsme byli schopni úspěšně spravovat revize. Aspose.Words for .NET nabízí výkonné rozhraní API pro zpracování textu s recenzemi a formuláři v dokumentech aplikace Word.

### FAQ

#### Otázka: Jak mohu vytvořit nový dokument a přidat tvary v Aspose.Words pro .NET?

A: Chcete-li vytvořit nový dokument a přidat tvary v Aspose.Words pro .NET, můžete použít následující kód. Zde přidáme do první části dokumentu dva tvary, krychli a slunce:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### Otázka: Jak povolím sledování revizí v Aspose.Words pro .NET?

 A: Chcete-li povolit sledování revizí v Aspose.Words pro .NET, můžete použít`StartTrackRevisions` metoda`Document` objekt. Tato metoda bere jako parametr jméno autora revizí:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### Otázka: Jak mohu zkontrolovat revize spojené s každým obrazcem v dokumentu Aspose.Words for .NET?

Odpověď: Chcete-li zkontrolovat revize spojené s každým tvarem v dokumentu Aspose.Words for .NET, můžete získat kolekci tvarů dokumentu pomocí`GetChildNodes` metoda s`NodeType.Shape` typ uzlu. Poté můžete přistupovat ke každému tvaru`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , a`IsMoveToRevision` vlastnosti k určení, jaký typ revize je spojen s tvarem:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### Otázka: Jak mohu zkontrolovat revize přemístění tvarů v dokumentu Aspose.Words for .NET?

 Odpověď: Chcete-li zkontrolovat revize posunutí tvaru v dokumentu Aspose.Words for .NET, můžete načíst existující dokument, který obsahuje revize posunutí tvaru. Poté můžete přistupovat ke každému tvaru`IsMoveFromRevision` a`IsMoveToRevision` vlastnosti, abyste zjistili, zda se přesouvá, a pokud ano, odkud a kam:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```