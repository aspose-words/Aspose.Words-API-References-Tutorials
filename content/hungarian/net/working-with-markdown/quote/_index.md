---
title: Idézet
linktitle: Idézet
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan használhatja az idézetet az Aspose.Words for .NET használatával Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/quote/
---

Ebben a példában elmagyarázzuk, hogyan használható az idézet funkció az Aspose-ban. A Words for .NET Quote a szövegrészek kiemelésére szolgál speciális kerettel.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. lépés: Az alapértelmezett idézési stílus használata

Az "Idézet" nevű alapértelmezett bekezdésstílust használjuk az idézet formázásának alkalmazásához a szövegben.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## 3. lépés: Stílusok létrehozása a beágyazott szintek számára

 A beágyazott szintekhez stílusokat hozhatunk létre a`Styles.Add` módszere a`Document` tárgy. Ebben a példában egy "Idézet1" nevű stílust hozunk létre, amely egy beágyazott idézetszintet képvisel.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Példa forráskódra hivatkozásokhoz az Aspose.Words for .NET használatával


```csharp
// Használjon dokumentumkészítőt, hogy tartalmat adjon a dokumentumhoz.
DocumentBuilder builder = new DocumentBuilder();

// Alapértelmezés szerint a dokumentum az első szint blokk-idézet stílusát tárolja.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Hozzon létre stílusokat a beágyazott szintek számára a stílusörökléssel.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Gratulálok ! Most már megtanulta, hogyan kell használni az Aspose.Words for .NET hivatkozási funkcióját.


### GYIK

#### K: Mit jelent az idézet a Markdown nyelven?

V: Az idézet a Markdown-ban egy módja annak, hogy kiemelje más forrásból származó szövegrészeket, vagy hivatkozzon híres idézetekre.

#### K: Hogyan használjunk idézőjeleket a Markdownban?

V: Ha a Markdown-ban idézetet szeretne használni, tegye az idézet szövegét szögletes zárójelbe (`>`). Az idézet minden sorának chevronnal kell kezdődnie.

#### K: A Markdown idézőjelek támogatják az attribútumokat?

V: A Markdown hivatkozások nem támogatnak bizonyos attribútumokat. Ezeket egyszerűen kiemeli az idézett szöveg formázása.

#### K: Be tud ágyazni idézeteket a Markdownba?

V: Igen, lehetséges idézőjelek egymásba ágyazása a Markdown-ban egy extra szintű szögletes zárójelek hozzáadásával (`>`).