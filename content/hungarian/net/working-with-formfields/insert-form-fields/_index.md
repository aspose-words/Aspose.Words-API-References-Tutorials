---
title: Űrlapmezők beszúrása
linktitle: Űrlapmezők beszúrása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szúrhat be legördülő űrlapmezőket Word dokumentumokba az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-formfields/insert-form-fields/
---

Ebben a lépésenkénti oktatóanyagban bemutatjuk, hogyan illeszthet be űrlapmezőket, különösen egy legördülő űrlapmezőt egy Word-dokumentumba az Aspose.Words for .NET használatával. Elmagyarázzuk a mellékelt C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe.

 A kezdéshez győződjön meg arról, hogy az Aspose.Words for .NET telepítve van és be van állítva a fejlesztői környezetben. Ha még nem tette meg, töltse le és telepítse a könyvtárat innen[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. lépés: A Document és a DocumentBuilder objektumok inicializálása

 Először inicializálja a`Document` és`DocumentBuilder` objektumok:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Legördülő űrlapmező beszúrása

 Ezután adja meg a legördülő űrlapmező beállításait, és szúrja be a dokumentumba a gombbal`InsertComboBox` módszere a`DocumentBuilder` tárgy. Ebben a példában beszúrunk egy „Legördülő” nevű legördülő űrlapmezőt három lehetőséggel: „Egy”, „Két” és „Három”:

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## 3. lépés: A dokumentum mentése

Végül mentse el a dokumentumot:

```csharp
doc.Save("OutputDocument.docx");
```

Ez az! Sikeresen beszúrt egy legördülő űrlapmezőt egy Word-dokumentumba az Aspose.Words for .NET használatával.

### Példa a Form Fields beszúrása Aspose.Words for .NET forráskódjához

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

Nyugodtan használja ezt a kódot saját projektjeiben, és módosítsa saját igényei szerint.

### GYIK

#### K: Hogyan illeszthetek be szöveges űrlapmezőt az Aspose.Words-be?

 V: Ha szöveges űrlapmezőt szeretne beszúrni az Aspose.Words-be, használja a`FormField` osztályt, és állítsa be`Type`tulajdonát`FormFieldType.Text`. Más tulajdonságokat, például nevet, címkét és beállításokat is személyre szabhat.

#### K: Létre lehet hozni egy jelölőnégyzet típusú űrlapmezőt egy dokumentumban?

 V: Igen, lehetőség van jelölőnégyzet típusú űrlapmező létrehozására egy Aspose.Words dokumentumban. Használhatja a`FormField` osztályt, és állítsa be`Type`tulajdonát`FormFieldType.CheckBox` jelölőnégyzet létrehozásához. Ezután szükség szerint testreszabhatja a jelölőnégyzet tulajdonságait.

#### K: Hogyan adhatok hozzá egy legördülő típusú űrlapmezőt egy dokumentumhoz?

 V: Ha egy Aspose.Words dokumentumhoz legördülő típusú űrlapmezőt szeretne hozzáadni, használja a`FormField` osztályt, és állítsa be`Type`tulajdonát`FormFieldType.DropDown` . Ezután beállíthatja a legördülő menü beállításait a`DropDownItems` ingatlan.

#### K: Beállíthatok alapértelmezett értéket az Aspose.Words űrlapmezőjéhez?

V: Igen, beállíthat alapértelmezett értéket az Aspose.Words űrlapmezőjéhez. Használja a`FormField.Result` tulajdonság megadásához az űrlapmező kezdeti értékét.

#### K: Hogyan kérhetem le az Aspose.Words űrlapmezőiben megadott adatokat?

 V: Az Aspose.Words űrlapmezőiben megadott adatok lekéréséhez használhatja a`FormField.Result` tulajdonság, amely a felhasználó által beírt értéket tartalmazza. Ezt a tulajdonságot a dokumentum minden űrlapmezőjéhez érheti el.