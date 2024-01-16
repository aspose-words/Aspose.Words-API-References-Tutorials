---
title: Szövegbeviteli űrlapmező beszúrása a Word dokumentumba
linktitle: Szövegbeviteli űrlapmező beszúrása a Word dokumentumba
second_title: Aspose.Words Document Processing API
description: Ebből a lépésenkénti útmutatóból megtudhatja, hogyan használhatja az Aspose.Words for .NET alkalmazást szövegbeviteli űrlapmezők beszúrásához Word dokumentumokba.
type: docs
weight: 10
url: /hu/net/add-content-using-documentbuilder/insert-text-input-form-field/
---
Ebben a lépésenkénti útmutatóban megvizsgáljuk, hogyan használható az Aspose.Words for .NET Szövegbeviteli űrlapmező beszúrása funkciója szövegbeviteli űrlapmezők hozzáadásához és kezeléséhez a Word-dokumentumokban C# forráskód használatával. A szövegbeviteli űrlapmezők lehetővé teszik a felhasználók számára, hogy egyéni szöveget írjanak be egy dokumentumba, így ideálisak interaktív űrlapok és kérdőívek létrehozásához. Az alábbi utasításokat követve könnyedén beillesztheti és testreszabhatja a szövegbeviteli űrlapmezőket a dokumentumokba. Kezdjük el!

## Bevezetés az Aspose.Words for .NET szövegbeviteli űrlapmező funkciójába

Az Aspose.Words for .NET Szövegbeviteli űrlapmező beszúrása funkciója lehetővé teszi szövegbeviteli űrlapmezők programozott hozzáadását a Word-dokumentumokhoz. Ezek az űrlapmezők interaktív elemet biztosítanak, ahol a felhasználók egyéni szöveget vagy adatokat írhatnak be.

## A funkció használatának követelményeinek megértése

Mielőtt folytatná a megvalósítást, győződjön meg arról, hogy megfelel a következő követelményeknek:

1. Aspose.Words for .NET könyvtár telepítve van a projektben.
2. C# programozási nyelv alapismerete.
3. Meglévő Word-dokumentum vagy új dokumentum a szövegbeviteli űrlapmező beillesztéséhez.

Győződjön meg arról, hogy megvannak ezek az előfeltételek a zökkenőmentes folytatáshoz.

## Útmutató lépésről lépésre a Szövegbeviteli űrlapmező beszúrása C# forráskód használatával történő megvalósításához

Kövesse az alábbi lépéseket a Szövegbeviteli űrlapmező beszúrása funkció megvalósításához a mellékelt C# forráskód használatával:

### 1. lépés: A dokumentum és a dokumentumkészítő inicializálása

A kezdéshez inicializálja a dokumentumot és a dokumentumkészítőt. A dokumentumkészítő az Aspose.Words for .NET által biztosított hatékony eszköz, amely lehetővé teszi Word-dokumentumok programozott létrehozását és kezelését. Használja a következő kódrészletet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### 2. lépés: Szövegbeviteli űrlapmező beszúrása

 Ezután a szövegbeviteli űrlapmezőt beszúrjuk a dokumentumba a`InsertTextInput` módszer. Ez a metódus különféle paramétereket fogad el, beleértve az űrlapmező nevét, az űrlapmező típusát (ebben az esetben`TextFormFieldType.Regular`), az alapértelmezett érték és a maximális hossz. Íme egy példa:

```csharp
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);
```

A fenti kód beszúr egy szövegbeviteli űrlapmezőt „TextInput” néven, alapértelmezett értéke „Hello”, és nincs maximális hosszkorlátozás.

### 3. lépés: A dokumentum mentése

 A szövegbeviteli űrlapmező beszúrása után mentse a dokumentumot a kívánt helyre a gombbal`Save` módszer. Ügyeljen arra, hogy megadja a megfelelő fájl elérési utat:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

Ez a kód elmenti a dokumentumot a beszúrt szövegbeviteli űrlapmezővel a megadott helyre.

### Példa forráskódra a Szövegbeviteli űrlapmező beszúrásához az Aspose.Words for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan lehet szövegbeviteli űrlapmezőket beszúrni és testreszabni egy Word-dokumentumban az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt C# forráskód használatával interaktív elemeket adhat a dokumentumaihoz, lehetővé téve a felhasználók számára, hogy egyéni szöveget vagy adatokat vigyenek be.

### GYIK a szövegbeviteli űrlapmező beszúrásához a Word dokumentumban

#### K: Mi a célja az Aspose.Words for .NET szövegbeviteli űrlapmezőjének funkciójának?

V: Az Aspose.Words for .NET-ben található Szövegbeviteli űrlapmező beszúrása funkciója lehetővé teszi szövegbeviteli űrlapmezők programozott hozzáadását a Word-dokumentumokhoz. Ezek az űrlapmezők lehetővé teszik a felhasználók számára, hogy egyéni szöveget vagy adatokat vigyenek be közvetlenül a dokumentumba, így ideálisak interaktív űrlapok, felmérések vagy kérdőívek létrehozásához.

#### K: Mik a Szövegbeviteli űrlapmező beszúrása funkció használatának előfeltételei?

V: A Szövegbeviteli űrlapmező beszúrása funkció megvalósítása előtt biztosítania kell a következő előfeltételeket:
1. Aspose.Words for .NET könyvtár telepítve van a projektben.
2. C# programozási nyelv alapismerete.
3. Meglévő Word-dokumentum vagy új dokumentum, amelybe be szeretné szúrni a szövegbeviteli űrlapmezőt.

#### K: Hogyan szabhatom testre a szövegbeviteli űrlapmezőt?

 V: Testreszabhatja a szövegbeviteli űrlapmezőt, ha meghatározott paramétereket ad meg a hívásakor`InsertTextInput`módszer. Például szükség szerint beállíthatja az űrlapmező nevét, alapértelmezett értékét és maximális hosszát.

#### K: Beszúrhatok több szövegbeviteli űrlapmezőt egyetlen dokumentumba?

 V: Igen, több szövegbeviteli űrlapmezőt is beszúrhat egyetlen dokumentumba. Egyszerűen hívja a`InsertTextInput` metódus különböző nevekkel és konfigurációkkal több űrlapmező hozzáadásához.

#### K: Hogyan használhatják a felhasználók a dokumentum szövegbeviteli űrlapmezőjét?

V: Miután a szövegbeviteli űrlapmezőt beszúrta a dokumentumba, a felhasználók rákattinthatnak az űrlapmezőre, és elkezdhetik a gépelést az egyéni szöveg beviteléhez. Az űrlapmező segítségével közvetlenül a dokumentumon belül szerkeszthetik a tartalmat.