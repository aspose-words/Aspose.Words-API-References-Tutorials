---
title: Dokumentumfájl formátum észlelése
linktitle: Dokumentumfájl formátum észlelése
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre útmutató a dokumentumfájl-formátum felismeréséhez az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-fileformat/detect-file-format/
---

Ez a cikk lépésről lépésre bemutatja a dokumentumfájl-formátum-észlelési szolgáltatás használatát az Aspose.Words for .NET-hez. Részletesen elmagyarázzuk a kód minden részét. Ennek az oktatóanyagnak a végén megértheti, hogyan lehet felismerni a különböző dokumentumfájlok formátumát.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette és konfigurálta az Aspose.Words for .NET könyvtárat a projektben. A könyvtárat és a telepítési utasításokat az Aspose webhelyén találja.

## 1. lépés: Adja meg a könyvtárakat

 A kezdéshez meg kell határoznia azokat a könyvtárakat, amelyekben a fájlokat tárolni kívánja, formátumuk szerint. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával. Létrehozzuk a "Támogatott", "Ismeretlen", "Titkosított" és "Pre97" könyvtárakat, ha még nem léteznek.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Hozza létre a könyvtárakat, ha még nem léteznek.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## 2. lépés: Tallózás a fájlok között

 Ezután használjuk a`GetFiles` módszere a`Directory` osztályba, hogy megkapja a megadott könyvtárban lévő fájlok listáját. Használjuk továbbá a`Where`záradék egy adott "Sérült dokumentum.docx" nevű fájl kizárására.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## 3. lépés: Határozza meg az egyes fájlok formátumát

 Végigpörgetjük a listában szereplő fájlokat, és használjuk a`DetectFileFormat` módszere a`FileFormatUtil` osztályt a fájl formátumának észleléséhez. Megjelenítjük az észlelt dokumentumtípust is.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Jelenítse meg a dokumentum típusát
switch (info.LoadFormat)
{
LoadFormat.Doc box:
Console.WriteLine("\tDocument Microsoft Word 97-2003.");
break;
LoadFormat.Dot box:
Console.WriteLine("\tMicrosoft Word 97-2003 template.");
break;
LoadFormat.Docx box:
Console.WriteLine("\tDocument Office Open XML WordprocessingML without macros.");
break;
// ... Adjon hozzá eseteket más támogatott dokumentumformátumokhoz
LoadFormat.Unknown case:
Console.WriteLine("\tFormat in

known.");
break;
}

if (info.IsEncrypted)
{
Console.WriteLine("\tAn encrypted document.");
File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
}
else
{
switch (info.LoadFormat)
{
LoadFormat.DocPreWord60 box:
File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
break;
LoadFormat.Unknown case:
File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
break;
default:
File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
break;
}
}
}
```

Ez minden ! Sikeresen észlelte a különböző dokumentumfájlok formátumát az Aspose.Words for .NET segítségével.

### Példa forráskód fájlformátum észleléséhez az Aspose.Words for .NET segítségével

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Hozza létre a könyvtárakat, ha még nem léteznek.
	if (Directory.Exists(supportedDir) == false)
		Directory.CreateDirectory(supportedDir);
	if (Directory.Exists(unknownDir) == false)
		Directory.CreateDirectory(unknownDir);
	if (Directory.Exists(encryptedDir) == false)
		Directory.CreateDirectory(encryptedDir);
	if (Directory.Exists(pre97Dir) == false)
		Directory.CreateDirectory(pre97Dir);

	
	IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
	
	foreach (string fileName in fileList)
	{
		string nameOnly = Path.GetFileName(fileName);
		
		Console.Write(nameOnly);
		
		FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

		// Jelenítse meg a dokumentum típusát
		switch (info.LoadFormat)
		{
			case LoadFormat.Doc:
				Console.WriteLine("\tMicrosoft Word 97-2003 document.");
				break;
			case LoadFormat.Dot:
				Console.WriteLine("\tMicrosoft Word 97-2003 template.");
				break;
			case LoadFormat.Docx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
				break;
			case LoadFormat.Docm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
				break;
			case LoadFormat.Dotx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
				break;
			case LoadFormat.Dotm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
				break;
			case LoadFormat.FlatOpc:
				Console.WriteLine("\tFlat OPC document.");
				break;
			case LoadFormat.Rtf:
				Console.WriteLine("\tRTF format.");
				break;
			case LoadFormat.WordML:
				Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
				break;
			case LoadFormat.Html:
				Console.WriteLine("\tHTML format.");
				break;
			case LoadFormat.Mhtml:
				Console.WriteLine("\tMHTML (Web archive) format.");
				break;
			case LoadFormat.Odt:
				Console.WriteLine("\tOpenDocument Text.");
				break;
			case LoadFormat.Ott:
				Console.WriteLine("\tOpenDocument Text Template.");
				break;
			case LoadFormat.DocPreWord60:
				Console.WriteLine("\tMS Word 6 or Word 95 format.");
				break;
			case LoadFormat.Unknown:
				Console.WriteLine("\tUnknown format.");
				break;
		}
		

		if (info.IsEncrypted)
		{
			Console.WriteLine("\tAn encrypted document.");
			File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
		}
		else
		{
			switch (info.LoadFormat)
			{
				case LoadFormat.DocPreWord60:
					File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
					break;
				case LoadFormat.Unknown:
					File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
					break;
				default:
					File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
					break;
			}
		}
	}
	

```

### GYIK a dokumentum fájlformátum észleléséhez

#### Hogyan lehet felismerni egy dokumentumfájl formátumát az Aspose.Words for .NET használatával?

 A dokumentumfájl formátumának észleléséhez az Aspose.Words for .NET használatával, kövesse az oktatóanyagban található lépéseket. Használni a`DetectFileFormat` módszere a`FileFormatUtil`osztály lehetővé teszi a dokumentumfájl formátumának észlelését. Ez lehetővé teszi annak meghatározását, hogy Microsoft Word 97-2003 dokumentumról, sablonról, Office Open XML WordprocessingML dokumentumról vagy más támogatott formátumról van-e szó. Az oktatóanyagban található kód végigvezeti a funkció megvalósításán.

#### Milyen dokumentumformátumokat támogat az Aspose.Words for .NET?

Az Aspose.Words for .NET számos dokumentumformátumot támogat, beleértve a Microsoft Word 97-2003 dokumentumokat (DOC), sablonokat (DOT), Office Open XML WordprocessingML dokumentumokat (DOCX), Office Open XML WordprocessingML dokumentumokat makróval (DOCM), Office Open XML WordprocessingML sablonok makrók nélkül (DOTX), Office Open XML WordprocessingML sablonok makróval (DOTM), Flat OPC dokumentumok, RTF dokumentumok, Microsoft Word 2003 WordprocessingML dokumentumok, HTML dokumentumok, MHTML (webarchívum) dokumentumok, OpenDocument Text (ODT) dokumentumok, OpenDocument Text (OTT) sablonok, MS Word 6 vagy Word 95 dokumentumok és ismeretlen dokumentumformátumok.

#### Hogyan kezeljük a titkosított dokumentumfájlokat a formátumészlelés során?

 Egy dokumentumfájl formátumának észlelésekor használhatja a`IsEncrypted` tulajdona a`FileFormatInfo` objektumot, hogy ellenőrizze, hogy a fájl titkosított-e. Ha a fájl titkosított, további lépéseket tehet az adott eset kezelésére, például átmásolhatja a fájlt egy titkosított dokumentumoknak szentelt könyvtárba. Használhatja a`File.Copy` módszer erre.

#### Milyen lépéseket kell tenni, ha egy dokumentum formátuma ismeretlen?

Ha egy dokumentum formátuma ismeretlen, dönthet úgy, hogy az alkalmazásának megfelelő módon kezeli. Az oktatóanyagban bemutatott példában a dokumentum egy adott, ismeretlen formátumú dokumentumok számára fenntartott könyvtárba másolódik. Ezt a műveletet saját igényeinek megfelelően testreszabhatja.

#### Vannak az Aspose.Words for .NET-nek egyéb olyan funkciói, amelyek használhatók a dokumentumformátum-észleléssel együtt?

Igen, az Aspose.Words for .NET számos egyéb szolgáltatást kínál a Word-dokumentumok feldolgozásához és kezeléséhez. A könyvtár segítségével például szöveget, képeket vagy metaadatokat kinyerhet a dokumentumokból, formázási változtatásokat alkalmazhat, dokumentumokat egyesíthet, dokumentumokat konvertálhat különböző formátumokba stb.