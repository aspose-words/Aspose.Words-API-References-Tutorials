---
title: Csak olvasási védelem a Word dokumentumban
linktitle: Csak olvasási védelem a Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan védheti meg írásvédett Word-dokumentumait az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/document-protection/read-only-protection/
---
Ebben az oktatóanyagban végigvezetjük az Aspose.Words for .NET írásvédett funkciójának használatához szükséges lépéseken. Ez a funkció lehetővé teszi, hogy egy Word-dokumentumot csak olvashatóvá tegye, hogy megakadályozza a jogosulatlan módosításokat. Kövesse az alábbi lépéseket:

## 1. lépés: A dokumentum létrehozása és a védelem alkalmazása

Először hozzon létre egy példányt a Document osztályból és egy DocumentBuilder objektumból:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Írjon tartalmat a dokumentumba
Használja a DocumentBuilder objektumot, hogy tartalmat írjon a dokumentumba:

```csharp
builder.Write("Open document as read-only");
```

## 3. lépés: Állítsa be a jelszót, és tegye csak olvashatóvá a dokumentumot

Állítson be jelszót a dokumentumhoz a WriteProtection objektum SetPassword() tulajdonságával:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Feltétlenül cserélje ki a „MyPassword”-t a ténylegesen használni kívánt jelszóra.

## 4. lépés: Alkalmazza a csak olvasható dokumentumot

Tegye a dokumentumot csak olvashatóvá a ReadOnlyRecommended tulajdonság igaz értékre állításával:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## 5. lépés: Alkalmazza a csak olvasható védelmet, és mentse a dokumentumot

Végül alkalmazzon írásvédett védelmet a Dokumentum objektum Protect() metódusával:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a védett dokumentum mentéséhez.

### Példa forráskód a Csak olvasható védelemhez az Aspose.Words for .NET használatával

Íme a teljes forráskód az Aspose.Words for .NET-hez csak olvasható védelemhez:

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Adjon meg egy legfeljebb 15 karakter hosszú jelszót.
doc.WriteProtection.SetPassword("MyPassword");

// Tegye a dokumentumot csak olvashatóvá.
doc.WriteProtection.ReadOnlyRecommended = true;

// Alkalmazzon írásvédelmet csak olvashatóként.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Az alábbi lépések követésével könnyedén megvédheti dokumentumait

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk az Aspose.Words for .NET csak olvasható védelmi funkcióját, amely lehetővé teszi a Word-dokumentumok írásvédettvé tételét az illetéktelen módosítások elkerülése érdekében. A megadott lépések követésével egyszerűen csak olvasható védelmet alkalmazhat dokumentumaira, és fokozhatja azok biztonságát. Az írásvédett védelem a szerkesztési lehetőségek korlátozásával segíti a dokumentum tartalmának integritását és pontosságát. Az Aspose.Words for .NET hatékony és rugalmas API-t biztosít a dokumentumvédelem kezelésére, és számos egyéb szolgáltatást is támogat a Word-dokumentumok testreszabásához és biztonságossá tételéhez.

### GYIK az írásvédett Word dokumentumban

#### K: Mi az a csak olvasható védelem az Aspose.Words for .NET-ben?

V: Az Aspose.Words for .NET csak olvasható védelme egy olyan szolgáltatás, amely lehetővé teszi egy Word-dokumentum írásvédettvé tételét, megakadályozva a jogosulatlan módosításokat. Ha egy dokumentum írásvédettre van állítva, a felhasználók megnyithatják és megtekinthetik a dokumentumot, de nem módosíthatják annak tartalmát.

#### K: Hogyan alkalmazhatok írásvédett Word-dokumentumot az Aspose.Words for .NET használatával?

V: Ha csak olvasható védelmet szeretne alkalmazni egy Word-dokumentumra az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:
1.  Hozzon létre egy példányt a`Document` osztály és a`DocumentBuilder` tárgy.
2.  Használja a`DocumentBuilder` tartalmat írni a dokumentumba.
3.  Állítson be jelszót a dokumentumhoz a segítségével`SetPassword` módszere a`WriteProtection` tárgy.
4.  Állítsa be a`ReadOnlyRecommended` tulajdona a`WriteProtection` tiltakozni`true` hogy javasoljuk a dokumentum csak olvashatóként való megnyitását.
5.  Alkalmazza a csak olvasható védelmet a`Protect` módszere a`Document` objektum, megadva a`ProtectionType` mint`ReadOnly`.
6.  Mentse el a védett dokumentumot a`Save` módszere a`Document` tárgy.

#### K: Eltávolíthatom az írásvédett védelmet egy Word-dokumentumból az Aspose.Words for .NET használatával?

V: Igen, az Aspose.Words for .NET segítségével eltávolíthatja a Word-dokumentum írásvédettségét. Ehhez használhatja a`Unprotect` módszere a`Document` osztályt, amely eltávolít minden meglévő védelmet a dokumentumból.

#### K: Beállíthatok más jelszót az írásvédett védelemhez egy Word-dokumentumban?

 V: Nem, az Aspose.Words for .NET csak olvasható védelme nem teszi lehetővé, hogy külön jelszót állítson be kifejezetten az írásvédett védelemhez. A segítségével beállított jelszó`SetPassword` módszere a`WriteProtection` Az objektum az általános dokumentumvédelemre vonatkozik, beleértve a csak olvasási és írási és olvasási védelmet is.

#### K: A felhasználók megkerülhetik a csak olvasható védelmet egy Word-dokumentumban?

V: A Word dokumentumok írásvédettségének célja, hogy megakadályozza és megakadályozza a véletlen vagy jogosulatlan módosításokat. Bár bizonyos szintű védelmet nyújt, a kellő műszaki ismeretekkel vagy szerkesztési jogosultsággal rendelkező felhasználók megkerülhetik. Az írásvédett védelem azonban visszatartó erőként szolgál, és segít megőrizni a dokumentum sértetlenségét.