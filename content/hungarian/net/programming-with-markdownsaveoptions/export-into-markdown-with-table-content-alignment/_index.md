---
title: Exportálás a Markdown-ba a táblázattartalom igazításával
linktitle: Exportálás a Markdown-ba a táblázattartalom igazításával
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan exportálhat különböző igazítású táblázattartalmakat Markdown-fájlokba az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Itt található egy lépésről lépésre bemutatott útmutató a következő C#-forráskódhoz, amely segít a tartalom exportálásában Markdown-fájlba a táblázattartalom-igazítással az Aspose.Words könyvtár .NET-hez segítségével. A kód használata előtt győződjön meg arról, hogy az Aspose.Words könyvtárat belefoglalta a projektbe.

## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Ügyeljen arra, hogy megadja a dokumentumkönyvtár megfelelő elérési útját, ahová a szerkesztett dokumentum mentésre kerül.

## 2. lépés: Hozzon létre egy dokumentumot és egy dokumentumgenerátort

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Itt létrehozunk egy példányt a`Document` osztály és egy példánya a`DocumentBuilder` osztály, amely lehetővé teszi számunkra a dokumentum kezelését és elemek hozzáadását.

## 3. lépés: Szúrjon be cellákat a táblázatba különböző bekezdésigazításokkal

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

A Dokumentumkészítő segítségével cellákat szúrunk be a táblázatba, és minden cellához különböző bekezdésigazítást állítunk be.

## 4. lépés: Állítsa be a Markdown exportálási beállításait, és mentse el a módosított dokumentumot

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

A Markdown exportálási beállításait különböző táblázattartalom-igazításokkal állítjuk be, majd az egyes igazítási beállításokkal elmentjük a módosított dokumentumot.

### Példa forráskód a Markdownba exportálandó táblázattartalom-igazítással az Aspose.Words for .NET használatával

```csharp

            
	// A dokumentumok könyvtárának elérési útja.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// A táblázaton belüli összes bekezdést igazítandóvá teszi.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// Az igazítás ebben az esetben a megfelelő táblázatoszlop első bekezdéséből történik.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Mentse el a módosított dokumentumot
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
