---
title: Bekerített kód
linktitle: Bekerített kód
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan használhatja az elkerített kód funkciót az Aspose.Words for .NET segítségével Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/fenced-code/
---

Ebben a példában végigvezetjük, hogyan használhatja az elkerített kód funkciót az Aspose.Words for .NET-hez. Az elkerített kód meghatározott formátumú kódblokkok megjelenítésére szolgál.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. lépés: Stílus hozzáadása a bekerített kódhoz

 Egyéni stílust adunk hozzá az elkerített kódhoz a`Styles.Add` módszere a`Document` tárgy. Ebben a példában létrehozunk egy "FencedCode" nevű stílust az elkerített kódhoz.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## 3. lépés: Elkerített kód hozzáadása információ nélkül

Most hozzáadhatunk egy elkerített kódblokkot információs karakterlánc nélkül a "FencedCode" egyéni stílus használatával.

```csharp
builder.Writeln("This is an fenced code");
```

## 4. lépés: Adjon hozzá elkerített kódot információs karakterlánccal

Hozzáadhatunk egy elkerített kódblokkot egy információs karakterlánccal egy másik egyedi stílus használatával. Ebben a példában egy "FencedCode.C#" nevű stílust hozunk létre, amely egy C# kód blokkját reprezentálja.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Példa forráskód a Fenced Code-hoz az Aspose.Words for .NET használatával

```csharp
// Használjon dokumentumkészítőt, hogy tartalmat adjon a dokumentumhoz.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### GYIK

#### K: Mi az a tagolt kód a Markdownban?

V: A Markdown elválasztott kódja egy formázási módszer, amelyet a Markdown dokumentumban lévő kód megjelenítésére használnak. Ez a kód meghatározott határolókkal való keretezéséből áll.

#### K: Milyen előnyei vannak a Markdown elválasztó kódjának?

V: A Markdown elválasztott kódja javítja a kód olvashatóságát, és könnyebben érthetővé teszi az olvasók számára. Egyes Markdown szerkesztőkben lehetővé teszi a szintaxis kiemelésének megőrzését is.

#### K: Mi a különbség a tagolt és a behúzott kód között a Markdownban?

V: A tagolt kód meghatározott határolókat használ a kód bezárására, míg a behúzott kód minden kódsort szóközökkel vagy tabulátorokkal behúz.

#### K: Az összes Markdown-szerkesztő támogatja a Markdown elválasztott kódját?

V: A Markdown tagolt kódjának támogatása a Markdown szerkesztőkben eltérő lehet. Ellenőrizze a kiadója konkrét dokumentációját, hogy megbizonyosodjon róla.

