---
title: Másolja a fejlécek lábléceit az előző szakaszból
linktitle: Másolja a fejlécek lábléceit az előző szakaszból
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan másolhat fejlécet és láblécet a Word dokumentumok előző szakaszából az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

Ebben a lépésenkénti oktatóanyagban bemutatjuk, hogyan másolhat fejlécet és láblécet az előző szakaszból egy Word-dokumentumba az Aspose.Words for .NET használatával. Elmagyarázzuk a mellékelt C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe.

 A kezdéshez győződjön meg arról, hogy az Aspose.Words for .NET telepítve van és be van állítva a fejlesztői környezetben. Ha még nem tette meg, töltse le és telepítse a könyvtárat innen[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. lépés: Az előző szakasz elérése

 Először nyissa meg az előző szakaszt a`PreviousSibling` az aktuális rész tulajdonsága:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## 2. lépés: Az előző szakasz ellenőrzése

Ezután ellenőrizze, hogy létezik-e előző szakasz. Ha nincs előző szakasz, egyszerűen visszatérünk:

```csharp
if (previousSection == null)
    return;
```

## 3. lépés: Fejlécek és láblécek törlése és másolása

A fejlécek és láblécek előző szakaszból az aktuális szakaszba másolásához töröljük a meglévő fejléceket és lábléceket az aktuális szakaszban, majd az előző szakasz fejlécein és láblécein keresztül ismételve klónozott másolatokat adunk az aktuális szakaszhoz:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## 4. lépés: A dokumentum mentése

Végül mentse el a módosított dokumentumot:

```csharp
doc.Save("OutputDocument.docx");
```

Ez az! Sikeresen másolta a fejléceket és lábléceket az előző szakaszból egy Word-dokumentum jelenlegi szakaszába az Aspose.Words for .NET használatával.

### Példa forráskód a fejlécek lábléceinek másolásához az előző szakaszból az Aspose.Words for .NET használatával

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

Nyugodtan használja ezt a kódot saját projektjeiben, és módosítsa saját igényei szerint.

### GYIK

#### K: Hogyan másolhatom át az előző szakasz fejléceit és lábléceit az Aspose.Wordsba?

 V: Az előző szakasz fejléceinek és lábléceinek Aspose.Wordsbe másolásához használja a`CopyHeadersFootersFromPreviousSection()` módszer az áramon`Section`tárgy. Ezzel átmásolja az előző szakasz fejléceit és lábléceit az aktuális szakaszba.

#### K: Lehetséges csak fejlécet vagy láblécet másolni az Aspose.Words előző részéből?

 V: Igen, az Aspose.Words előző szakaszából csak a fejlécet vagy láblécet lehet másolni. Ehhez használhatja a`CopyHeaderFromPreviousSection()` és`CopyFooterFromPreviousSection()` módszerek az áramon`Section` objektumot a fejléc vagy lábléc konkrétan az előző szakaszból az aktuális szakaszba másolásához.

#### K: A fejlécek és láblécek előző szakaszból történő másolása felváltja a meglévő fejléceket és lábléceket az aktuális szakaszban?

V: Igen, a fejlécek és láblécek előző szakaszból való másolása lecseréli a meglévő fejléceket és lábléceket az aktuális szakaszban. Ha meg szeretné tartani a meglévő fejléceket és lábléceket, és hozzá szeretné adni őket a másolt fejlécekhez és láblécekhez, további műveletet kell végrehajtania a tartalom egyesítéséhez.

#### K: Hogyan ellenőrizhetem, hogy egy szakasznak van-e fejléce vagy lábléc az Aspose.Words előző szakaszából?

V: Ha ellenőrizni szeretné, hogy egy szakasznak van-e fejléce vagy lábléc az Aspose.Words előző szakaszából, használja a`HasHeader` és`HasFooter` tulajdonságok a`Section` objektumot annak meghatározására, hogy a fejléc vagy a lábléc jelen van-e. Ha`HasHeader` vagy`HasFooter` visszatér`false`, ez azt jelenti, hogy ebben a szakaszban nincs fejléc vagy lábléc az előző szakaszból.