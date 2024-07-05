---
title: Behúzott kód
linktitle: Behúzott kód
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan használhatja a behúzott kódot az Aspose.Words for .NET-hez Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/indented-code/
---

Ebben a példában elmagyarázzuk, hogyan kell használni a behúzott kód szolgáltatást az Aspose.Words for .NET-hez. A behúzott kód speciális formázással rendelkező kódblokkok vizuális megjelenítésére szolgál.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. lépés: Adjon hozzá stílust a behúzott kódhoz

Egyéni stílust adunk hozzá a behúzott kódhoz a segítségével`Styles.Add` módszere a`Document` tárgy. Ebben a példában létrehozunk egy "IndentedCode" nevű stílust a behúzott kódhoz.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## 3. lépés: Adjon hozzá behúzott kódot

Most hozzáadhatunk egy behúzott kódblokkot az "IndentedCode" egyéni stílus használatával.

```csharp
builder.Writeln("This is an indented code block");
```

### Példa forráskód a behúzott kódhoz az Aspose.Words for .NET-hez

```csharp
// Használjon dokumentumkészítőt, hogy tartalmat adjon a dokumentumhoz.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Gratulálok ! Most megtanulta, hogyan kell használni a behúzott kód funkciót az Aspose.Words for .NET-hez.


### GYIK

#### K: Mi az a behúzott kód a Markdownban?

V: A Markdown behúzott kódja egy formázási módszer, amelyet a Markdown dokumentumban lévő kód megjelenítésére használnak. Ez abból áll, hogy minden kódsort szóközökkel vagy tabulátorokkal behúz.

#### K: Hogyan kell használni a behúzott kódot a Markdownban?

V: Ha behúzott kódot szeretne használni a Markdown alkalmazásban, minden kódsort szóközzel vagy tabulátorral húzza be.

#### K: Milyen előnyei vannak a Markdown behúzott kódjának?

V: A Markdown behúzott kódja javítja a kód olvashatóságát, és könnyebben érthetővé teszi az olvasók számára.

#### K: Mi a különbség a behúzott kód és a Markdown kódblokkjai között?

V: A behúzott kódot a szövegbe beszúrt kis kódrészletekhez, míg a kódblokkokat a nagyobb kódrészletek külön formátumban történő megjelenítéséhez használják.

#### K: Az összes Markdown-szerkesztő támogatja a Markdown behúzott kódját?

V: A Markdown program behúzott kódjának támogatása a Markdown szerkesztőkben eltérő lehet. Ellenőrizze a kiadója konkrét dokumentációját, hogy megbizonyosodjon róla.