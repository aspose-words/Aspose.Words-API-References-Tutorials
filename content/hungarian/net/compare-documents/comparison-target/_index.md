---
title: Összehasonlítási cél a Word dokumentumban
linktitle: Összehasonlítási cél a Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg a cél összehasonlítását az Aspose.Words for .NET Word dokumentum funkciójában, amely lehetővé teszi a dokumentumok összehasonlítását, és a végrehajtott módosításokat tartalmazó új dokumentum létrehozását.
type: docs
weight: 10
url: /hu/net/compare-documents/comparison-target/
---
Itt található egy lépésről lépésre bemutatott útmutató a C# forráskód leírásához, amely az Aspose.Words for .NET Word dokumentum funkciójában az összehasonlítási célt használja.

## 1. lépés: Bevezetés

Az Aspose.Words for .NET célösszehasonlító funkciója lehetővé teszi két dokumentum összehasonlítását, és új dokumentum létrehozását, amely tartalmazza a céldokumentum módosításait. Ez hasznos lehet a dokumentum különböző verziói között végrehajtott változtatások nyomon követéséhez.

## 2. lépés: A környezet beállítása

Mielőtt elkezdené, be kell állítania a fejlesztői környezetet az Aspose.Words for .NET használatához. Győződjön meg arról, hogy telepítve van az Aspose.Words könyvtár, és van egy megfelelő C# projekt a kód beágyazásához.

## 3. lépés: Adja hozzá a szükséges összeállításokat

Az Aspose.Words for .NET összehasonlító célszolgáltatásának használatához hozzá kell adnia a szükséges összeállításokat a projekthez. Győződjön meg arról, hogy megfelelő hivatkozásokat tartalmaz az Aspose.Words-re a projektben.

```csharp
using Aspose.Words;
```

## 4. lépés: Dokumentum inicializálása

Ebben a lépésben két dokumentumot inicializálunk összehasonlítás céljából. Meg kell adnia a könyvtár elérési útját, ahol a dokumentumok találhatók, valamint a forrásdokumentum nevét.

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Az A dokumentum inicializálása az összehasonlításhoz.
Document docA = new Document(dataDir + "DocumentA.docx");

// Az A dokumentum klónozása a B dokumentum azonos másolatának létrehozásához.
Document docB = docA.Clone();
```

## 5. lépés: Összehasonlítási beállítások konfigurálása

Ebben a lépésben konfiguráljuk az összehasonlítási beállításokat, hogy meghatározzuk az összehasonlítás viselkedését. A lehetőségek között szerepel a formázás figyelmen kívül hagyása, valamint az összehasonlítási cél, amely a Microsoft Word „Dokumentumok összehasonlítása” párbeszédpaneljének „Változások megjelenítése” opciója.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## 6. lépés: Dokumentumok összehasonlítása

Most összehasonlítjuk a dokumentumokat, és létrehozzuk az eredményt egy új dokumentumban.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 A`Compare`módszer összehasonlítja az A dokumentumot a B dokumentummal, és elmenti az A dokumentum módosításait. Referenciaként megadhatja a felhasználónevet és az összehasonlítás dátumát.

### Minta forráskód a Comparison Targethez az Aspose.Words for .NET használatával


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// A Microsoft Word „Változások megjelenítése” opciójához kapcsolódik a „Dokumentumok összehasonlítása” párbeszédpanelen.
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Következtetés

Ebben a cikkben megvizsgáltuk az Aspose.Words for .NET diff target funkcióját. Ez a funkció lehetővé teszi két dokumentum összehasonlítását, és egy új dokumentum létrehozását, amely tartalmazza a végrehajtott módosításokat. Ezt a tudást felhasználhatja a dokumentumok különböző verziói közötti változások nyomon követésére.

### GYIK

#### K: Mi a célja a Comparison Target használatának az Aspose.Words for .NET-ben?

V: Összehasonlítási cél az Aspose.Words for .NET-ben lehetővé teszi két dokumentum összehasonlítását, és egy új dokumentum létrehozását, amely tartalmazza a céldokumentum módosításait. Ez a funkció a dokumentum különböző verziói között végrehajtott változtatások nyomon követéséhez és a különbségek külön dokumentumban való megjelenítéséhez hasznos.

#### K: Hogyan használhatom az Összehasonlítási célt az Aspose.Words for .NET-ben?

V: A Comparison Target használatához az Aspose.Words for .NET-ben, kövesse az alábbi lépéseket:
1. Állítsa be fejlesztői környezetét az Aspose.Words könyvtárral.
2. Adja hozzá a szükséges összeállításokat a projekthez az Aspose.Words hivatkozással.
3.  Inicializálja az összehasonlítani kívánt dokumentumokat a segítségével`Document` osztály vagy a`DocumentBuilder` osztály.
4.  Konfigurálja az összehasonlítási beállításokat a létrehozásával`CompareOptions` objektum és beállítás tulajdonságai, mint pl`IgnoreFormatting` és`Target` (például,`ComparisonTargetType.New` összehasonlítási célhoz).
5.  Használja a`Compare` módszer az egyik dokumentumon, átadva a másik dokumentumot és a`CompareOptions` objektum paraméterként. Ez a módszer összehasonlítja a dokumentumokat, és elmenti a módosításokat az első dokumentumban.

####  K: Mi a célja a`Target` property in the `CompareOptions` class?

 V: A`Target` ingatlan a`CompareOptions` osztály lehetővé teszi az összehasonlítási cél megadását, amely hasonló a Microsoft Word "Dokumentumok összehasonlítása" párbeszédpaneljének "Változások megjelenítése" opciójához. A cél beállítható`ComparisonTargetType.New` új dokumentum változásainak megjelenítéséhez,`ComparisonTargetType.Current` az aktuális dokumentum változásainak megjelenítéséhez, vagy`ComparisonTargetType.Formatting` hogy csak a formázási változások jelenjenek meg.