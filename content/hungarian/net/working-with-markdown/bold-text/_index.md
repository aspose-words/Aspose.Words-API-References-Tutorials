---
title: Félkövér szöveg
linktitle: Félkövér szöveg
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan lehet félkövéren szedni a szöveget az Aspose.Words for .NET segítségével Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/bold-text/
---

Ebben a példában bemutatjuk, hogyan lehet félkövér szöveget szedni az Aspose.Words for .NET segítségével. A félkövér szöveg láthatóbbá teszi, és jobban kiemeli.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. lépés: Félkövér szöveg

 A szöveget félkövérre szedhetjük a dokumentumkészítő beállításával`Font.Bold`tulajdonát`true`.

```csharp
builder.Font.Bold = true;
```

## 3. lépés: Adjon hozzá tartalmat a dokumentumhoz

 Most már a dokumentumkészítő módszerekkel tudunk tartalmat hozzáadni a dokumentumhoz, mint pl`Writeln`, amely egy sor szöveget ad hozzá.

```csharp
builder.Writeln("This text will be bold");
```

## Példa forráskód félkövér szöveghez az Aspose.Words for .NET használatával


```csharp
// Használjon dokumentumkészítőt, hogy tartalmat adjon a dokumentumhoz.
DocumentBuilder builder = new DocumentBuilder();

// Tegye félkövérre a szöveget.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Gratulálok ! Most megtanulta, hogyan lehet félkövér szöveget szedni az Aspose.Words for .NET segítségével.


### GYIK

#### K: Hogyan tudom félkövérre szedni a szöveget az Aspose.Words-ben?

 V: Az Aspose.Words szövegének félkövérré tételéhez használhatja a`Font.Bold` tulajdona a`Run` tárgy. Beállíthatja ezt a tulajdonságot`true` félkövér konkrét szöveghez. Például használhatja`run.Font.Bold=true` hogy vastagon szedje a szöveg belsejében`Run` tárgy.

#### K: Lehetséges ugyanabban a bekezdésben több szövegrész félkövér szedése?

 V: Igen, egy bekezdésben több szövegrészt is félkövérre szedhet, ha több szöveget használ`Run` tárgyakat. Többet is létrehozhat`Run` objektumok és állítsa be a`Font.Bold`tulajdonát`true` hogy minden objektum félkövérre szedje a kívánt szövegrészeket. Ezután hozzáadhatja őket a bekezdéshez a`Paragraph.AppendChild(run)` módszer.

#### K: Félkövérrel szedhetek olyan szöveget, amely az Aspose.Words táblázatában vagy cellájában található?

 V: Igen, az Aspose.Words táblázatában vagy cellájában lévő szöveget félkövéren szedheti. A megfelelő módszerekkel navigálhat a kívánt cellához vagy bekezdéshez, majd alkalmazhatja a félkövér formázást a gombbal`Font.Bold` tulajdona a`Run` vagy`Paragraph` tárgy.