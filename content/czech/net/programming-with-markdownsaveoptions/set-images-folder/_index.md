---
title: Nastavte složku obrázků
linktitle: Nastavte složku obrázků
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit složku obrázků při exportu do Markdown pomocí Aspose.Words for .NET. Upravte umístění obrázků pro lepší organizaci a integraci.
type: docs
weight: 10
url: /cs/net/programming-with-markdownsaveoptions/set-images-folder/
---

Zde je průvodce krok za krokem, který vysvětluje následující zdrojový kód C#, který pomáhá nastavit složku obrázků pro možnosti exportu Markdown pomocí knihovny Aspose.Words pro .NET. Před použitím tohoto kódu se ujistěte, že jste do projektu zahrnuli knihovnu Aspose.Words.

## Krok 1: Nastavte cestu k adresáři dokumentu

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Ujistěte se, že jste zadali správnou cestu k adresáři dokumentů, kde je umístěn dokument obsahující obrázky.

## Krok 2: Vložte dokument obsahující obrázky

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Zadaný dokument, který obsahuje obrázky, které chceme exportovat, načteme pomocí možností Markdown.

## Krok 3: Nastavte složku obrázků pro možnosti exportu Markdown

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Vytvoříme instanci`MarkdownSaveOptions` a nastavte cestu ke složce obrázků pomocí`ImagesFolder` vlastnictví. Ujistěte se, že jste zadali správnou cestu ke složce, kam chcete uložit exportované obrázky.

## Krok 4: Uložte dokument pomocí možností exportu Markdown

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Dokument uložíme do paměťového toku pomocí zadaných možností exportu Markdown. Tok pak můžete použít k provádění dalších operací, jako je ukládání obsahu Markdown do souboru.

### Příklad zdrojového kódu pro nastavení složky obrázků pro MarkdownSaveOptions s Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Tento zdrojový kód ukazuje, jak načíst dokument, který obsahuje obrázky, a poté nastavit složku obrázků pro možnosti exportu Markdown. Pomocí zadaných možností se pak dokument uloží do paměti. To vám umožní přizpůsobit umístění složky obrázků při exportu obsahu Markdown.