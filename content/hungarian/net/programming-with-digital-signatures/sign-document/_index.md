---
title: Sign Word dokumentum
linktitle: Sign Word dokumentum
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan írhat alá digitálisan Word-dokumentumot az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-digital-signatures/sign-document/
---
Ebben az oktatóanyagban végigvezetjük a dokumentum-aláíró funkció használatának lépésein az Aspose.Words for .NET-hez. Ez a funkció lehetővé teszi Word-dokumentumok digitális aláírását egy tanúsítvány segítségével. Kövesse az alábbi lépéseket:

## 1. lépés: A tanúsítvány betöltése

Kezdje az aláíró tanúsítvány betöltésével a CertificateHolder osztály használatával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Ügyeljen arra, hogy megadja a tanúsítvány és a kapcsolódó jelszó helyes elérési útját.

## 2. lépés: A dokumentum aláírása

A dokumentum aláírásához használja a DigitalSignatureUtil osztályt:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Ügyeljen arra, hogy a megfelelő elérési utat adja meg a forrásdokumentumhoz és az aláírt dokumentumhoz.

### Példa forráskódra a Dokumentum aláírásához az Aspose.Words for .NET használatával

Íme a teljes forráskód egy dokumentum Aspose.Words for .NET segítségével történő aláírásához:

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Az alábbi lépések követésével egyszerűen aláírhat egy Word-dokumentumot az Aspose.Words for .NET segítségével.

## Következtetés

 Ebben az oktatóanyagban megvizsgáltuk az Aspose.Words for .NET dokumentum-aláírási funkcióját. Az aláíró tanúsítvány betöltésével és a`DigitalSignatureUtil.Sign` módszerrel tudunk digitálisan aláírni egy Word dokumentumot. A dokumentum-aláírás hitelesítést biztosít, és biztosítja a dokumentum tartalmának integritását, így a biztonságos és megbízható dokumentumkezelés értékes funkciója.

### GYIK a jelszavas dokumentumhoz

#### K: Mi az a dokumentum-aláírás az Aspose.Words for .NET-ben?

V: Dokumentum-aláírás az Aspose.Words for .NET-ben egy Word-dokumentum tanúsítvány segítségével történő digitális aláírásának folyamatára utal. Ez a funkció digitális aláírást ad a dokumentumhoz, amely hitelességet, integritást és a dokumentum tartalmának letagadhatatlanságát biztosítja.

#### K: Hogyan tölthetem be az aláíró tanúsítványt az Aspose.Words for .NET-be?

 V: Az aláíró tanúsítvány betöltéséhez az Aspose.Words for .NET-be, használja a`CertificateHolder` osztály. Hozzon létre egy példányt a`CertificateHolder` a tanúsítványfájl elérési útjának és a hozzá tartozó jelszó megadásával. Íme egy példa:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Ügyeljen arra, hogy a tanúsítvány megfelelő elérési útját és a kapcsolódó jelszót adja meg.

#### K: Hogyan írhatok alá Word-dokumentumot az Aspose.Words for .NET használatával?

 V: Word-dokumentum aláírásához az Aspose.Words for .NET használatával, használhatja a`DigitalSignatureUtil` osztály. Hívja a`Sign` metódust, megadva a forrásdokumentum elérési útját, az aláírt dokumentum (kimenet) elérési útját és a`CertificateHolder` tárgy. Íme egy példa:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Győződjön meg arról, hogy a forrásdokumentum és az aláírt dokumentum (kimenet) megfelelő elérési útjait adja meg.

#### K: Mi a célja a dokumentumok aláírásának?

V: A dokumentumok aláírása a dokumentum hitelességének és sértetlenségének biztosítására szolgál. Egy dokumentum digitális aláírásával igazolhatja annak eredetét, ellenőrizheti, hogy a tartalma nem változott-e meg, és megerősítheti a letagadhatatlanságot. A dokumentumok aláírását gyakran használják jogi, pénzügyi és érzékeny dokumentumokhoz.

#### K: Használhatok bármilyen tanúsítványt a dokumentumok aláírására az Aspose.Words for .NET-ben?

V: Az Aspose.Words for .NET programban történő dokumentum-aláírásához érvényes X.509 tanúsítványt kell használnia. Ez a tanúsítvány beszerezhető egy megbízható tanúsító hatóságtól (CA), vagy önaláírt tanúsítvány használható tesztelési célokra.

#### K: Milyen fájlformátumot támogat az Aspose.Words for .NET a dokumentumok aláírásához?

 V: Az Aspose.Words for .NET támogatja a Word dokumentumok DOCX fájlformátumú aláírását. A DOCX fájlokat a`DigitalSignatureUtil` osztályt és a megfelelő bizonyítványt.

#### K: Aláírhatok több Word-dokumentumot ugyanazzal a tanúsítvánnyal?

V: Igen, ugyanazzal a tanúsítvánnyal több Word-dokumentumot is aláírhat. Miután betöltötte a tanúsítványt a`CertificateHolder` osztályban, akkor újra felhasználhatja több dokumentum aláírására, ha hívja a`DigitalSignatureUtil.Sign` módszer különböző forrás- és aláírt dokumentumútvonalakkal.

#### K: A dokumentum aláírása módosítja az eredeti dokumentumot?

V: Az Aspose.Words for .NET programmal történő dokumentum-aláírás nem módosítja az eredeti dokumentumot. Ehelyett létrehoz egy digitálisan aláírt másolatot a dokumentumról, így az eredeti dokumentumot érintetlenül hagyja. A digitálisan aláírt példány tartalmazza a hozzáadott digitális aláírást, amely biztosítja a dokumentum tartalmának sértetlenségét.

#### K: Ellenőrizhetem egy aláírt dokumentum digitális aláírását az Aspose.Words for .NET használatával?

 V: Igen, az Aspose.Words for .NET funkciót biztosít az aláírt dokumentumok digitális aláírásának ellenőrzésére. Használhatja a`DigitalSignatureUtil.Verify` módszer a digitális aláírás érvényességének és hitelességének ellenőrzésére.