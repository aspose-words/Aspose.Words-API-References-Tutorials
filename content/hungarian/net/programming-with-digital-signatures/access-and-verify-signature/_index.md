---
title: Hozzáférés és aláírás ellenőrzése Word dokumentumban
linktitle: Hozzáférés és aláírás ellenőrzése Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan érheti el és ellenőrizheti a digitális aláírásokat egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-digital-signatures/access-and-verify-signature/
---
Ebben az oktatóanyagban végigvezetjük az Aspose.Words for .NET hozzáférés- és aláírás-ellenőrzési funkciójának használatának lépésein. Ez a funkció lehetővé teszi a digitális aláírások elérését egy Word-dokumentumban és azok érvényességének ellenőrzését. Kövesse az alábbi lépéseket:

## 1. lépés: A dokumentum betöltése és az aláírások elérése

Kezdje a digitális aláírást tartalmazó dokumentum feltöltésével:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## 2. lépés: Tallózás a digitális aláírások között

Használjon hurkot a dokumentumban lévő összes digitális aláírás áthaladásához:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Hozzáférés az aláírási információkhoz
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Ez a tulajdonság csak az MS Word dokumentumokban érhető el.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Ügyeljen arra, hogy a kijelző üzeneteit az Ön igényei szerint szabja testre.

### Példa forráskód a hozzáféréshez és az aláírás ellenőrzéséhez az Aspose.Words for .NET használatával

Íme a teljes forráskód az Aspose.Words for .NET-hez való hozzáféréshez és aláírás-ellenőrzéshez:

```csharp
	
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Ez a tulajdonság csak az MS Word dokumentumokban érhető el.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Ha követi ezeket a lépéseket, az Aspose.Words for .NET segítségével könnyedén elérheti és ellenőrizheti a Word-dokumentumban lévő digitális aláírásokat.

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk a Word-dokumentumok digitális aláírásainak elérését és ellenőrzését az Aspose.Words for .NET használatával. A megadott lépések követésével könnyedén betölthet egy dokumentumot, hozzáférhet a digitális aláírásához, és ellenőrizheti azok érvényességét. A digitális aláírásokhoz való hozzáférés és azok ellenőrzése lehetővé teszi a Word-dokumentumok integritásának és hitelességének biztosítását. Az Aspose.Words for .NET hatékony API-t kínál a szövegfeldolgozáshoz digitális aláírással, amely lehetővé teszi az ellenőrzési folyamat automatizálását és a dokumentumok biztonságának fokozását.

### GYIK

#### K: Mik azok a digitális aláírások egy Word-dokumentumban?

V: A Word dokumentumokban lévő digitális aláírások olyan elektronikus aláírások, amelyek lehetővé teszik a dokumentum integritásának és eredetének hitelesítését. Digitális tanúsítványokkal és kriptográfiai algoritmusokkal hozzák létre, így a címzett ellenőrizheti, hogy a dokumentumot nem módosították, és megbízható forrásból származik-e.

#### K: Hogyan érhetek el digitális aláírásokat egy Word-dokumentumban az Aspose.Words for .NET használatával?

V: Az Aspose.Words for .NET használatával a Word-dokumentumban lévő digitális aláírások eléréséhez kövesse az alábbi lépéseket:
1.  Töltse be a dokumentumot a gombbal`Document` osztályt, és adja meg a dokumentumfájl elérési útját.
2.  Használjon hurkot a`DigitalSignatures` a dokumentumok gyűjteménye. Minden iteráció egy digitális aláírást jelent.

#### K: Milyen információkhoz férhetek hozzá egy Word-dokumentumban lévő digitális aláírásból?

V: A Word-dokumentumban lévő digitális aláírásból különféle információkhoz férhet hozzá, például:
- Érvényesség: Ellenőrizze, hogy az aláírás érvényes-e.
- Megjegyzések: Olvassa el az aláíró által megadott aláírás okát.
- Aláírási idő: A dokumentum aláírásának időpontja.
- Tárgy neve: Az aláíró vagy a tanúsítvány alanya nevének lekérése.
- Kibocsátó neve: Szerezze meg a tanúsítvány kibocsátójának nevét.

#### K: Ellenőrizhetem egy Word-dokumentumban lévő digitális aláírás érvényességét az Aspose.Words for .NET használatával?

 V: Igen, ellenőrizheti egy Word-dokumentumban lévő digitális aláírás érvényességét az Aspose.Words for .NET használatával. A hozzáféréssel a`IsValid` tulajdona a`DigitalSignature` objektum esetén meghatározhatja, hogy az aláírás érvényes-e vagy sem.

#### K: Hogyan ellenőrizhetem a digitális aláírások érvényességét egy Word-dokumentumban az Aspose.Words for .NET használatával?

V: A Word-dokumentumban lévő digitális aláírások érvényességének ellenőrzéséhez az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:
1.  Hozzáférés a`DigitalSignatures` a dokumentumok gyűjteménye.
2.  Ismételje meg mindegyiket`DigitalSignature` tárgy a gyűjteményben.
3.  Használja a`IsValid` tulajdona a`DigitalSignature` objektumot, hogy ellenőrizze, hogy az aláírás érvényes-e.

#### K: Lekérhetem az aláíró megjegyzéseit vagy az aláírás indokát egy Word dokumentumban lévő digitális aláírásból?

V: Igen, lekérheti az aláíró megjegyzéseit vagy az aláírás indokait egy Word-dokumentumban lévő digitális aláírásból. A`Comments` tulajdona a`DigitalSignature` Az objektum hozzáférést biztosít az aláíró által az aláírási folyamat során megadott megjegyzésekhez.

#### K: Milyen típusú dokumentumokat támogat az aláírás-ellenőrzési funkció az Aspose.Words for .NET-ben?

V: Az Aspose.Words for .NET aláírás-ellenőrzési funkciója támogatja a DOCX fájlformátumú Word dokumentumok digitális aláírásainak ellenőrzését. Ezzel a funkcióval ellenőrizheti a DOCX-fájlok aláírásait.

#### K: Hogyan érhetem el a Word-dokumentumban lévő digitális aláírás tanúsítványának részleteit az Aspose.Words for .NET használatával?

 V: A Word-dokumentumban lévő digitális aláírás tanúsítvány részleteinek eléréséhez az Aspose.Words for .NET használatával elérheti a`CertificateHolder` tulajdona a`DigitalSignature` tárgy. Tól`CertificateHolder` objektumhoz, lekérheti a tanúsítvány különféle részleteit, például az alany nevét és a kibocsátó nevét.

#### K: Testreszabhatom a digitális aláírások megjelenítését vagy feldolgozását egy Word-dokumentumban az Aspose.Words for .NET használatával?

 V: Igen, személyre szabhatja a digitális aláírások megjelenítését vagy feldolgozását egy Word-dokumentumban az Aspose.Words for .NET segítségével. A tulajdonságaihoz és metódusaihoz való hozzáféréssel a`DigitalSignature` objektum, kivonhatja a kívánt információkat, további ellenőrzéseket hajthat végre, vagy integrálhatja az aláírás-ellenőrzési folyamatot az alkalmazás munkafolyamatába.

#### K: Ellenőrizhető több digitális aláírás egy Word-dokumentumban az Aspose.Words for .NET használatával?

 V: Igen, lehetséges több digitális aláírás ellenőrzése egy Word-dokumentumban az Aspose.Words for .NET használatával. Iterációval a`DigitalSignatures` a dokumentum gyűjteményét, minden egyes digitális aláírást külön-külön érhet el és ellenőrizhet.

