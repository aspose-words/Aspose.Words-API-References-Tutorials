---
title: Csak az űrlapmezők védelme engedélyezése a Word-dokumentumban
linktitle: Csak az űrlapmezők védelme engedélyezése a Word-dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan használhatja az Aspose.Words for .NET-et a Word-dokumentum védelmére, és csak az űrlapmezők szerkesztését engedélyezi.
type: docs
weight: 10
url: /hu/net/document-protection/allow-only-form-fields-protect/
---
dokumentumvédelem alapvető funkció a C#-alkalmazáson belüli fájlokkal végzett szövegfeldolgozás során. A .NET Aspose.Words könyvtárával könnyedén megvédheti dokumentumait, és csak az űrlapmezők szerkesztését engedélyezheti. Ebben a részletes útmutatóban végigvezetjük, hogyan használhatja a C# forráskódot, hogy csak az űrlapmezőket engedélyezze az Aspose.Words for .NET Csak űrlapmezők védelme funkciójával.

## 1. lépés: A dokumentumkönyvtár beállítása

Az első lépés a dokumentum könyvtárának meghatározása. Meg kell adnia az elérési utat, ahová a védett dokumentumot menteni kívánja. Például :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 2. lépés: szakaszok és szöveg beszúrása

Ezután szakaszokat és szöveget kell beillesztenie a dokumentumba. Használja az Aspose.Words által biztosított DocumentBuilder osztályt a dokumentum tartalmának felépítéséhez. Íme egy egyszerű példa:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

Ebben a példában létrehozunk egy új üres dokumentumot, majd a DocumentBuilder segítségével szövegsort adunk hozzá.

## 3. lépés: A dokumentumvédelem engedélyezése

 A dokumentumvédelem csak akkor működik, ha a dokumentumvédelem be van kapcsolva. A dokumentumvédelmet a`Protect` a Dokumentum osztály metódusa. Itt van, hogyan:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Ebben a példában a dokumentumvédelmet a ` védelmi típus megadásával engedélyezzük

AllowOnlyFormFields` és jelszó beállítása.

## 4. lépés: Csak űrlapmezők engedélyezése

Most, hogy a dokumentumvédelem engedélyezve van, meg kell adnunk, hogy csak az űrlapmezők szerkesztése engedélyezett. Ez biztosítja, hogy a felhasználók csak a dokumentum azon részeit szerkeszthessék, amelyek űrlapmezők. Itt van, hogyan:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Feltétlenül cserélje ki a „jelszó” kifejezést a korábban beállított jelszóra.

## 5. lépés: A védett dokumentum mentése

 Végül elmentheti a védett dokumentumot a`Save` a Dokumentum osztály metódusa. Adja meg a teljes fájl elérési utat és a kívánt fájlnevet. Például :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Feltétlenül cserélje ki a "dataDir" kifejezést a dokumentumkönyvtár elérési útjára.

### Példa forráskód az Allow Only Form Fields Protect funkcióhoz az Aspose.Words for .NET használatával

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Szúrjon be két részt szöveggel.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// A dokumentumvédelem csak akkor működik, ha a dokumentumvédelem be van kapcsolva, és csak az űrlapmezők szerkesztése engedélyezett.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Mentse el a védett dokumentumot.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Következtetés

Ebben az útmutatóban megvizsgáltuk, hogyan használhatjuk az Aspose.Words könyvtárat .NET-hez a dokumentumok védelmére, és csak az űrlapmezők szerkesztését engedélyezzük. A megadott lépések követésével könnyedén megvalósíthatja ezt a funkciót a C# alkalmazásban. A dokumentumok védelme elengedhetetlen a dokumentumai biztonságának és bizalmasságának szavatolásához.

### A Word dokumentumban csak az űrlapmezők engedélyezésével kapcsolatos GYIK

#### K: Mi a dokumentumvédelem az Aspose.Words for .NET-ben?

V: Az Aspose.Words for .NET dokumentumvédelme egy olyan szolgáltatás, amely bizonyos műveletek, például szerkesztés, formázás vagy tartalommódosítás korlátozásával lehetővé teszi a dokumentumok védelmét. Segít megőrizni a dokumentumok sértetlenségét és titkosságát azáltal, hogy megakadályozza a jogosulatlan módosításokat.

#### K: Hogyan védhetek meg egy dokumentumot, és csak az űrlapmezőket engedélyezhetem az Aspose.Words for .NET használatával?

V: Ha meg szeretne védeni egy dokumentumot, és csak űrlapmezőket szeretne szerkeszteni az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:
1. Határozza meg a dokumentum könyvtárának elérési útját.
2.  Szúrjon be szakaszokat és szöveget a dokumentumba a gombbal`DocumentBuilder` osztály.
3.  Engedélyezze a dokumentumvédelmet a`Protect` módszere a`Document` osztály, megadva a védelmi típust as`AllowOnlyFormFields` és jelszó megadása.
4.  Mentse el a védett dokumentumot a`Save` módszere a`Document` osztály.

#### K: Beszúrhatok űrlapmezőket védett dokumentumokba az Aspose.Words for .NET használatával?

V: Igen, beszúrhat űrlapmezőket egy védett dokumentumba az Aspose.Words for .NET használatával. Az iratvédelem a`AllowOnlyFormFields` típus lehetővé teszi a felhasználók számára, hogy csak az űrlapmezőket szerkeszthessék, miközben védik a dokumentum többi tartalmát. Használhatja a`DocumentBuilder` osztályt, hogy űrlapmezőket szúrjon be a dokumentumba a védelem engedélyezése előtt.

#### K: Eltávolíthatom a dokumentumvédelmet egy védett dokumentumról?

 V: Igen, az Aspose.Words for .NET használatával eltávolíthatja a védett dokumentumokról a dokumentumvédelmet. A védelem eltávolításához használhatja a`Unprotect` módszere a`Document` osztályt, és adja meg a helyes jelszót. Ezzel eltávolítja a védelmet, és lehetővé teszi a dokumentum korlátlan szerkesztését.

#### K: Lehetséges egy dokumentum több védelmi típussal történő védelme?

 V: Nem, az Aspose.Words for .NET egyszerre csak egy védelmi típus alkalmazását teszi lehetővé egy dokumentumon. Azonban a`AllowOnlyFormFields` védelmi típus hatékonyan korlátozhatja a szerkesztést az űrlapmezőkre, miközben más védelmi típusokat is engedélyez, mint pl`AllowOnlyComments` vagy`AllowOnlyRevisions`formamező védelemmel kombinálandó.

#### K: Beállíthatok különböző jelszavakat a különböző védelmi típusokhoz egy dokumentumban?

V: Nem, az Aspose.Words for .NET lehetővé teszi, hogy egyetlen jelszót állítson be a dokumentumok védelméhez, a védelem típusától függetlenül. Ugyanazt a jelszót fogja használni a dokumentumvédelem engedélyezéséhez és letiltásához.