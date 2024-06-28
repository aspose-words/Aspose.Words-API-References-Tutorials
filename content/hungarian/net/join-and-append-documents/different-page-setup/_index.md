---
title: Különböző oldalbeállítások
linktitle: Különböző oldalbeállítások
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan fűzhet hozzá dokumentumokat különböző oldalbeállítási beállításokkal az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/different-page-setup/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET egy eltérő oldalbeállítási beállításokkal rendelkező dokumentum másik dokumentumhoz fűzéséhez. A mellékelt forráskód bemutatja, hogyan állíthat be különböző oldalbeállításokat a forrás- és céldokumentumokhoz, és hogyan biztosíthatja a megfelelő folytatást és számozást.

## 1. lépés: Állítsa be a projektet

Győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

-  Aspose.Words for .NET könyvtár telepítve. Letöltheti innen[Aspose.Releases]https://releases.aspose.com/words/net/ vagy használja a NuGet csomagkezelőt a telepítéséhez.
- Egy dokumentumkönyvtár elérési útja, ahol a forrás- és céldokumentum található.

## 2. lépés: Nyissa meg a forrás- és céldokumentumot

 Nyissa meg a forrás- és céldokumentumot a segítségével`Document` osztályú konstruktőr. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. lépés: Állítsa be a forrásdokumentum oldalbeállításait

 Módosítsa a forrásdokumentum oldalbeállítási beállításait a megfelelő folytatás és számozás érdekében. Ebben a példában a szakasz kezdetét állítjuk be`SectionStart.Continuous`és indítsa újra az oldalszámozást. Gondoskodunk arról is, hogy az oldal szélessége, magassága és tájolása megegyezzen a céldokumentum utolsó részével.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## 4. lépés: Módosítsa a bekezdés formázását

 A megfelelő formázás megőrzése érdekében ismételje meg a forrásdokumentum összes bekezdését, és állítsa be a`KeepWithNext`tulajdonát`true`. Ez biztosítja, hogy a bekezdések együtt maradjanak a hozzáfűzési folyamat során.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 5. lépés: A forrásdokumentum hozzáfűzése a céldokumentumhoz

 Használja a`AppendDocument` a céldokumentum módszere, amellyel a módosított forrásdokumentumot hozzáfűzi a céldokumentumhoz, megőrizve a forrás formázását.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6. lépés: Mentse el a céldokumentumot

Végül mentse el a módosított céldokumentumot a`Save` módszere a`Document` tárgy.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Ezzel befejeződik a különböző oldalbeállítási beállításokkal rendelkező dokumentumok hozzáfűzésének megvalósítása az Aspose.Words for .NET használatával.

### Példa forráskódra különböző oldalbeállításokhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Állítsa be a forrásdokumentumot úgy, hogy közvetlenül a céldokumentum vége után folytassa.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Indítsa újra az oldalszámozást a forrásdokumentum elején.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	//Annak érdekében, hogy ez ne forduljon elő, ha a forrásdokumentum eltérő oldalbeállításokkal rendelkezik, győződjön meg arról, hogy a
	// a beállítások megegyeznek a céldokumentum utolsó részében.
	// Ha további folyamatos szakaszok következnek a forrásdokumentumban,
	// ezt meg kell ismételni azoknál a szakaszoknál.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Ismételje meg a forrásdokumentum összes szakaszát.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```