---
title: Vízszintes szabály beszúrása Word dokumentumba
linktitle: Vízszintes szabály beszúrása Word dokumentumba
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be vízszintes szabályokat Word dokumentumokba az Aspose.Words for .NET használatával. Lépésről lépésre útmutató.
type: docs
weight: 10
url: /hu/net/add-content-using-documentbuilder/insert-horizontal-rule/
---
Ebből az átfogó példából megtudhatja, hogyan illeszthet be vízszintes szabályt egy Word-dokumentumba az Aspose.Words for .NET használatával. Végigvezetjük a folyamaton, és biztosítjuk a szükséges C# kódrészleteket. Az útmutató végére vízszintes szabályokat adhat a dokumentumokhoz a vizuális elkülönítés és rendszerezés érdekében.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Az Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Hozzon létre egy új dokumentumot és DocumentBuildert
Kezdésként hozzon létre egy új dokumentumot a Document osztály használatával, és inicializáljon egy DocumentBuilder objektumot:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Szúrjon be egy vízszintes szabályt
Ezután használja a DocumentBuilder osztály Writeln metódusát egy leíró szöveg hozzáadásához, majd szúrjon be egy vízszintes szabályt:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## 3. lépés: Mentse el a dokumentumot
A vízszintes szabály beszúrása után mentse a dokumentumot fájlba a Dokumentum osztály Mentés metódusával:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Példa forráskód a vízszintes szabály beszúrásához az Aspose.Words for .NET használatával
Íme a teljes forráskód vízszintes szabály beszúrásához az Aspose.Words for .NET használatával:
A vízszintes szabályok különféle forgatókönyveknél hasznosak, például szakaszok felosztása, vizuális törések létrehozása vagy fontos információk kiemelése.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Ne felejtse el beállítani a kódot saját igényei szerint, és szükség szerint bővítse további funkciókkal.

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan lehet vízszintes szabályt beszúrni egy Word-dokumentumba az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód használatával most már vizuálisan elkülönítheti és rendezheti dokumentumait vízszintes szabályok segítségével.

### GYIK a vízszintes szabály beszúrásához a Word dokumentumban

#### K: Testreszabhatom a vízszintes szabály megjelenését?

V: Igen, feltétlenül! Az Aspose.Words for .NET különféle tulajdonságokat biztosít a vízszintes szabály megjelenésének testreszabásához. Beállíthatja szélességét, magasságát, igazítását, színét és árnyékolását, hogy megfeleljen a dokumentum esztétikájának.

#### K: Hozzáadhatok több vízszintes szabályt egyetlen dokumentumhoz?

V: Természetesen! Az Aspose.Words for .NET használatával tetszőleges számú vízszintes szabályt illeszthet be egy Word-dokumentumba. Egyszerűen ismételje meg a beillesztési folyamatot több vizuális törés vagy szakaszelválasztó hozzáadásához.

#### K: Kompatibilisek a vízszintes szabályok más fájlformátumokkal, például a PDF-formátummal?

V: Igen, az Aspose.Words for .NET segítségével beszúrt vízszintes szabályok különféle fájlformátumokkal kompatibilisek, beleértve a DOCX-et és a PDF-t. Ez azt jelenti, hogy a dokumentumokat különböző formátumokban exportálhatja, miközben megtartja a vízszintes szabályokat.

#### K: Beilleszthetek-e programozottan vízszintes szabályt a dokumentum adott helyeire?

V: Abszolút! Az Aspose.Words for .NET lehetővé teszi, hogy a vízszintes szabályt a dokumentum meghatározott helyeire programozottan helyezze el. Elhelyezését a dokumentum tartalma és szerkezete alapján szabályozhatja.

#### K: Az Aspose.Words for .NET alkalmas asztali és webes alkalmazásokhoz is?

V: Igen, az Aspose.Words for .NET sokoldalú, és asztali és webes alkalmazásokban is használható. Akár Windows-alkalmazást, akár webalapú rendszert épít, a könyvtárat könnyedén integrálhatja.