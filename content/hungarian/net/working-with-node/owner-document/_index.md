---
title: Tulajdonosi dokumentum
linktitle: Tulajdonosi dokumentum
second_title: Aspose.Words Document Processing API
description: Ismerje meg a tulajdonosi dokumentum használatát az Aspose.Words for .NET-ben.
type: docs
weight: 10
url: /hu/net/working-with-node/owner-document/
---

Itt található egy lépésről lépésre bemutatott útmutató a C# forráskód leírásához, amely bemutatja, hogyan használhatja a szabadalmaztatott dokumentumfunkciókat az Aspose.Words for .NET-hez.

## 1. lépés: Importálja a szükséges referenciákat
Mielőtt elkezdené, győződjön meg arról, hogy importálta az Aspose.Words for .NET használatához szükséges hivatkozásokat a projektbe. Ez magában foglalja az Aspose.Words könyvtár importálását és a szükséges névterek hozzáadását a forrásfájlhoz.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## 2. lépés: Hozzon létre egy új dokumentumot
 Ebben a lépésben egy új dokumentumot hozunk létre a`Document` osztály.

```csharp
Document doc = new Document();
```

## 3. lépés: Hozzon létre egy csomópontot a tulajdonos dokumentumával
 Ha bármilyen típusú új csomópontot hoz létre, át kell adnia a dokumentumot a konstruktornak. Ebben a példában egy új bekezdés csomópontot hozunk létre a dokumentum segítségével`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## 4. lépés: Ellenőrizze a szülőcsomópontot és a tulajdonos dokumentumát
 Most, hogy létrehoztuk a bekezdés csomópontját, ellenőrizhetjük, hogy van-e szülőcsomópontja, és hogy a tulajdonos dokumentum megegyezik-e`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## 5. lépés: Módosítsa a csomópont tulajdonságait dokumentumadatokkal
A csomópont és a dokumentum közötti kapcsolat lehetővé teszi a dokumentum-specifikus adatokra, például stílusokra vagy listákra hivatkozó tulajdonságok elérését és módosítását. Ebben a példában a bekezdésstílus nevét "Címsor 1"-re állítjuk be.

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## 6. lépés: Adja hozzá a bekezdést a dokumentumhoz
Most hozzáadhatjuk a bekezdés csomópontját a dokumentum fő részéhez.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 7. lépés: Hozzáadás után ellenőrizze a szülőcsomópontot
Miután hozzáadtuk a bekezdést a dokumentumhoz, újra ellenőrizzük, hogy van-e szülőcsomópontja.

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### Minta forráskód a tulajdonosi dokumentumhoz az Aspose.Words for .NET segítségével

```csharp
Document doc = new Document();

// Bármilyen típusú új csomópont létrehozásához a konstruktorba átadott dokumentumra van szükség.
Paragraph para = new Paragraph(doc);

// Az új bekezdéscsomópontnak még nincs szülője.
Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

// De a bekezdés csomópontja ismeri a dokumentumát.
Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

// Az a tény, hogy egy csomópont mindig egy dokumentumhoz tartozik, lehetővé teszi számunkra a hozzáférést és a módosítást
// olyan tulajdonságok, amelyek a dokumentumszintű adatokra hivatkoznak, például stílusok vagy listák.
para.ParagraphFormat.StyleName = "Heading 1";

// Most adja hozzá a bekezdést az első szakasz fő szövegéhez.
doc.FirstSection.Body.AppendChild(para);

// A bekezdéscsomópont mostantól a Törzs csomópont gyermeke.
Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
```

### GYIK

#### K: Mi az a védett dokumentum a Node.js-ben?

V: A Node.js-ben lévő tulajdonosi dokumentum az az XML-dokumentum, amelyhez egy adott csomópont tartozik. A csomópontot tartalmazó XML-dokumentum példányát képviseli.

#### K: Hogyan szerezhető be egy csomópont tulajdonosi dokumentuma?

 V: A Node.js egyik csomópontjának tulajdonosi dokumentumának beszerzéséhez használja a`ownerDocument` a csomópont tulajdonsága. Ez a tulajdonság a csomópontot birtokló XML-dokumentumot adja vissza.

#### K: Mire használják a védett dokumentumot?

V: A tulajdonos dokumentumot egy csomópont globális kontextusának ábrázolására használják egy XML-dokumentumban. Hozzáférést biztosít a dokumentum más csomópontjaihoz, és lehetővé teszi a műveletek végrehajtását azokon.

#### K: Módosíthatjuk egy csomópont tulajdonosi dokumentumát?

V: A legtöbb esetben a csomópont dokumentumtulajdonosa a csomópont létrehozásakor kerül meghatározásra, és nem módosítható közvetlenül. A tulajdonos dokumentuma csak olvasható tulajdonság.

#### K: Hogyan lehet elérni a tulajdonos dokumentumának csomópontjait?

 V: A védett dokumentum csomópontjainak eléréséhez használhatja a Node.js környezetben használt XML API által biztosított módszereket és tulajdonságokat. Használhat például olyan módszereket, mint`getElementsByTagName` vagy`querySelector` adott csomópontok kiválasztásához a dokumentumban.