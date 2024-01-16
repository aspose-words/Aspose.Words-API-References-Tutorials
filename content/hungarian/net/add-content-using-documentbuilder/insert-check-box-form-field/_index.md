---
title: Helyezze be a jelölőnégyzet űrlapmezőjét a Word dokumentumba
linktitle: Helyezze be a jelölőnégyzet űrlapmezőjét a Word dokumentumba
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be jelölőnégyzet-űrlapmezőket Word dokumentumokba az Aspose.Words for .NET használatával. Lépésről lépésre útmutató.
type: docs
weight: 10
url: /hu/net/add-content-using-documentbuilder/insert-check-box-form-field/
---
Ebből az átfogó oktatóanyagból megtudhatja, hogyan szúrhat be egy jelölőnégyzet űrlapmezőt egy Word-dokumentumba az Aspose.Words for .NET használatával. Végigvezetjük a folyamaton, és biztosítjuk a szükséges C# kódrészleteket. Az útmutató végére testreszabható tulajdonságokkal rendelkező jelölőnégyzetes űrlapmezőket adhat a dokumentumaihoz.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Az Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Hozzon létre egy új dokumentumot és DocumentBuildert
Kezdésként hozzon létre egy új dokumentumot a Document osztály használatával, és inicializáljon egy DocumentBuilder objektumot:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Szúrjon be egy jelölőnégyzet űrlapmezőt
Ezután használja a DocumentBuilder osztály InsertCheckBox metódusát egy jelölőnégyzet űrlapmező beszúrásához. Adja meg argumentumként a nevet, az ellenőrzött állapotot, az alapértelmezett állapotot és a méretet:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## 3. lépés: Mentse el a dokumentumot
A jelölőnégyzet űrlapmezőjének beszúrása után mentse a dokumentumot fájlba a Dokumentum osztály Mentés metódusával:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### Példa forráskódra a jelölőnégyzet beszúrása űrlapmezőhöz az Aspose.Words for .NET használatával
Íme a teljes forráskód egy jelölőnégyzet űrlapmező beszúrásához az Aspose.Words for .NET használatával:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertCheckBox("CheckBox", true, true, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

Ne felejtse el beállítani a kódot saját igényei szerint, és szükség szerint bővítse további funkciókkal.

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan illesszen be jelölőnégyzet űrlapmezőt egy Word-dokumentumba az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód felhasználásával mostantól interaktív jelölőnégyzet-űrlapmezőkkel bővítheti dokumentumait.

### GYIK

#### K: Beilleszthetek több jelölőnégyzet űrlapmezőt egyetlen dokumentumba?

V: Abszolút! Az Aspose.Words for .NET használatával tetszőleges számú jelölőnégyzet űrlapmezőt szúrhat be egy Word-dokumentumba. Egyszerűen ismételje meg a beillesztési folyamatot több interaktív jelölőnégyzet hozzáadásához.

#### K: Beállíthatom a jelölőnégyzet űrlapmezőjének kezdeti állapotát (pipálva vagy nem jelölve)?

V: Igen, teljes ellenőrzése alatt áll a jelölőnégyzet űrlapmezőjének kezdeti állapota felett. Az ellenőrzött állapot paraméter igaz vagy hamis értékre állításával meghatározhatja, hogy a jelölőnégyzet kezdetben be legyen jelölve vagy nincs bejelölve.

#### K: A jelölőnégyzet űrlapmezői kompatibilisek más fájlformátumokkal, például PDF-formátummal?

V: Igen, az Aspose.Words for .NET segítségével beszúrt jelölőnégyzetes űrlapmezők különféle fájlformátumokkal kompatibilisek, beleértve a DOCX-et és a PDF-t. Ez lehetővé teszi a dokumentumok exportálását különböző formátumokba az interaktív jelölőnégyzetek megtartása mellett.

#### K: Beállíthatom a jelölőnégyzet űrlapmezőjének méretét?

V: Természetesen! A jelölőnégyzet űrlapmezőjének méretét az InsertCheckBox metódus mérete paraméterével adhatja meg. Ez lehetővé teszi a jelölőnégyzet méreteinek szabályozását a tervezési preferenciái szerint.

#### K: Az Aspose.Words for .NET alkalmas asztali és webes alkalmazásokhoz is?

V: Igen, az Aspose.Words for .NET egy sokoldalú könyvtár, amely asztali és webes alkalmazásokhoz egyaránt alkalmas. Akár Windows-alkalmazást, akár webalapú rendszert épít, a könyvtárat könnyedén integrálhatja.