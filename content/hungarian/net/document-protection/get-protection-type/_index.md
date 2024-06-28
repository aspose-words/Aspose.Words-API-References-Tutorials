---
title: Védelem típusának lekérése Word dokumentumban
linktitle: Védelem típusának lekérése Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan használhatja az Aspose.Words for .NET védelmi típusát a Word dokumentumban a dokumentum védelmi típusának meghatározására.
type: docs
weight: 10
url: /hu/net/document-protection/get-protection-type/
---
Üdvözöljük ebben a lépésenkénti útmutatóban, amely elmagyarázza az Aspose.Words for .NET védelmi típusa szolgáltatásának C# forráskódját. Ebben a cikkben bemutatjuk, hogyan használhatja ezt a hatékony funkciót a dokumentumok védelmi típusának meghatározására. A dokumentumok védelme elengedhetetlen a fájlok titkosságának és integritásának biztosításához. Végigvezetjük az Aspose.Words for .NET integrálásához és a Védelemtípus lekérése funkció használatához szükséges lépéseken.

## 1. lépés: A dokumentum betöltése

Védelemtípus lekérése funkció használatának első lépése a feldolgozni kívánt dokumentum feltöltése. Ezt az Aspose.Words for .NET által biztosított Document osztály használatával teheti meg. Íme egy mintakód a dokumentum fájlból történő betöltéséhez:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

Ügyeljen arra, hogy a dokumentumfájl helyes elérési útját adja meg.

## 2. lépés: A védelmi típus lekérése

A dokumentum feltöltése után a Dokumentum objektum ProtectionType tulajdonságával lekérheti a dokumentumra alkalmazott védelem típusát. A következőképpen teheti meg:

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### Példa forráskódra az Aspose.Words for .NET védelmi típusához

Íme a Get Protection Type funkció teljes forráskódja az Aspose.Words for .NET használatával:

```csharp
Document doc = new Document(MyDir + "Document.docx");
ProtectionType protectionType = doc.ProtectionType;
```

## Következtetés

Ebben a cikkben elmagyaráztuk, hogyan használható az Aspose.Words for .NET védelmi típusa funkciója egy dokumentum védelmi típusának meghatározására. A leírt lépések követésével könnyedén integrálhatja ezt a funkciót saját C#-projektjeibe, és hatékonyan kezelheti a védett dokumentumokat. Az Aspose.Words for .NET nagy rugalmasságot kínál

### GYIK

#### K: Mi az Aspose.Words for .NET ProtectionType tulajdonsága?

 V: A`ProtectionType` tulajdonság az Aspose.Words for .NET-ben egy olyan szolgáltatás, amely lehetővé teszi a Word-dokumentumokra alkalmazott védelem típusának meghatározását. Információkat ad a dokumentumvédelem szintjéről, például arról, hogy a dokumentum védett-e a megjegyzések, revíziók, űrlapok vagy egyéb korlátozások tekintetében.

#### K: Hogyan kérhetem le egy dokumentum védelmi típusát az Aspose.Words for .NET használatával?

V: Egy dokumentum védelmi típusának lekéréséhez az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:
1.  Töltse be a dokumentumot a gombbal`Document` osztály.
2.  Hozzáférés a`ProtectionType` tulajdona a`Document` objektumot a védelmi típus lekéréséhez.

#### K: Meghatározhatom, hogy egy dokumentum védett-e az űrlapok vagy űrlapmezők számára a ProtectionType tulajdonság használatával?

 V: Igen, a segítségével meghatározhatja, hogy egy dokumentum védett-e az űrlapok vagy űrlapmezők számára`ProtectionType` tulajdonság az Aspose.Words for .NET-ben. Ha a védelem típusa a következőre van állítva`AllowOnlyFormFields`, azt jelzi, hogy a dokumentum védett, és csak az űrlapmezők szerkeszthetők.

#### K: Milyen egyéb védelmi típusokat adhat vissza a ProtectionType tulajdonság?

 V: A`ProtectionType` Az Aspose.Words for .NET-ben található tulajdonságok különböző típusú védelmi funkciókat adhatnak vissza, többek között:
- `NoProtection`: A dokumentum nem védett.
- `AllowOnlyRevisions`: A dokumentum védett, és csak revíziók hajthatók végre.
- `AllowOnlyComments`: A dokumentum védett, csak megjegyzések fűzhetők hozzá.
- `AllowOnlyFormFields`: A dokumentum védett, és csak az űrlapmezők szerkeszthetők.
- `ReadOnly`: A dokumentum védett és írásvédett.

#### K: Módosíthatom egy dokumentum védelmi típusát a ProtectionType tulajdonság használatával?

 V: Nem, a`ProtectionType`tulajdonság az Aspose.Words for .NET-ben csak olvasható tulajdonság. Lehetővé teszi egy dokumentum aktuális védelmi típusának lekérését, de nem biztosít közvetlen módot a védelmi típus módosítására. A védelem típusának módosításához más módszereket és tulajdonságokat kell használnia, amelyek elérhetők a`Document` osztály, mint pl`Protect` vagy`Unprotect`.

#### K: Lehetséges egy dokumentum egyidejű védelme több védelmi típussal?

V: Nem, az Aspose.Words for .NET egyszerre csak egy védelmi típus alkalmazását teszi lehetővé egy dokumentumon. A különböző védelmi típusokat azonban kombinálhatja úgy, hogy engedélyezi a védelmet, beállít egy típust, letiltja a védelmet, majd ismét engedélyezi egy másik típussal.

