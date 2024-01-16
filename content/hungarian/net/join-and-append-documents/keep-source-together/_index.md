---
title: Tartsa együtt a forrást
linktitle: Tartsa együtt a forrást
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan használhatja az Aspose.Words for .NET-et Word-dokumentumok összekapcsolására és hozzáfűzésére, miközben a forrástartalom a céldokumentummal együtt marad.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/keep-source-together/
---

Ez az oktatóanyag végigvezeti az Aspose.Words for .NET Forrás együtt tartása funkciójának használatán. Ez a funkció lehetővé teszi több Word-dokumentum összekapcsolását és hozzáfűzését, miközben a forrásdokumentum tartalma együtt marad a céldokumentum tartalmával. 

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

1. Az Aspose.Words for .NET telepítve van. Letöltheti az Aspose webhelyéről, vagy telepítheti a NuGet segítségével.
2. Visual Studio vagy bármely más C# fejlesztői környezet.

## 1. lépés: Inicializálja a dokumentumkönyvtárakat

 Először is be kell állítania a dokumentumkönyvtár elérési útját. Módosítsa az értékét`dataDir` változó ahhoz az elérési úthoz, ahol a dokumentumok találhatók.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a forrás- és céldokumentumot

 Ezután be kell töltenie a forrás- és céldokumentumot az Aspose.Words használatával`Document` osztály. Frissítse a fájlneveket a`Document` konstruktor a dokumentumnevek szerint.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 3. lépés: Állítsa be, hogy a forrásdokumentum a céldokumentum tartalma után jelenjen meg

 Annak biztosításához, hogy a forrásdokumentum közvetlenül a céldokumentum tartalma után jelenjen meg, be kell állítania a`SectionStart` a forrásdokumentum első szakaszának tulajdonsága`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 4. lépés: Állítsa be a "Keep with Next" bekezdésformázást a forrásdokumentumhoz

 forrásdokumentum bekezdéseinek egyben tartásához ismételheti a dokumentum egyes bekezdéseit, és beállíthatja a`KeepWithNext`tulajdonát`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 5. lépés: Csatolja a forrásdokumentumot a céldokumentumhoz

 Most hozzáfűzheti a forrásdokumentumot a céldokumentumhoz a segítségével`AppendDocument` módszere a`Document` osztály. A`ImportFormatMode.KeepSourceFormatting` paraméter biztosítja, hogy a forrás formázása megmaradjon a hozzáfűzési művelet során.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6. lépés: Mentse el a záródokumentumot

 Végül mentse el az egyesített dokumentumot a „Forrás együtt tartása” funkcióval a`Save` módszere a`Document` osztály.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Példa forráskódra a Keep Source Together alkalmazáshoz az Aspose.Words for .NET használatával 

Íme a teljes forráskód a "Keep Source Together" funkcióhoz C# nyelven az Aspose.Words for .NET használatával:


```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Állítsa be, hogy a forrásdokumentum közvetlenül a céldokumentum tartalma után jelenjen meg.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Ez az! Sikeresen implementálta a Forrás együtt tartása funkciót az Aspose.Words for .NET használatával. A végleges dokumentum az összevont tartalmat fogja tartalmazni a forrásdokumentum bekezdéseivel együtt.