---
title: Export do Markdown se zarovnáním obsahu tabulky
linktitle: Export do Markdown se zarovnáním obsahu tabulky
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se exportovat obsah tabulky s různým zarovnáním do souborů Markdown pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Zde je podrobný průvodce, který vysvětluje následující zdrojový kód C#, který pomáhá exportovat obsah do souboru Markdown se zarovnáním obsahu tabulky pomocí knihovny Aspose.Words pro .NET. Před použitím tohoto kódu se ujistěte, že jste do projektu zahrnuli knihovnu Aspose.Words.

## Krok 1: Nastavte cestu k adresáři dokumentu

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Ujistěte se, že jste zadali správnou cestu k adresáři dokumentů, kam se upravený dokument uloží.

## Krok 2: Vytvořte dokument a generátor dokumentů

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Zde vytvoříme instanci`Document` třída a instance třídy`DocumentBuilder` třída, která nám umožní manipulovat s dokumentem a přidávat prvky.

## Krok 3: Vložte buňky do tabulky s různým zarovnáním odstavců

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Pomocí Tvůrce dokumentů vložíme buňky do tabulky a pro každou buňku nastavíme jiné zarovnání odstavce.

## Krok 4: Nastavte možnosti exportu Markdown a uložte upravený dokument

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

Nastavíme možnosti exportu Markdown s různými zarovnáními obsahu tabulky a poté upravený dokument uložíme pomocí každé možnosti zarovnání.

### Příklad zdrojového kódu pro export do Markdown se zarovnáním obsahu tabulky pomocí Aspose.Words for .NET

```csharp

            
	// Cesta k adresáři dokumentů.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Umožňuje zarovnat všechny odstavce uvnitř tabulky.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// Zarovnání v tomto případě bude převzato z prvního odstavce v odpovídajícím sloupci tabulky.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Uložte upravený dokument
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
