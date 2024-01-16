---
title: Formát 1Bpp Indexováno
linktitle: Formát 1Bpp Indexováno
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se formátovat obrázky v 1 bpp indexované pomocí Aspose.Words pro .NET. Kompletní návod pro obrázky s nízkou barevnou hloubkou.
type: docs
weight: 10
url: /cs/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
V tomto tutoriálu prozkoumáme zdrojový kód C# poskytovaný pro funkci "Formát 1Bpp Indexed" s Aspose.Words pro .NET. Tato funkce umožňuje formátovat obrázky v dokumentu ve formátu PNG s barevnou hloubkou 1 bit na pixel (1 bpp) a indexovaným barevným režimem.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že jste nastavili své vývojové prostředí s Aspose.Words for .NET. Ujistěte se, že jste přidali potřebné reference a importovali příslušné jmenné prostory.

## Krok 2: Načtení dokumentu

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 V tomto kroku načteme dokument pomocí`Document` a předání cesty k souboru DOCX k načtení.

## Krok 3: Nakonfigurujte možnosti zálohování obrazu

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 V tomto kroku nakonfigurujeme možnosti zálohování pro obrazy. Vytváříme nový`ImageSaveOptions`objekt určující požadovaný formát uložení, zde "Png" pro formát PNG. Definujeme také stránku, která se má zahrnout do obrázku, černobílý barevný režim a indexovaný pixelový formát 1 bpp.

## Krok 4: Zálohování obrázků

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 V tomto posledním kroku uložíme obrázky dokumentu ve formátu PNG pomocí`Save` a předání cesty k výstupnímu souboru spolu se zadanými možnostmi uložení.

Nyní můžete spustit zdrojový kód pro formátování obrázků dokumentů ve formátu PNG s indexovanou barevnou hloubkou 1 bpp. Výsledný soubor bude uložen do zadaného adresáře s názvem "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### Ukázkový zdrojový kód pro formát 1Bpp indexovaný pomocí Aspose.Words pro .NET

```csharp 
 
			 // Cesta k vašemu adresáři dokumentů
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Závěr

V tomto tutoriálu jsme prozkoumali funkci indexovaného formátu 1Bpp s Aspose.Words pro .NET. Naučili jsme se formátovat obrázky v dokumentu ve formátu PNG s barevnou hloubkou 1 bit na pixel (1 bpp) a indexovaným barevným režimem.

Tato funkce je užitečná, když chcete získat obrázky s nízkou barevnou hloubkou a malou velikostí souboru. Formát 1Bpp Indexed umožňuje zobrazení obrázků pomocí indexované palety barev, což může být výhodné pro některé specifické aplikace.

Aspose.Words for .NET nabízí širokou škálu pokročilých funkcí pro manipulaci a generování dokumentů. Indexovaný formát 1Bpp je jedním z mnoha výkonných nástrojů, které máte k dispozici.