---
title: Áthúzott
linktitle: Áthúzott
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan alkalmazhatja az áthúzott szövegstílust az Aspose.Words for .NET segítségével Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/strikethrough/
---


Ebben a példában végigvezetjük, hogyan alkalmazhatja az áthúzott szövegstílust az Aspose.Words for .NET használatával. Az áthúzott szöveg azt jelzi, hogy a szöveg törölve van vagy már nem érvényes.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. lépés: Alkalmazza az áthúzott szövegstílust

Az áthúzott szövegstílust a beállításával engedélyezzük`StrikeThrough` tulajdona a`Font` tiltakozni`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## 3. lépés: Adjon hozzá áthúzott szöveget

 Mostantól áthúzható szöveget adhatunk hozzá a dokumentumgenerátor segítségével`Writeln` módszer.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Példa forráskódra áthúzott szöveghez az Aspose.Words for .NET segítségével

```csharp
// Használjon dokumentumkészítőt, hogy tartalmat adjon a dokumentumhoz.
DocumentBuilder builder = new DocumentBuilder();

// Tegye áthúzva a szöveget.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Gratulálok ! Most megtanulta, hogyan kell alkalmazni az áthúzott szövegstílust az Aspose.Words for .NET segítségével.

### GYIK

#### K: Hogyan adhatom hozzá az áthúzott szöveget az Aspose.Words-hez?

 V: Az áthúzott szöveg hozzáadásához az Aspose.Wordsben használhatja a`Font.StrikeThrough` tulajdona a`Run`tárgy. Beállíthatja ezt a tulajdonságot`true` áthúzott szöveg hozzáadásához az adott szöveghez. Például használhatja`run.Font.StrikeThrough=true` az áthúzott szöveg hozzáadásához`Run` tárgy.

#### K: Hozzáadható az áthúzott szöveg több szövegrészhez ugyanabban a bekezdésben?

 V: Igen, egy bekezdésben több szövegrészhez is hozzáadhat áthúzott szöveget, ha több elemet használ`Run` tárgyakat. Többet is létrehozhat`Run` objektumok és állítsa be a`Font.StrikeThrough`tulajdonát`true` minden objektumhoz hozzá kell adni az áthúzott szöveget a kívánt szövegrészekhez. Ezután hozzáadhatja őket a bekezdéshez a`Paragraph.AppendChild(run)` módszer.

#### K: Hozzáadhatok áthúzott szöveget az Aspose.Words táblázatában vagy cellájában lévő szöveghez?

 V: Igen, hozzáadhat áthúzott szöveget az Aspose.Words táblázatában vagy cellájában lévő szöveghez. A megfelelő módszerekkel ugorhat a kívánt cellára vagy bekezdésre, majd alkalmazhatja az áthúzott szövegformázást a segítségével`Font.StrikeThrough` tulajdona a`Run` vagy`Paragraph` tárgy.