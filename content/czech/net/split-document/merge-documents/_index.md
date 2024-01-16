---
title: Sloučit dokumenty aplikace Word
linktitle: Sloučit dokumenty
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se sloučit více dokumentů Word pomocí Aspose.Words for .NET. Toto výkonné API zjednodušuje proces slučování dokumentů, takže je efektivní a přímočaré.
type: docs
weight: 10
url: /cs/net/split-document/merge-documents/
---

V tomto tutoriálu vás provedeme tím, jak sloučit více dokumentů aplikace Word pomocí funkce Sloučit dokumenty Aspose.Words for .NET. Chcete-li porozumět zdrojovému kódu a získat sloučený dokument obsahující všechny zdrojové dokumenty, postupujte podle následujících kroků.

## Krok 1: Vyhledejte dokumenty ke sloučení

Před sloučením dokumentů musíme najít zdrojové dokumenty, které mají být sloučeny. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Vyhledejte dokumenty ke sloučení.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Krok 2: Sloučení dokumentů

Nyní sloučíme dokumenty jeden po druhém, abychom vytvořili konečný sloučený dokument. Zde je postup:

```csharp
// Otevřete první část výsledného dokumentu.
Document sourceDoc = new Document(sourceDocumentPath);

// Vytvořte nový výsledný dokument.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Sloučit dokumenty jeden po druhém.
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

### Příklad zdrojového kódu pro Merge Documents pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro funkci Sloučit dokumenty Aspose.Words pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Najděte dokumenty pomocí pro sloučení.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Otevřete první část výsledného dokumentu.
Document sourceDoc = new Document(sourceDocumentPath);

// Vytvořte nový výsledný dokument.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Sloučit části dokumentu jednu po druhé.
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

## Závěr

Gratulujeme! Naučili jste se sloučit více dokumentů aplikace Word pomocí funkce Sloučit dokumenty Aspose.Words for .NET. Podle poskytnutého zdrojového kódu můžete zkombinovat samostatné dokumenty do jednoho sloučeného dokumentu při zachování formátování každého zdrojového dokumentu.

Sloučení dokumentů může být užitečné, když chcete sloučit informace z více zdrojů nebo vytvořit jednotný dokument z jednotlivých částí. Aspose.Words for .NET poskytuje výkonné API, které zjednodušuje proces slučování dokumentů a činí jej efektivním a přímočarým.

Neváhejte a prozkoumejte další funkce nabízené Aspose.Words pro .NET, abyste zlepšili své možnosti zpracování dokumentů a zefektivnili svůj pracovní postup.

### Nejčastější dotazy

#### Jak mohu sloučit dokumenty s různým formátováním?

 Při slučování dokumentů poskytuje Aspose.Words for .NET možnost zachovat formátování každého zdrojového dokumentu. Pomocí`ImportFormatMode.KeepSourceFormatting` možnost, sloučený dokument si zachová formátování původních dokumentů. Pokud chcete použít konzistentní formátování v celém sloučeném dokumentu, můžete po sloučení dokumentů upravit formátování pomocí Aspose.Words API.

#### Mohu sloučit dokumenty v různých formátech?

Ano, Aspose.Words for .NET podporuje slučování dokumentů v různých formátech, včetně DOCX, DOC, RTF a dalších. Do Aspose.Words API můžete načíst dokumenty různých formátů a sloučit je do jednoho dokumentu bez ohledu na jejich původní formáty.

#### Mohu sloučit dokumenty se složitými strukturami, jako jsou tabulky a obrázky?

Absolutně! Aspose.Words for .NET je schopen slučovat dokumenty se složitými strukturami, včetně tabulek, obrázků, záhlaví, zápatí a dalších. Rozhraní API zpracovává proces slučování při zachování integrity a rozvržení obsahu v každém dokumentu.

#### Je možné sloučit dokumenty s různými orientacemi nebo velikostmi stránek?

Ano, Aspose.Words for .NET zpracovává dokumenty s různou orientací stránky nebo velikostí během procesu slučování. Výsledný sloučený dokument se přizpůsobí různým orientacím stránek a velikostem zdrojových dokumentů.