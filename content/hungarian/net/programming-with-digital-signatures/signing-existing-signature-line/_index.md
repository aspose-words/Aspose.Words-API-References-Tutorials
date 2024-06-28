---
title: Meglévő aláírási sor aláírása Word dokumentumban
linktitle: Meglévő aláírási sor aláírása Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan írhat alá egy meglévő aláírási sort egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-digital-signatures/signing-existing-signature-line/
---
Ebben az oktatóanyagban végigvezetjük az Aspose.Words for .NET segítségével meglévő aláírási sor aláírási funkciójának használatán. Ez a funkció lehetővé teszi a Word-dokumentumban már meglévő aláírási sor digitális aláírását. Kövesse az alábbi lépéseket:

## 1. lépés: A dokumentum betöltése és az aláírási sor elérése

Kezdje a meglévő aláírási sort tartalmazó dokumentum feltöltésével:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 2. lépés: Az aláírási beállítások megadása

Hozzon létre egy példányt a SignOptions osztályból, és állítsa be az aláírási beállításokat, beleértve az aláírási sor azonosítóját és az aláírási sor képét:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Ügyeljen arra, hogy megadja az aláírási sor képének helyes elérési útját.

## 3. lépés: A tanúsítvány betöltése

Kezdje az aláíró tanúsítvány betöltésével a CertificateHolder osztály használatával:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Ügyeljen arra, hogy megadja a tanúsítvány és a kapcsolódó jelszó helyes elérési útját.

## 4. lépés: A meglévő aláírási sor aláírása

Használja a DigitalSignatureUtil osztályt a meglévő aláírási sor aláírásához:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Feltétlenül adja meg a forrásdokumentum, az aláírt dokumentum és a tanúsítvány megfelelő elérési útját.

### Példa forráskódra a meglévő aláírási sor aláírásához az Aspose.Words for .NET használatával

Íme a teljes forráskód egy meglévő aláírási sor Aspose.Words for .NET-hez való aláírásához:


```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Az alábbi lépések követésével egyszerűen aláírhat egy meglévő aláírási sort egy Word-dokumentumban az Aspose.Words for .NET segítségével.

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan írhatunk alá egy meglévő aláírási sort egy Word-dokumentumban az Aspose.Words for .NET használatával. A megadott lépések követésével könnyedén betöltheti a dokumentumot, hozzáférhet a meglévő aláírási sorhoz, beállíthatja az aláírási beállításokat, és aláírhatja a dokumentumot. A meglévő aláírási sor aláírásának lehetősége kényelmes módot biztosít digitális aláírások hozzáadására a Word-dokumentumok előre meghatározott területeire, így biztosítva a dokumentum integritását és hitelesítését. Az Aspose.Words for .NET egy hatékony API-t kínál a szövegfeldolgozáshoz digitális aláírással, amely lehetővé teszi az aláírási folyamat testreszabását és a Word-dokumentumok biztonságának növelését.

### GYIK

#### K: Mi az a meglévő aláírási sor egy Word-dokumentumban?

V: A Word-dokumentumban egy meglévő aláírássor egy előre meghatározott terület, ahol aláírás helyezhető el. Általában egy alakzat vagy objektum képviseli a dokumentumban, és kijelölt helyként szolgál az aláíró számára, hogy hozzáadhassa digitális aláírását.

#### K: Hogyan írhatok alá egy meglévő aláírási sort egy Word-dokumentumban az Aspose.Words for .NET használatával?

V: Egy Word-dokumentumban lévő meglévő aláírási sor aláírásához az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:
1.  Töltse be a dokumentumot a gombbal`Document` osztályt, és adja meg a dokumentumfájl elérési útját.
2.  Hozzáférés a meglévő aláírási vonalhoz a megfelelő módszerrel vagy tulajdonsággal. Például használhatja`GetChild` módszer az aláírási vonal alakjának lekérésére.
3.  Hozzon létre egy példányt a`SignOptions` osztályt, és állítsa be a`SignatureLineId` tulajdonság a meglévő aláírási sor azonosítójához.
4.  Állítsa be a`SignatureLineImage` tulajdona a`SignOptions` osztályt a digitális aláírást képviselő képhez.
5.  Töltse be az aláíró tanúsítványt a`CertificateHolder` osztályt, és adja meg a szükséges tanúsítványt és jelszót.
6.  Használja a`DigitalSignatureUtil.Sign` A dokumentum aláírásának módja, megadva a szükséges paramétereket, beleértve a`SignOptions` tárgy.

#### K: Hogyan érhetem el a meglévő aláírási sort egy Word-dokumentumban az Aspose.Words for .NET használatával?

 V: A Word-dokumentum meglévő aláírási sorának eléréséhez az Aspose.Words for .NET használatával a megfelelő módszerrel vagy tulajdonsággal lekérheti az aláírási vonal alakját a dokumentum szerkezetéből. Használhatja például a`GetChild` módszert a megfelelő paraméterekkel, hogy megkapjuk a kívánt aláírási vonal alakzatot.

#### K: Testreszabhatom a digitális aláírás megjelenését egy meglévő aláírási sorban?

V: Igen, testreszabhatja a digitális aláírás megjelenését egy meglévő aláírási sorban az aláírást reprezentáló képfájl megadásával. A kép lehet logó, kézzel írt aláírás vagy az aláírás bármely más grafikus ábrázolása. Beállíthatja a`SignatureLineImage` tulajdona a`SignOptions` osztályt a képfájl bájtjaira.

#### K: Aláírhatok több meglévő aláírási sort egy Word-dokumentumban?
 V: Igen, aláírhat több meglévő aláírási sort egy Word-dokumentumban. Minden aláírási sorhoz külön-külön kell követni a lépéseket, beállítva a megfelelőt`SignatureLineId` és`SignatureLineImage` értékek a`SignOptions` objektumot minden aláírási sorhoz.

#### K: Milyen formátumú legyen a képfájl a digitális aláíráshoz egy meglévő aláírási sorban?

 V: A meglévő aláírási sorban lévő digitális aláírás képfájlja különböző formátumú lehet, például PNG, JPEG, BMP vagy GIF. Megadhatja a fájl elérési útját, vagy beolvassa a képfájl bájtjait, és hozzárendelheti a fájlhoz`SignatureLineImage` tulajdona a`SignOptions` osztály.
