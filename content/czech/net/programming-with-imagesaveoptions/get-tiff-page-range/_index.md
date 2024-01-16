---
title: Získejte rozsah stránek Tiff
linktitle: Získejte rozsah stránek Tiff
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak extrahovat řadu stránek TIFF pomocí Aspose.Words pro .NET. Kompletní návod pro vlastní soubory TIFF.
type: docs
weight: 10
url: /cs/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

V tomto tutoriálu prozkoumáme poskytnutý zdrojový kód C#, abychom získali řadu stránek TIFF s Aspose.Words pro .NET. Tato funkce umožňuje extrahovat určitý rozsah stránek z dokumentu a uložit je jako soubor TIFF.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že jste nastavili své vývojové prostředí s Aspose.Words for .NET. Ujistěte se, že jste přidali potřebné reference a importovali příslušné jmenné prostory.

## Krok 2: Načtení dokumentu

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 V tomto kroku načteme dokument pomocí`Document` a předání cesty k souboru DOCX k načtení.

## Krok 3: Uložení celého dokumentu ve formátu TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

 tomto kroku uložíme celý dokument ve formátu TIFF pomocí`Save` a zadáním cesty k výstupnímu souboru s příponou`.tiff`.

## Krok 4: Nakonfigurujte možnosti zálohování pro rozsah stránek

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 V tomto kroku nakonfigurujeme možnosti zálohování pro konkrétní rozsah stránek. Vytváříme nový`ImageSaveOptions` objekt určující požadovaný formát uložení, zde "Tiff" pro formát TIFF. Používáme`PageSet` k určení rozsahu stránek, které chceme extrahovat, zde od stránky 0 do stránky 1 (včetně). Nastavili jsme také kompresi TIFF na`Ccitt4` a rozlišení až 160 dpi.

## Krok 5: Uložení rozsahu stránek do formátu TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 V tomto posledním kroku uložíme zadaný rozsah stránek ve formátu TIFF pomocí`Save` a předání cesty k výstupnímu souboru pomocí`.tiff` rozšíření spolu se zadanými možnostmi uložení .

Nyní můžete spustit zdrojový kód a získat konkrétní rozsah stránek z dokumentu a uložit je jako soubor TIFF. Výsledné soubory budou uloženy do určeného adresáře s názvy "WorkingWithImageSaveOptions.MultipageTiff.tiff" pro celý dokument a "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" pro zadaný rozsah stránek.

### Ukázkový zdrojový kód Get Tiff Page Range pomocí Aspose.Words pro .NET

```csharp 

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Závěr

V tomto tutoriálu jsme prozkoumali funkčnost získání řady stránek TIFF pomocí Aspose.Words pro .NET. Naučili jsme se, jak extrahovat konkrétní rozsah stránek z dokumentu a uložit je jako soubor TIFF.

Tato funkce je užitečná, když chcete z dokumentu extrahovat pouze určité stránky a uložit je ve standardním formátu obrázku, jako je TIFF. Můžete také upravit možnosti komprese a rozlišení, abyste získali soubory TIFF v nejlepší kvalitě.

Aspose.Words for .NET nabízí širokou škálu pokročilých funkcí pro manipulaci a generování dokumentů. Získání rozsahu stránek TIFF je jedním z mnoha výkonných nástrojů, které máte k dispozici.

Neváhejte a integrujte tuto funkci do svých projektů Aspose.Words for .NET, abyste extrahovali a ukládali konkrétní rozsahy stránek z vašich dokumentů ve formátu TIFF.