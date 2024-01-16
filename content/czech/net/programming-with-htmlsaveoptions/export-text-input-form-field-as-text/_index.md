---
title: Export textového vstupního pole formuláře jako text
linktitle: Export textového vstupního pole formuláře jako text
second_title: Aspose.Words API pro zpracování dokumentů
description: Průvodce krok za krokem pro export polí formuláře pro zadávání textu jako prostý text pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro export polí vstupního formuláře jako prostý text pomocí Aspose.Words pro .NET. Tato funkce umožňuje exportovat pole formuláře pro zadávání textu jako čitelný text, nikoli je exportovat jako vstupní prvky HTML.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument k exportu. K načtení dokumentu ze zadaného adresáře použijte následující kód:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Tento kód vytvoří instanci`Document` načtením dokumentu ze zadaného adresáře.

## Krok 3: Konfigurace možností zálohování HTML

Nyní nakonfigurujeme možnosti uložení HTML pro export polí vstupního textu jako prostý text. Použijte následující kód:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// Zadaná složka musí existovat a být prázdná.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Tento kód vytvoří instanci`HtmlSaveOptions` nastaví`ExportTextInputFormFieldAsText` možnost`true` exportovat pole formuláře pro zadávání textu jako prostý text. Navíc určuje složku, do které budou extrahované obrázky uloženy.

## Krok 4: Převod a uložení dokumentu do HTML

Nakonec převedeme dokument do HTML pomocí dříve nakonfigurovaných možností uložení HTML. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Tento kód převede dokument do HTML exportem polí formuláře pro zadávání textu jako prostý text a uloží exportovaný soubor HTML do určeného adresáře.

### Příklad zdrojového kódu pro export textového vstupního pole formuláře jako text pomocí Aspose.Words pro .NET


```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// Zadaná složka musí existovat a měla by být prázdná.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Nastavte možnost exportovat pole formuláře jako prostý text, nikoli jako vstupní prvky HTML.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Ujistěte se, že jste zadali správnou cestu k adresáři dokumentů v`dataDir` variabilní.