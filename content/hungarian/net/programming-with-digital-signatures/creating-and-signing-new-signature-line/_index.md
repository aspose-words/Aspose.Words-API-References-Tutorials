---
title: Új aláírási sor létrehozása és aláírása
linktitle: Új aláírási sor létrehozása és aláírása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre és írhat alá új aláírási sort egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
Ebben az oktatóanyagban végigvezetjük az Aspose.Words for .NET-hez tartozó aláírási vonal létrehozása és aláírása funkció használatának lépésein. Ez a funkció lehetővé teszi aláírási sor beszúrását egy Word dokumentumba, egyéni beállítások megadását és a dokumentum aláírását. Kövesse az alábbi lépéseket:

## 1. lépés: A dokumentum és a generátor létrehozása

Először hozzon létre egy példányt a Document osztályból és egy DocumentBuilder objektumból:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Az aláírási sor beszúrása

A DocumentBuilder objektum InsertSignatureLine() metódusával új aláírási sort illeszthet be a dokumentumba:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## 3. lépés: Mentse el a dokumentumot

Mentse el a módosított dokumentumot:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a dokumentum mentéséhez.

## 4. lépés: A dokumentum aláírása

A dokumentum aláírásához be kell állítania az aláírási beállításokat, és használnia kell a DigitalSignatureUtil osztályt:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Ügyeljen arra, hogy a megfelelő elérési utat adja meg a dokumentumhoz, az aláírási sor képéhez és az aláírt dokumentumhoz.

### Példa forráskód új aláírási sor létrehozásához és aláírásához az Aspose.Words for .NET használatával

Íme a teljes forráskód egy új aláírási sor létrehozásához és aláírásához az Aspose.Words for .NET-hez:

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Ha követi ezeket a lépéseket, könnyen létrehozhat és aláírhat egy új aláírási sort a Word-dokumentumban az Aspose.Words for .NET segítségével.

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet új aláírási sort létrehozni és aláírni egy Word-dokumentumban az Aspose.Words for .NET használatával. A megadott lépések követésével egyszerűen beilleszthet egy aláírási sort a dokumentumba, testreszabhatja annak beállításait, és aláírhatja a dokumentumot digitális tanúsítvánnyal. Aláírási sorok és digitális aláírások hozzáadása a dokumentumokhoz növeli azok hitelességét és integritását, így biztonságosabbá és megbízhatóbbá válik. Az Aspose.Words for .NET hatékony API-t biztosít a Word Processing-hoz aláírásokkal és digitális tanúsítványokkal a Word dokumentumokban, lehetővé téve az aláírási folyamat automatizálását és a dokumentumok érvényességének biztosítását.

### GYIK

#### K: Mi az aláírássor egy Word-dokumentumban?

V: A Word-dokumentumban lévő aláírássor egy helyőrző, amely jelzi, hová kell elhelyezni az aláírást. Általában tartalmazza a nevet, a címet és a dátumot, és helyet biztosít a kézzel írott vagy digitális aláírásnak.

#### K: Hogyan hozhatok létre aláírási sort egy Word-dokumentumban az Aspose.Words for .NET használatával?

V: Aláírási sor létrehozásához egy Word-dokumentumban az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:
1.  Hozzon létre egy példányt a`Document` osztály és a`DocumentBuilder` tárgy.
2.  Használja a`InsertSignatureLine` módszere a`DocumentBuilder` objektumot egy új aláírási sor beillesztéséhez a dokumentumba.
3. Mentse el a módosított dokumentumot.

#### K: Testreszabhatom az aláírási sor beállításait, például a nevet, a címet és a dátumot?

 V: Igen, testreszabhatja az aláírási sor beállításait. A`SignatureLineOptions` osztály tulajdonságokat biztosít a kívánt opciók beállításához, mint pl`Signer`, `SignerTitle`, `ShowDate`, stb. Az aláírási sor beszúrása előtt módosíthatja ezeket a tulajdonságokat.

#### K: Hogyan írhatom alá a dokumentumot aláírási sor létrehozása után?

 V: A dokumentum aláírásához aláírási sor létrehozása után be kell állítania az aláírási beállításokat, és használnia kell a`DigitalSignatureUtil` osztály. Íme a lépések:
1.  Állítsa be a`SignatureLineId` ingatlan a`SignOptions` objektumot az aláírási sor azonosítójára.
2.  Állítsa be a`SignatureLineImage` ingatlan a`SignOptions` tiltakozzon a használni kívánt aláírás képére.
3.  Töltse be az aláíró tanúsítványt a`CertificateHolder` osztály.
4.  Használja a`DigitalSignatureUtil.Sign` a dokumentum aláírásának módja, megadva a szükséges paramétereket.

#### K: Használhatok digitális aláírási képet a dokumentum aláírásához?

 V: Igen, használhat digitális aláírási képet a dokumentum aláírásához. Ehhez meg kell adnia a képfájlt a`SignOptions` objektum segítségével`SignatureLineImage`ingatlan. A kép bármilyen támogatott képformátumban lehet, például JPEG, PNG vagy EMF.

#### K: Mi a célja egy új aláírási sor létrehozásának és aláírásának egy Word dokumentumban?

V: Új aláírási sor létrehozása és aláírása egy Word-dokumentumban az Aspose.Words for .NET használatával lehetővé teszi, hogy helyőrzőt adjon az aláíráshoz, majd aláírja a dokumentumot digitális tanúsítvánnyal. Ez a folyamat biztosítja a dokumentum hitelességét és sértetlenségét, bizonyítva a jóváhagyást vagy az egyetértést.

#### K: Létrehozhatok és aláírhatok több aláírási sort egy Word-dokumentumban az Aspose.Words for .NET használatával?

V: Igen, az Aspose.Words for .NET használatával több aláírási sort is létrehozhat és aláírhat egy Word-dokumentumban. Minden aláírási sor saját egyedi azonosítóval és opciókkal rendelkezhet. A lépéseket megismételheti további aláírási sorok létrehozásához és aláírásához a dokumentumban.

#### K: Módosíthatom az aláírási sort vagy adhatok hozzá további információkat az aláírás után?

V: Az aláírási sor aláírása után a dokumentum tartalmának részévé válik, és külön nem módosítható. Az aláírt aláírási sor után azonban további információkat vagy tartalmat adhat hozzá.

#### K: Ellenőrizhetem egy aláírási sort tartalmazó dokumentum digitális aláírását?

 V: Igen, az Aspose.Words for .NET funkciót biztosít az aláírássort tartalmazó dokumentumok digitális aláírásának ellenőrzésére. Használhatja a`DigitalSignatureUtil.Verify` módszer a digitális aláírás érvényességének és hitelességének ellenőrzésére.

#### K: Milyen fájlformátumot támogat az Aspose.Words for .NET az aláírási sorok létrehozásához és aláírásához?

V: Az Aspose.Words for .NET támogatja az aláírási sorok létrehozását és aláírását DOCX fájlformátumban. Létrehozhat és aláírhat aláírási sorokat DOCX-fájlokban a megadott metódusok és osztályok használatával.