---
title: Nyissa meg a Type Features
linktitle: Nyissa meg a Type Features
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan engedélyezheti és használhatja az Aspose.Words for .NET Open Type szolgáltatásait
type: docs
weight: 10
url: /hu/net/enable-opentype-features/open-type-features/
---

Ebből az átfogó oktatóanyagból megtudhatja, hogyan engedélyezheti és használhatja az Aspose.Words for .NET Open Type funkcióit. Végigvezetjük a folyamaton, és biztosítjuk a szükséges C# kódrészleteket. Ennek az útmutatónak a végére képes lesz dolgozni a Word-dokumentumok Open Type funkcióival.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Töltse be a dokumentumot
Kezdésként töltse be a dokumentumot a Dokumentum osztály segítségével:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## 2. lépés: Engedélyezze az Open Type funkciókat
Az Open Type szolgáltatások engedélyezéséhez állítsa be a LayoutOptions osztály TextShaperFactory tulajdonságát a kívánt szövegalakító gyár példányára. Ebben a példában a HarfBuzzTextShaperFactory-t használjuk:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## 3. lépés: Mentse el a dokumentumot
Az Open Type funkciók engedélyezése után mentse a dokumentumot a kívánt kimeneti formátumban, például PDF-ben:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Példa forráskód nyílt típusú szolgáltatásokhoz az Aspose.Words for .NET használatával
Íme a teljes forráskód az Aspose.Words for .NET Open Type funkcióinak használatához:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan engedélyezheti és használhatja az Aspose.Words for .NET Open Type szolgáltatásait. A lépésenkénti útmutató követésével és a mellékelt forráskód felhasználásával most már használhatja a Word-dokumentumok Open Type funkcióit.

Az Open Type funkciók továbbfejlesztett tipográfiai és szövegformálási lehetőségeket kínálnak, így tetszetős és professzionális megjelenésű dokumentumokat hozhat létre. Kísérletezzen különböző szövegformáló gyárakkal, és fedezze fel projektjeiben az Open Type funkciók lehetőségeit.

### GYIK

#### K: Hogyan engedélyezhetem az OpenType-szolgáltatásokat az Aspose.Words for .NET-ben?

V: Az Aspose.Words for .NET OpenType szolgáltatásainak engedélyezéséhez kövesse az oktatóanyagban említett lépéseket.

#### K: Milyen OpenType-szolgáltatásokat támogat az Aspose.Words for .NET?

V: Az Aspose.Words for .NET számos OpenType szolgáltatást támogat, például ligatúrákat, karakterjel-változatokat, kontextus szerinti helyettesítéseket és egyebeket.

#### K: Hogyan ellenőrizhetem, hogy egy adott betűtípus támogatja-e az OpenType szolgáltatást?

V: Ellenőrizheti, hogy egy OpenType szolgáltatás támogatott-e egy adott betűtípusban a következővel`Font.OpenTypeFeatures` metódus az Aspose.Words for .NET-ben.

#### K: Milyen egyéb szövegformázási funkciókat támogat az Aspose.Words for .NET?

V: Az OpenType-szolgáltatásokon kívül az Aspose.Words for .NET más szövegformázási funkciókat is támogat, mint például a bekezdések formázása, táblázatok létrehozása, képek hozzáadása stb.

#### K: Használhatom az OpenType szolgáltatásait az Aspose.Words for .NET összes verziójában?

V: Az OpenType-szolgáltatásokat az Aspose.Words for .NET újabb verziói támogatják. Győződjön meg arról, hogy kompatibilis verziót használ, hogy élvezhesse ezeket a funkciókat.