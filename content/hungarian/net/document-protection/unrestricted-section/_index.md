---
title: Korlátlan szakasz a Word dokumentumban
linktitle: Korlátlan szakasz a Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan határozhat meg korlátlan szakaszokat egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/document-protection/unrestricted-section/
---
Ebben az oktatóanyagban végigvezetjük az Aspose.Words for .NET korlátlan szakasz funkciójának használatának lépésein. Ez a funkció lehetővé teszi, hogy meghatározott szakaszokat határozzon meg egy Word-dokumentumban, amelyek nem védettek, még akkor is, ha a dokumentum többi része védett. Kövesse az alábbi lépéseket:

## 1. lépés: A dokumentum és a szakaszok létrehozása

Először hozzon létre egy példányt a Document osztályból és egy DocumentBuilder objektumból:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Adjon hozzá tartalmat a dokumentumhoz
Használja a DocumentBuilder objektumot tartalom hozzáadásához a dokumentumhoz és szakasztörések beszúrásához:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## 3. lépés: Védje a dokumentumot és a szakaszokat

szakaszvédelem csak akkor működik, ha a dokumentumvédelem engedélyezve van, és csak az űrlapmezők szerkesztése engedélyezett. A dokumentumot a Dokumentum objektum Protect() metódusával védheti:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Feltétlenül adja meg a megfelelő védelmi típust és állítsa be a kívánt jelszót.

## 4. lépés: Egy adott szakasz védelmének letiltása

Alapértelmezés szerint minden szakasz védett, de a Section objektum ProtectedForms tulajdonságával szelektíven letilthatja egy adott szakasz védelmét:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

Ebben a példában a védelem le van tiltva az első szakaszban.

## 5. lépés: Mentse el a dokumentumot

Végül mentse el a módosított dokumentumot:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a dokumentum korlátlan részekkel történő mentéséhez.

### Példa forráskódra a Korlátlan szakaszhoz az Aspose.Words for .NET használatával

Íme az Aspose.Words for .NET korlátlan szakaszának teljes forráskódja:


```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Szúrjon be két szakaszt némi szöveggel.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// A szakaszvédelem csak akkor működik, ha a dokumentumvédelem be van kapcsolva, és csak az űrlapmezők szerkesztése engedélyezett.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//Alapértelmezés szerint minden szakasz védett, de a védelmet szelektíven kikapcsolhatjuk.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Ha követi ezeket a lépéseket, az Aspose.Words for .NET segítségével könnyedén meghatározhat korlátlan szakaszokat a Word-dokumentumban.

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk az Aspose.Words for .NET korlátlan szakaszszolgáltatását, amely lehetővé teszi, hogy a Word-dokumentum egyes szakaszai védelem nélkül maradjanak, miközben a dokumentum többi része védett. A megadott lépések követésével könnyedén meghatározhat olyan szakaszokat a dokumentumban, amelyekben a felhasználók szabadon szerkeszthetik a tartalmat, miközben fenntartja a többi szakasz védelmét. Az Aspose.Words for .NET hatékony dokumentumok védelmét és testreszabását kínálja, így Ön szabályozhatja a Word-dokumentumok szerkesztési engedélyeit.

### GYIK a Word dokumentum korlátlan részéhez

#### K: Mik azok a korlátlan szakaszok az Aspose.Words for .NET-ben?

V: Az Aspose.Words for .NET korlátlan szakaszai a Word-dokumentum azon szakaszai, amelyek nem védettek, még akkor sem, ha a dokumentum többi része védett. Ezek a szakaszok lehetővé teszik a felhasználók számára, hogy módosítsák a bennük lévő tartalmat, miközben fenntartják a dokumentum többi része védelmét.

#### K: Hogyan hozhatok létre korlátlan szakaszokat az Aspose.Words for .NET használatával?

V: Ha korlátlan szakaszokat szeretne létrehozni egy Word-dokumentumban az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:
1.  Hozzon létre egy példányt a`Document` osztály és a`DocumentBuilder` tárgy.
2.  Használja a`DocumentBuilder` tartalom hozzáadásához a dokumentumhoz és szakasztörések beszúrásához.
3.  Védje meg a dokumentumot a`Protect` módszere a`Document` objektum, megadva a kívánt védelmi típust és jelszót.
4.  Egy adott szakasz védelmének letiltása a`ProtectedForForms` a megfelelő tulajdonsága`Section` tiltakozni`false`.
5. Mentse el a módosított dokumentumot.

#### K: Lehet több korlátlan szakasz egy Word-dokumentumban?

 V: Igen, egy Word-dokumentumban több korlátlan szakasz is lehet. Ha szelektíven letiltja bizonyos szakaszok védelmét a`ProtectedForForms` tulajdona a`Section`objektum, több szakaszt is meghatározhat, ahol a felhasználók szabadon módosíthatják a tartalmat, miközben a többi szakaszt védik.

#### Q4. Eltávolíthatom a védelmet az eredetileg védett szakaszról?
 Igen, eltávolíthatja a védelmet az eredetileg védett szakaszról a`ProtectedForForms` a megfelelő tulajdonsága`Section` tiltakozni`false`. Ez lehetővé teszi a felhasználók számára, hogy korlátozások nélkül szerkesszék a tartalmat az adott szakaszon belül.

#### K: Milyen védelmi típusok alkalmazhatók egy Word-dokumentumra?

V: Az Aspose.Words for .NET különféle védelmi típusokat kínál, amelyek alkalmazhatók Word-dokumentumokra, többek között:
- NoProtection: Nincs védelem.
- AllowOnlyRevisions: A felhasználók csak a dokumentumot módosíthatják.
- AllowOnlyComments: A felhasználók csak megjegyzéseket fűzhetnek a dokumentumhoz.
- AllowOnlyFormFields: A felhasználók csak az űrlapmezőket szerkeszthetik a dokumentumban.
- Csak olvasható: A dokumentum csak olvasható, szerkesztése nem engedélyezett.


