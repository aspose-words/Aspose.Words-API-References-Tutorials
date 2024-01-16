---
title: Állítsa be az aláírás-szolgáltató azonosítóját a Word dokumentumban
linktitle: Állítsa be az aláírás-szolgáltató azonosítóját a Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja be az aláírásszolgáltató azonosítóját egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-digital-signatures/set-signature-provider-id/
---
Ebben az oktatóanyagban végigvezetjük a Set Signature Provider ID funkció használatának lépésein az Aspose.Words for .NET-hez. Ez a szolgáltatás lehetővé teszi az aláírás-szolgáltató azonosítójának megadását egy Word-dokumentum aláírási sorához. Kövesse az alábbi lépéseket:

## 1. lépés: A dokumentum betöltése és az aláírási sor elérése

Kezdje az aláírási sort tartalmazó dokumentum feltöltésével:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 2. lépés: Az aláírási beállítások megadása

Hozzon létre egy példányt a SignOptions osztályból, és állítsa be az aláírási beállításokat, beleértve a szolgáltató azonosítóját:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## 3. lépés: A dokumentum aláírása

A dokumentum aláírásához a DigitalSignatureUtil osztályt kell használnia, és meg kell adnia az aláíró tanúsítványt:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Feltétlenül adja meg a dokumentum, a tanúsítvány és az aláírt dokumentum helyes elérési útját.

### Példa forráskódra a Set Signature Provider Id-hez az Aspose.Words for .NET használatával

Itt található a teljes forráskód az aláírás-szolgáltató azonosítójának Aspose.Words for .NET-hez való beállításához:

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Fejezd be az aláírásszolgáltató azonosítóját a Word-dokumentumban az Aspose.Words for .NET segítségével.


## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan állíthatja be az aláírás-szolgáltató azonosítóját egy aláírási sorhoz egy Word-dokumentumban az Aspose.Words for .NET használatával. A megadott lépések követésével könnyedén betöltheti a dokumentumot, hozzáférhet az aláírási sorhoz, beállíthatja a szolgáltatói azonosítót és aláírhatja a dokumentumot. Az aláírásszolgáltató azonosítójának beállításának lehetősége segít megállapítani az aláíró személyazonosságát és megbízhatóságát, növelve a Word-dokumentumok biztonságát és integritását. Az Aspose.Words for .NET robusztus API-t biztosít a szövegfeldolgozáshoz digitális aláírással, amely lehetővé teszi az aláírási folyamat egyszerű testreszabását és kezelését.

### GYIK az aláírás-szolgáltató azonosítójának beállításához a Word dokumentumban

#### K: Mi az aláírás-szolgáltató azonosítója egy Word-dokumentumban?

V: Az aláírás-szolgáltató azonosítója egy Word-dokumentumban egy egyedi azonosító, amely meghatározza a digitális aláírás szolgáltatóját. Segít azonosítani a digitális aláírás létrehozásáért és kezeléséért felelős entitást vagy szervezetet.

#### K: Hogyan állíthatom be az aláírásszolgáltató azonosítóját egy aláírási sorhoz egy Word-dokumentumban az Aspose.Words for .NET használatával?

V: Az Aspose.Words for .NET használatával egy Word-dokumentum aláírási sorához tartozó aláírásszolgáltató azonosító beállításához kövesse az alábbi lépéseket:
1.  Töltse be a dokumentumot a gombbal`Document` osztályt, és adja meg a dokumentumfájl elérési útját.
2.  Az aláírási sor elérése a megfelelő módszerrel vagy tulajdonsággal. Például használhatja`GetChild` módszer az aláírási vonal alakjának lekérésére.
3. Keresse le a szolgáltató azonosítóját az aláírási sorból.
4.  Hozzon létre egy példányt a`SignOptions` osztályt, és állítsa be a`ProviderId` tulajdonság a lekért szolgáltatói azonosítóhoz.
5.  Használja a`DigitalSignatureUtil.Sign` A dokumentum aláírásának módja, megadva a szükséges paramétereket, beleértve a`SignOptions` tárgy.

#### K: Hogyan érhetem el az aláírási sort egy Word-dokumentumban az Aspose.Words for .NET használatával?

 V: A Word-dokumentum aláírási sorának eléréséhez az Aspose.Words for .NET használatával a megfelelő metódus vagy tulajdonság segítségével lekérheti az aláírási vonal alakját a dokumentum szerkezetéből. Használhatja például a`GetChild` módszert a megfelelő paraméterekkel, hogy megkapjuk a kívánt aláírási vonal alakzatot.

#### K: Beállíthatom az aláírásszolgáltató azonosítóját több aláírási sorhoz egy Word-dokumentumban?

 V: Igen, beállíthatja az aláírásszolgáltató azonosítóját több aláírási sorhoz egy Word-dokumentumban. Iterálhatja a dokumentum aláírási sorainak gyűjteményét, és minden aláírási sorhoz külön-külön beállíthatja a szolgáltatói azonosítót a`SignOptions.ProviderId` ingatlan.

#### K: Mi a célja az aláírás-szolgáltató azonosítójának egy Word-dokumentumban?

V: Az aláírás-szolgáltató azonosítója egy Word-dokumentumban a digitális aláírás létrehozásáért és kezeléséért felelős entitás vagy szervezet azonosítását szolgálja. Segít a digitális aláírás hitelességének és megbízhatóságának megállapításában azáltal, hogy egy adott szolgáltatóhoz rendeli.

#### K: Milyen típusú digitális tanúsítványok használhatók az aláírás-szolgáltató azonosítójának beállítására egy Word-dokumentumban?

V: A megfelelő szolgáltatói adatokkal rendelkező X.509 digitális tanúsítványok segítségével beállíthatja az aláírás-szolgáltató azonosítóját egy Word-dokumentumban. A digitális tanúsítványt egy megbízható tanúsító hatóságnak (CA) kell kiadnia, és tartalmaznia kell a szolgáltató azonosításához szükséges metaadatokat.