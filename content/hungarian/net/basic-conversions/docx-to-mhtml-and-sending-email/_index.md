---
title: A Docx konvertálása Mhtml-re és e-mail küldése
linktitle: A Docx konvertálása Mhtml-re és e-mail küldése
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan konvertálhat Word dokumentumokat Docx-ből MHTML-be, és hogyan küldheti el e-mailben az Aspose.Words és az Aspose.Email használatával. Lépésről lépésre bemutató.
type: docs
weight: 10
url: /hu/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

Ebben a lépésenkénti oktatóanyagban bemutatjuk, hogyan használhatja az Aspose.Words for .NET alkalmazást a Docx formátumú Word-dokumentumok MHTML-formátumba való konvertálásához, és az Aspose.Email használatával e-mailben történő elküldéséhez. Elmagyarázzuk a mellékelt C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe.

 A kezdéshez győződjön meg arról, hogy az Aspose.Words for .NET és az Aspose.Email könyvtárak telepítve vannak és be vannak állítva a fejlesztői környezetben. Ha még nem tette meg, töltse le és telepítse a könyvtárakat innen[Aspose.Releases](https://releases.aspose.com/words/net/).

## 1. lépés: A dokumentumobjektum inicializálása

 Először inicializálja a`Document`objektum a forrásdokumentum elérési útjával Docx formátumban:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## 2. lépés: A dokumentum mentése MHTML formátumban

 Ezután mentse a dokumentumot a`Stream` objektum MHTML formátumban:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## 3. lépés: Az adatfolyam visszatekerése

Mivel az Aspose.Email-nek az elejétől kell olvasnia az adatfolyamot, tekerje vissza az adatfolyamot az elejére:

```csharp
stream.Position = 0;
```

## 4. lépés: Aspose.Email MIME üzenet létrehozása

 Hozzon létre egy`MailMessage` objektumot a folyamból használva`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Nyugodtan testreszabhatja az üzenet tulajdonságait, például a feladót, a címzettet és a tárgyat.

## 5. lépés: E-mail küldése

 Használja az Aspose.Email-t`SmtpClient` e-mail küldéséhez:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Győződjön meg arról, hogy a megfelelő SMTP-kiszolgáló gazdagépcímét adta meg.

Ez az! Sikeresen konvertált egy Word dokumentumot Docx formátumban MHTML-re, és e-mailben elküldte az Aspose.Words for .NET és az Aspose.Email használatával.

### Példa forráskódra a Docx to Mhtml-hez és az e-mailek küldéséhez az Aspose.Words for .NET használatával

```csharp

	// Document doc = new Document(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//Tekerje vissza az adatfolyamot az elejére, hogy az Aspose.Email elolvashassa.
	stream.Position = 0;

	// Hozzon létre egy Aspose.Email MIME e-mail üzenetet az adatfolyamból.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Küldje el az üzenetet az Aspose.Email használatával.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Nyugodtan használja ezt a kódot saját projektjeiben, és módosítsa saját igényei szerint.

### GYIK

#### Hogyan lehet DOCX fájlt MHTML-re konvertálni?

A DOCX-fájlok MHTML-re konvertálásához használhat szoftvereszközöket vagy könyvtárakat, amelyek biztosítják ezt a funkciót. Az Aspose.Words for .NET megbízható megoldás ehhez az átalakításhoz. A könyvtár API segítségével betöltheti a DOCX fájlt és mentheti MHTML formátumban.

#### Hogyan küldhetek e-mailt MHTML fájlmelléklettel?

Ha MHTML-fájlt csatolt e-mailben szeretne elküldeni, használhat könyvtárakat vagy speciális e-mail-küldési eszközöket, mint például a System.Net.Mail a .NET-ben. Létre kell hoznia egy e-mail üzenetet, meg kell adnia a címzettet, a tárgyat és a tartalmat, majd elküldése előtt csatolnia kell az MHTML-fájlt az üzenethez.

#### Milyen korlátai vannak az e-mailek átalakítási és küldési folyamatának?

Az e-mailek konverziós és küldési folyamatának korlátai az Ön által használt konkrét eszközöktől függenek. Egyes eszközök korlátozásokat tartalmazhatnak a fájlmérettel, a biztonsági beállításokkal vagy a támogatott e-mail protokollokkal kapcsolatban. Fontos, hogy az igényeinek megfelelő eszközöket válasszon, és a megvalósítás során vegye figyelembe ezeket a korlátokat.

#### Megbízható eszköz az Aspose a DOCX-ből MHTML-be konvertálásához és az e-mailek küldéséhez?

Igen, az Aspose.Words for .NET egy megbízható eszköz a DOCX-ről MHTML-re konvertálásához és az e-mailek küldéséhez. A fejlesztők és a szakemberek széles körben használják teljesítménye és minősége miatt. Az eszköz átfogó dokumentációt, speciális szolgáltatásokat és dedikált technikai támogatást kínál, így ezekhez a feladatokhoz ajánlott választás.