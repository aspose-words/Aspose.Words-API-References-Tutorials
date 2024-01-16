---
title: Soron belüli kép beszúrása Word dokumentumba
linktitle: Soron belüli kép beszúrása Word dokumentumba
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be sorközi képeket Word dokumentumokba az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/add-content-using-documentbuilder/insert-inline-image/
---
Ebből az átfogó oktatóanyagból megtudhatja, hogyan illeszthet be sorközi képeket egy Word-dokumentumba az Aspose.Words for .NET használatával. Végigvezetjük a folyamaton, és biztosítjuk a szükséges C# kódrészleteket. Az útmutató végére képeket közvetlenül hozzáadhat a dokumentumok szövegéhez.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Az Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Hozzon létre egy új dokumentumot és DocumentBuildert
Kezdésként hozzon létre egy új dokumentumot a Document osztály használatával, és inicializáljon egy DocumentBuilder objektumot:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Szúrjon be egy soron belüli képet
Ezután a DocumentBuilder osztály InsertImage metódusával illesszen be egy soros képet a dokumentumba. Paraméterként adja meg a képfájl elérési útját:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## 3. lépés: Mentse el a dokumentumot
A soros kép beszúrása után mentse a dokumentumot fájlba a Dokumentum osztály Mentés metódusával:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Példa forráskódra a soron belüli kép beszúrásához az Aspose.Words for .NET használatával
Íme a teljes forráskód egy soron belüli kép beszúrásához az Aspose.Words for .NET használatával:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan illeszthet be sorközi képeket egy Word-dokumentumba az Aspose.Words for .NET segítségével. A lépésenkénti útmutató követésével és a mellékelt forráskód felhasználásával zökkenőmentesen hozzáadhat képeket a dokumentumok szövegéhez.

A beágyazott képek különféle forgatókönyvek esetén hasznosak, például illusztrációk, logók vagy más vizuális elemek közvetlenül a dokumentumfolyamatba való hozzáadásához.

### GYIK a szövegközi kép Word dokumentumba történő beszúrásához

#### K: Átméretezhetem a beágyazott képeket a Word dokumentumban?

V: Igen, átméretezheti a soron belüli képeket az Aspose.Words for .NET használatával. A kép beszúrása után módosíthatja a méretét a képet reprezentáló Shape objektum szélességének és magasságának beállításával.

#### K: Lehetséges-e alternatív szöveget hozzáadni a soron belüli képekhez kisegítő okokból?

V: Igen, a kisegítő lehetőségek javítása érdekében alternatív szöveget is hozzáadhat a soron belüli képekhez. Az Aspose.Words for .NET támogatja az alternatív szövegek hozzáadását a képekhez, lehetővé téve a képernyőolvasók és más segítő technológiák számára a képtartalom leírását a látássérült felhasználók számára.

#### K: Alkalmazhatok formázást vagy stílusokat a soron belüli képekre?

V: Abszolút! Az Aspose.Words for .NET kiterjedt formázási lehetőségeket kínál a beágyazott képekhez. Különféle stílusokat, szegélyeket, effektusokat és egyéb formázási attribútumokat alkalmazhat a képeken, hogy illeszkedjen a dokumentum vizuális tervéhez.

#### K: Az Aspose.Words for .NET támogatja a képek beszúrását adatfolyamból vagy bájttömbből?

V: Igen, az Aspose.Words for .NET segítségével beszúrhat soron belüli képeket adatfolyamokból vagy bájttömbökből. Ez lehetővé teszi, hogy külső forrásból vagy dinamikusan generált képekkel dolgozzon.

#### K: Beszúrhatok képeket a szöveges tartalom bizonyos helyeire?

V: Igen, az Aspose.Words for .NET DocumentBuilder osztálya precízen szabályozza a soron belüli képek beillesztési helyzetét. Megadhatja a szövegben a pontos helyet, ahová a képet be kell illeszteni.