---
title: Hozzon létre új aláírási sort és állítsa be a szolgáltatói azonosítót
linktitle: Hozzon létre új aláírási sort és állítsa be a szolgáltatói azonosítót
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre új aláírási sort és állíthat be szolgáltatói azonosítót egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
Ebben az oktatóanyagban végigvezetjük az Új aláírási sor létrehozása és a Szolgáltató-azonosító beállítása funkció használatának lépésein az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi aláírási sor beszúrását egy Word dokumentumba, egyéni beállítások megadását és a dokumentum aláírását. Kövesse az alábbi lépéseket:

## 1. lépés: A dokumentum és a generátor létrehozása

Először hozzon létre egy példányt a Document osztályból és egy DocumentBuilder objektumból:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Az aláírási sor beállításainak megadása

Hozzon létre egy példányt a SignatureLineOptions osztályból, és állítsa be a kívánt beállításokat:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## 3. lépés: Az aláírási sor beszúrása

A DocumentBuilder objektum InsertSignatureLine() metódusával illessze be az aláírási sort a dokumentumba:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## 4. lépés: Állítsa be a szolgáltató azonosítóját

Állítsa be az aláírási sor szolgáltatói azonosítóját a ProviderId tulajdonság segítségével:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Ügyeljen arra, hogy a használati esetnek megfelelő szolgáltatói azonosítót adja meg.

## 5. lépés: Mentse el a dokumentumot

Mentse el a módosított dokumentumot:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a dokumentum mentéséhez.

## 6. lépés: A dokumentum aláírása

A dokumentum aláírásához be kell állítania az aláírási beállításokat, és használnia kell a DigitalSignatureUtil osztályt:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Feltétlenül adja meg a dokumentum, a tanúsítvány és az aláírt dokumentum helyes elérési útját.

### Példa forráskód az Új aláírási sor létrehozásához és a szolgáltatói azonosító beállításához az Aspose.Words for .NET használatával

Itt található a teljes forráskód egy új aláírási sor létrehozásához és a szolgáltatói azonosító beállításához az Aspose.Words for .NET-hez:

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Ezeket a lépéseket követve egyszerűen létrehozhat egy új aláírási sort, és beállíthatja a szolgáltatói azonosítót a Word-dokumentumban az Aspose.Words for .NET segítségével.

## Következtetés

Ebben az oktatóanyagban az Aspose.Words for .NET segítségével új aláírási sor létrehozásának és a szolgáltatói azonosító beállításának lehetőségét vizsgáltuk meg egy Word-dokumentumban. A megadott lépések követésével egyszerűen beilleszthet egy aláírási sort egyéni beállításokkal, és társíthatja azt egy adott szolgáltatóhoz a szolgáltatói azonosító használatával. Az aláírási sorok hozzáadása és a szolgáltatói adatok testreszabása javítja a dokumentumok hitelességét és megbízhatóságát. Az Aspose.Words for .NET hatékony API-t biztosít a Word Processing számára aláírási sorokkal és digitális tanúsítványokkal a Word dokumentumokban, lehetővé téve az aláírási folyamat automatizálását és a dokumentumok érvényességének biztosítását.

### GYIK

#### K: Mi az a szolgáltatói azonosító az aláírási sorban?

V: Az aláírássorban szereplő szolgáltatói azonosító egy egyedi azonosító, amely a digitális aláírás szolgáltatóját jelöli. Segít azonosítani az aláírásért felelős forrást vagy szervezetet.

#### K: Hogyan hozhatok létre új aláírássort egy Word-dokumentumban az Aspose.Words for .NET használatával?

V: Ha új aláírási sort szeretne létrehozni egy Word-dokumentumban az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:
1.  Hozzon létre egy példányt a`Document` osztály és a`DocumentBuilder` tárgy.
2.  Hozzon létre egy példányt a`SignatureLineOptions` osztályt, és állítsa be a kívánt aláírási sor opciókat.
3.  Használja a`InsertSignatureLine` módszere a`DocumentBuilder` objektumot az aláírási sor beillesztéséhez a dokumentumba.

#### K: Testreszabhatom az aláírási sor beállításait, például az aláíró nevét, címét és utasításait?

 V: Igen, testreszabhatja az aláírási sor beállításait. A`SignatureLineOptions` osztály tulajdonságokat biztosít a kívánt opciók beállításához, mint pl`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, stb. Az aláírási sor beszúrása előtt módosíthatja ezeket a tulajdonságokat.

#### K: Mi a célja az aláírási sor szolgáltatói azonosítójának beállításának?

V: Az aláírási sor szolgáltatói azonosítójának beállítása segít azonosítani a digitális aláírásért felelős forrást vagy szervezetet. Lehetővé teszi, hogy az aláírást egy adott szolgáltatóhoz vagy entitáshoz társítsa, további információkat biztosítva az aláírás eredetéről és megbízhatóságáról.

#### K: Hogyan állíthatom be egy aláírási sor szolgáltatói azonosítóját az Aspose.Words for .NET használatával?

V: Az Aspose.Words for .NET használatával egy aláírási sor szolgáltatói azonosítójának beállításához kövesse az alábbi lépéseket:
1.  Az aláírási sor beszúrása után nyissa meg a`ProviderId` tulajdona a`SignatureLine` tárgy.
2.  Állítsa be a`ProviderId` tulajdonságot a kívánt szolgáltató azonosító értékéhez használja a`Guid` adattípus.

#### K: Aláírhatom a dokumentumot egy új aláírási sor létrehozása és a szolgáltatói azonosító beállítása után?

 V: Igen, az új aláírási sor létrehozása és a szolgáltatói azonosító beállítása után aláírhatja a dokumentumot. A dokumentum aláírásához be kell állítania az aláírási beállításokat, beleértve az aláírási sor azonosítóját, a szolgáltató azonosítóját, a megjegyzéseket és az aláírási időt. Ezután használja a`DigitalSignatureUtil.Sign` módszer a dokumentum digitális tanúsítvánnyal történő aláírására.

#### K: Megadhatok egy adott szolgáltatói azonosítót a Word-dokumentum minden aláírási sorához?

V: Igen, megadhat egy adott szolgáltatói azonosítót a Word-dokumentum minden aláírási sorához. Az egyes aláírási sorok beillesztése után beállíthatja az adott aláírási sorhoz tartozó szolgáltatói azonosítót a következő megnyitásával`ProviderId` az illető tulajdona`SignatureLine` tárgy.

#### K: Hogyan menthetem el a módosított dokumentumot egy új aláírási sor létrehozása és a szolgáltatói azonosító beállítása után?

 V: A módosított dokumentum mentéséhez új aláírási sor létrehozása és a szolgáltatói azonosító beállítása után használhatja a`Save` módszere a`Document` tárgy. Adja meg a megfelelő elérési utat és fájlnevet a dokumentum mentéséhez.

#### K: Milyen fájlformátumot támogat az Aspose.Words for .NET az aláírási sorok létrehozásához és aláírásához?

V: Az Aspose.Words for .NET támogatja az aláírási sorok létrehozását és aláírását DOCX fájlformátumban. Létrehozhat és aláírhat aláírási sorokat DOCX-fájlokban a megadott metódusok és osztályok használatával.

#### K: Módosíthatom az aláírási sor szolgáltatói azonosítóját vagy egyéb beállításait az aláírás után?

V: Az aláírási sor aláírása után a dokumentum tartalmának részévé válik, és külön nem módosítható. Az aláírási sor bármilyen módosítása, például a szolgáltatói azonosító vagy egyéb beállítások módosítása a meglévő aláírás eltávolítását és egy új aláírási sor létrehozását igényli.