---
title: Word dokumentumok egyesítése
linktitle: Dokumentumok egyesítése
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan egyesíthet több Word-dokumentumot az Aspose.Words for .NET használatával. Ez a hatékony API leegyszerűsíti a dokumentumok egyesítésének folyamatát, ezáltal hatékony és egyszerű.
type: docs
weight: 10
url: /hu/net/split-document/merge-documents/
---

Ebben az oktatóanyagban végigvezetjük, hogyan egyesíthet több Word-dokumentumot az Aspose.Words for .NET Dokumentumok egyesítése funkciójával. Kövesse az alábbi lépéseket a forráskód megértéséhez, és az összes forrásdokumentumot tartalmazó egyesített dokumentum létrehozásához.

## 1. lépés: Keresse meg az egyesítendő dokumentumokat

A dokumentumok egyesítése előtt meg kell találnunk az összevonandó forrásdokumentumokat. Itt van, hogyan:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Az egyesítendő dokumentumok keresése.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## 2. lépés: Egyesítse a dokumentumokat

Most egyenként egyesítjük a dokumentumokat, hogy létrehozzuk a végleges egyesített dokumentumot. Itt van, hogyan:

```csharp
// Nyissa meg a kapott dokumentum első részét.
Document sourceDoc = new Document(sourceDocumentPath);

// Hozzon létre egy új eredményül kapott dokumentumot.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Egyesítse a dokumentumokat egyenként.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Példa forráskódra az Aspose.Words for .NET használatával egyesített dokumentumokhoz

Íme az Aspose.Words for .NET Dokumentumok egyesítése funkciójának teljes forráskódja:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Keressen dokumentumokat az egyesítéshez.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Nyissa meg a kapott dokumentum első részét.
Document sourceDoc = new Document(sourceDocumentPath);

// Hozzon létre egy új eredményül kapott dokumentumot.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// A dokumentumrészek egyesítése egyesével.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## Következtetés

Gratulálunk! Megtanulta, hogyan lehet több Word-dokumentumot egyesíteni az Aspose.Words for .NET Dokumentumok egyesítése funkciójával. A megadott forráskód követésével külön dokumentumokat egyesíthet egyetlen egyesített dokumentummá, miközben megőrzi az egyes forrásdokumentumok formázását.

dokumentumok egyesítése akkor lehet hasznos, ha több forrásból származó információkat szeretne egyesíteni, vagy egyes részekből egységes dokumentumot szeretne létrehozni. Az Aspose.Words for .NET hatékony API-t biztosít, amely leegyszerűsíti a dokumentumok egyesítésének folyamatát, ezáltal hatékony és egyszerű.

Nyugodtan fedezze fel az Aspose.Words for .NET által kínált egyéb funkciókat a dokumentumfeldolgozási képességek javítása és a munkafolyamat egyszerűsítése érdekében.

### GYIK

#### Hogyan egyesíthetek különböző formátumú dokumentumokat?

 A dokumentumok egyesítésekor az Aspose.Words for .NET lehetőséget biztosít az egyes forrásdokumentumok formázásának megőrzésére. Használatával a`ImportFormatMode.KeepSourceFormatting` opciót, az egyesített dokumentum megtartja az eredeti dokumentumok formázását. Ha konzisztens formázást szeretne alkalmazni az egyesített dokumentumban, módosíthatja a formázást az Aspose.Words API segítségével a dokumentumok egyesítése után.

#### Összevonhatom a különböző formátumú dokumentumokat?

Igen, az Aspose.Words for .NET támogatja a különböző formátumú dokumentumok egyesítését, beleértve a DOCX, DOC, RTF és egyebeket. Különböző formátumú dokumentumokat tölthet be az Aspose.Words API-ba, és egyesítheti őket egyetlen dokumentumba, függetlenül az eredeti formátumtól.

#### Összevonhatok-e összetett szerkezetű dokumentumokat, például táblázatokat és képeket?

Teljesen! Az Aspose.Words for .NET képes összetett struktúrájú dokumentumok egyesítésére, beleértve a táblázatokat, képeket, fejlécet, láblécet és egyebeket. Az API kezeli az egyesítési folyamatot, miközben megőrzi a tartalom integritását és elrendezését az egyes dokumentumokban.

#### Lehetséges a különböző oldaltájolású vagy méretű dokumentumok egyesítése?

Igen, az Aspose.Words for .NET különböző oldaltájolású vagy méretű dokumentumokat kezel az egyesítési folyamat során. Az eredményül kapott egyesített dokumentum alkalmazkodik a forrásdokumentumok eltérő oldaltájolásához és méretéhez.