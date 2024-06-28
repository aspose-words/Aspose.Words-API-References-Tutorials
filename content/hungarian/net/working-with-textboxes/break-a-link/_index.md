---
title: Hivatkozás előretörése a Word-dokumentumban
linktitle: Hivatkozás előretörése a Word-dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan bonthat tovább hivatkozásokat egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-textboxes/break-a-link/
---

Az Aspose.Words for .NET egy hatékony könyvtár, amely különféle funkciókat kínál a Microsoft Word dokumentumok programozott szövegfeldolgozásához. Egyik hasznos funkciója, hogy képes áttörni a Word dokumentumban lévő hivatkozásokat. Ebben az oktatóanyagban megvizsgáljuk a C# nyelvű forráskódot, amely bemutatja, hogyan lehet áttörni az előremutató hivatkozást Word dokumentumban az Aspose.Words for .NET használatával.

## 1. lépés: C# forráskód előnézete

A mellékelt C# forráskód az Aspose.Words for .NET "Break A Link" funkciójára összpontosít. Megmutatja, hogyan lehet megtörni egy hivatkozást egy szövegdoboz alakzatban egy dokumentumon belül. A kód különböző forgatókönyveket mutat be a linkek megszakítására, és egyértelmű utasításokat ad a kívánt eredmények elérésére vonatkozóan.

## 2. lépés: A dokumentum beállítása és egy TextBox alakzat létrehozása

 A kezdéshez be kell állítani a dokumentumot, és létre kell hoznunk egy TextBox alakzatot. A következő kód inicializálja a`Document` osztályt, és létrehoz egy szövegdoboz alakzatot:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## 3. lépés: Bontsa át a hivatkozást a TextBoxban

 Egy továbbító hivatkozás megszakításához a TextBoxban használhatjuk a`BreakForwardLink()` módszer. Ez a módszer megszakítja a hivatkozást a sorozat következő alakzatára. A következő kód megmutatja, hogyan szakíthat meg egy továbbító hivatkozást:

```csharp
textBox.BreakForwardLink();
```

## 4. lépés: Szakítsa meg az előre irányuló kapcsolatot null érték beállításával

 Alternatív megoldásként megszakíthatjuk a továbbító hivatkozást a TextBox beállításával`Next`tulajdonát`null`. Ez hatékonyan eltávolítja a kapcsolatot a következő alakzattal. A következő kód ezt a megközelítést mutatja be:

```csharp
textBox. Next = null;
```

## 5. lépés: Törje meg a TextBoxhoz vezető hivatkozást

 Bizonyos esetekben meg kell szakítanunk egy hivatkozást, amely a TextBox alakzathoz vezet. Ezt úgy érhetjük el, hogy felhívjuk a`BreakForwardLink()` módszer a`Previous` űrlapot, amely megszakítja a TextBoxra mutató hivatkozást. Íme egy példa egy ilyen hivatkozás megszakítására:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Minta forráskód az Aspose.Words for .NET-hez való hivatkozás megszakításához

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Bontsa tovább a linket.
textBox.BreakForwardLink();

// Egy null érték beállításával szakítsa meg az előre irányuló kapcsolatot.
textBox. Next = null;

// Törj meg egy linket, amely ehhez a szövegmezőhöz vezet.
textBox.Previous?.BreakForwardLink();
```

## Következtetés

Gratulálok ! Most megtanulta, hogyan bonthatja meg az átirányítási hivatkozásokat egy Word-dokumentumban a .NET Aspose.Words könyvtárával. Az útmutató lépéseit követve különböző módszerekkel beállíthatta a dokumentumot, létrehozhat egy TextBox alakzatot, és megszakította az átirányítási hivatkozásokat.

### GYIK a Word dokumentumban található továbbítási hivatkozáshoz

#### K: Mi az a könyvtár, amely az Aspose.Words for .NET segítségével megtöri az átirányítási hivatkozásokat egy Word-dokumentumban?

V: A Word-dokumentumban az Aspose.Words for .NET használatával történő átirányítási hivatkozások megszakításához a használt könyvtár az Aspose.Words for .NET.

#### K: Hogyan lehet megtörni egy átirányítási hivatkozást a TextBoxban?

 V: A szövegdobozban lévő továbbítási hivatkozás megszakításához használja a`BreakForwardLink()` módszer. Ez a módszer megszakítja a hivatkozást a sorozat következő alakzatára.

#### K: Hogyan lehet megszakítani az átirányítási hivatkozást null érték beállításával?

V: Alternatív megoldásként megszakíthatja az átirányítási hivatkozást a`Next` a TextBox tulajdonsága`null`. Ez hatékonyan eltávolítja a kapcsolatot a következő alakzattal.

#### K: Hogyan lehet megtörni egy hivatkozást, amely a TextBoxhoz vezet?

 V: Bizonyos esetekben meg kell szakítania egy hivatkozást, amely a TextBoxhoz vezet. Ezt úgy érheti el, hogy hívja a`BreakForwardLink()` módszer a`Previous` űrlapot, amely megszakítja a TextBoxra mutató hivatkozást.

#### K: Megtörhetjük az átirányítási hivatkozásokat a TextBoxokon kívüli elemeken?

V: Igen, az Aspose.Words for .NET segítségével megtörheti az átirányítási hivatkozásokat különböző elemeken, például bekezdéseken, táblázatokon, képeken stb. A folyamat attól függően változhat, hogy melyik elemen szeretné megszakítani a hivatkozást.