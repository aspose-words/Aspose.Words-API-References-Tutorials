---
title: Dokumentum beszúrása a körlevélbe
linktitle: Dokumentum beszúrása a körlevélbe
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szúrhat be egy dokumentumot egy másikba az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
Ebben az oktatóanyagban végigvezetjük, hogyan illeszthet be egy dokumentumot egy másik dokumentumba a körlevélkészítés során az Aspose.Words for .NET Dokumentum beszúrása körözés során funkciójával. Kövesse az alábbi lépéseket a forráskód megértéséhez és a dokumentum beszúrásához.

## 1. lépés: A fő dokumentum betöltése

A kezdéshez adja meg a dokumentumok könyvtárát, és töltse be a fő dokumentumot egy dokumentum objektumba. Itt van, hogyan:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## 2. lépés: A körlevél konfigurálása

Most állítsuk be a körlevél-összevonást, és adjuk meg a mezőegyesítés visszahívását, hogy egy dokumentumot beszúrjunk egy másik dokumentumba. Itt van, hogyan:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## 3. lépés: A körlevél futtatása

Az egyesítési mezők nevének és a megfelelő adatok megadásával futtatjuk a körlevél-összevonást. Itt van, hogyan:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Példa forráskódra a Dokumentum beszúrása körlevélnél funkcióhoz az Aspose.Words for .NET használatával

Íme az Aspose.Words for .NET Dokumentum beszúrása körlevél funkciójának teljes forráskódja:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// A fő dokumentumban van egy "Dokumentum_1" nevű összevonási mező.
// Ennek a mezőnek a megfelelő adatai tartalmazzák a dokumentum teljes elérési útját.
// Ezt be kell illeszteni ebbe a mezőbe.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Ezzel a kóddal egy dokumentumot illeszthet be egy másik dokumentumba az Aspose.Words for .NET segítségével történő körlevél-egyesítés során. Az eredményül kapott dokumentum új néven kerül mentésre


## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan illeszthetünk be egy dokumentumot egy másik dokumentumba körlevél-egyesítés során az Aspose.Words for .NET Dokumentum beszúrása körözés során funkciójával. A körlevél konfigurálásával és a szükséges adatok megadásával dinamikusan összeállíthatja a dokumentumokat különböző dokumentumsablonok vagy -szakaszok egyesítésével. Az Aspose.Words for .NET rugalmas és hatékony módszert kínál összetett dokumentum-előállítási forgatókönyvek kezelésére, így értékes eszköz a dokumentumkészítési és -kezelési feladatok automatizálására.

### GYIK

#### K: Mi a célja egy dokumentum beszúrásának egy másik dokumentumba a körözés során?

V: Egy dokumentum beszúrása egy másik dokumentumba a körözés során lehetővé teszi a különböző dokumentumsablonok vagy -szakaszok dinamikus kombinálását az egyesítési folyamat során megadott adatok alapján. Ez a funkció különösen akkor hasznos, ha összetett dokumentumokat szeretne összeállítani úgy, hogy különféle előre meghatározott sablonokat vagy szakaszokat egyesít egy végleges dokumentumba.

#### K: Hogyan illeszthetek be egy dokumentumot egy másik dokumentumba az Aspose.Words for .NET használatával egyesítés során?

V: Ha egy dokumentumot szeretne beszúrni egy másik dokumentumba az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:
1. Töltse be az alapként szolgáló fő dokumentumot egy dokumentum objektumba.
2. Konfigurálja a körlevél-összevonást, és adja meg a mezőegyesítés visszahívását a dokumentumbeillesztés kezeléséhez.
3. Futtassa a körlevél-összevonást az egyesítési mezők nevével és a megfelelő adatokkal (a beillesztendő dokumentum elérési útja).

#### K: Hogyan szabhatom testre a beillesztési viselkedést a körlevél-összevonás során?

V: A körlevél-összevonás során a beillesztési viselkedés testreszabásához egyéni FieldMergingCallbacket valósíthat meg az IFieldMergingCallback felületről való örökléssel. Ez lehetővé teszi a dokumentumok beszúrásának és egyesítésének szabályozását az Ön egyedi igényei alapján.

#### K: Beilleszthetek több dokumentumot a körlevél-egyesítés során?

V: Igen, a körlevélkészítés során több dokumentumot is beszúrhat, ha minden egyes összevonási mezőhöz megadja a megfelelő adatokat. Minden egyes dokumentum beszúrást igénylő mezőnél adja meg adatként a megfelelő dokumentum elérési útját.


