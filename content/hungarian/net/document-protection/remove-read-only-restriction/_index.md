---
title: Távolítsa el a Csak olvasási korlátozást
linktitle: Távolítsa el a Csak olvasási korlátozást
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan távolíthatja el a csak olvasható korlátozást egy Word-dokumentumból az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/document-protection/remove-read-only-restriction/
---
Ebben az oktatóanyagban végigvezetjük az Aspose.Words for .NET írásvédett korlátozás eltávolítási funkciójának használatának lépésein. Ez a funkció lehetővé teszi a csak olvasható korlátozás eltávolítását a Word-dokumentumból, hogy szerkeszthető legyen. Kövesse az alábbi lépéseket:

## 1. lépés: A dokumentum létrehozása és a védelem beállítása

Kezdje a Dokumentum osztály példányának létrehozásával:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Állítson be jelszót a dokumentumhoz a WriteProtection objektum SetPassword() tulajdonságával:

Feltétlenül cserélje ki a „MyPassword”-t a dokumentum védelméhez használt tényleges jelszóra.

## 2. lépés: Távolítsa el a csak olvasható korlátozást

A csak olvasható korlátozás eltávolításához állítsa a ReadOnlyRecommended tulajdonságot false értékre:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## 3. lépés: Korlátlan védelem alkalmazása

Végül alkalmazzon korlátlan védelmet a Document objektum Protect() metódusával:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a dokumentum csak olvasható korlátozás nélküli mentéséhez.

### Példa forráskód a Csak olvasható korlátozás eltávolításához az Aspose.Words for .NET használatával

Íme a teljes forráskód az Aspose.Words for .NET használatával való csak olvasható korlátozásának eltávolításához:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// Adjon meg egy legfeljebb 15 karakter hosszú jelszót.
doc.WriteProtection.SetPassword("MyPassword");

//Távolítsa el a csak olvasható beállítást.
doc.WriteProtection.ReadOnlyRecommended = false;

// Alkalmazzon írásvédelmet védelem nélkül.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Ha követi ezeket a lépéseket, az Aspose.Words for .NET segítségével egyszerűen eltávolíthatja a csak olvasható korlátozást a Word-dokumentumokból.


## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan távolíthatja el a csak olvasható korlátozást egy Word-dokumentumból az Aspose.Words for .NET használatával. A megadott lépések követésével könnyedén eltávolíthatja a korlátozást, és újra szerkeszthetővé teheti a dokumentumot. Az Aspose.Words for .NET szolgáltatások átfogó készletét kínálja a dokumentumok védelmének és korlátozásainak kezelésére, rugalmasságot és ellenőrzést biztosítva a Word-dokumentumok biztonsági és szerkesztési lehetőségei felett.

### GYIK

#### K: Mi az Aspose.Words for .NET csak olvasható korlátozása?

V: Az Aspose.Words for .NET csak olvasható korlátozása egy olyan szolgáltatásra vonatkozik, amely lehetővé teszi egy Word-dokumentum írásvédettként való beállítását, megakadályozva, hogy a felhasználók módosítsák a tartalmat vagy a formázást. Ez a korlátozás segít megvédeni a dokumentum sértetlenségét, és biztosítja, hogy véletlenül vagy rosszindulatúan ne módosítsák.

#### K: Hogyan távolíthatom el a csak olvasható korlátozást az Aspose.Words for .NET használatával?

V: Ha az Aspose.Words for .NET használatával el szeretné távolítani a Word-dokumentum írásvédettségi korlátozását, kövesse az alábbi lépéseket:
1.  Hozzon létre egy példányt a`Document` osztályt, és állítson be jelszót a dokumentumhoz a segítségével`SetPassword` módszere a`WriteProtection` tárgy.
2.  Állítsa be a`ReadOnlyRecommended` tulajdona a`WriteProtection` tiltakozni`false` a csak olvasható ajánlás eltávolításához.
3.  Alkalmazzon korlátlan védelmet a dokumentumra a`Protect` módszere a`Document` tárgyat a`NoProtection` védelmi típus.
4.  Mentse el a dokumentumot írásvédett korlátozás nélkül a`Save` módszere a`Document` tárgy.

#### K: Eltávolíthatom a csak olvasható korlátozást egy Word-dokumentumból jelszó nélkül?

V: Nem, nem távolíthatja el a csak olvasható korlátozást a Word-dokumentumból a megfelelő jelszó megadása nélkül. A csak olvasható korlátozást biztonsági okokból állítják be, és a jelszó nélküli eltávolítása aláásná a dokumentum integritásának védelmét.

#### K: Eltávolíthatom a csak olvasható korlátozást egy rossz jelszóval rendelkező Word-dokumentumból?

V: Nem, nem távolíthatja el a csak olvasható korlátozást egy rossz jelszóval rendelkező Word-dokumentumból. A helyes jelszót meg kell adni az írásvédett korlátozás megszüntetéséhez és a dokumentum újra szerkeszthetővé tételéhez. Ez biztosítja, hogy csak a megfelelő jelszóval rendelkező jogosult felhasználók módosíthatják a dokumentumot.

#### K: Eltávolítható más típusú dokumentumvédelem az Aspose.Words for .NET használatával?

V: Igen, az Aspose.Words for .NET különféle módszereket kínál más típusú dokumentumvédelem eltávolítására, például jelszavas védelemre, űrlapvédelemre vagy dokumentumszerkesztési korlátozásokra. A dokumentumra alkalmazott védelem típusától függően használhatja az Aspose.Words által biztosított megfelelő módszereket és tulajdonságokat az adott védelem eltávolításához és a dokumentum szerkeszthetővé tételéhez.
