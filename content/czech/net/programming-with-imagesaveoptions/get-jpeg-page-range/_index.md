---
title: Získejte rozsah stránek Jpeg
linktitle: Získejte rozsah stránek Jpeg
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak získat řadu stránek JPEG pomocí Aspose.Words pro .NET. Kompletní návod pro extrahování vlastních obrázků.
type: docs
weight: 10
url: /cs/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

V tomto tutoriálu prozkoumáme zdrojový kód C# poskytovaný pro funkci "Získat rozsah stránek JPEG" pomocí Aspose.Words pro .NET. Tato funkce umožňuje převést určitý rozsah stránek dokumentu na obrázky ve formátu JPEG.

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
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 V tomto kroku nakonfigurujeme možnosti zálohování pro obrazy. Vytváříme nový`ImageSaveOptions` objekt určující požadovaný formát uložení, zde "Jpeg" pro formát JPEG. Také jsme nastavili rozsah stránek pro převod pomocí`PageSet`objekt. Nakonec upravíme jas a kontrast obrázku pomocí`ImageBrightness` a`ImageContrast` vlastnosti, resp. Horizontální rozlišení také měníme pomocí`HorizontalResolution` vlastnictví.

## Krok 4: Zálohování obrázků

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 V tomto posledním kroku uložíme obrázky zadaného rozsahu stránek ve formátu JPEG pomocí`Save` a předání cesty k výstupnímu souboru spolu se zadanými možnostmi uložení.

Nyní můžete spustit zdrojový kód a převést určitý rozsah stránek v dokumentu na obrázky JPEG. Výsledný soubor bude uložen do zadaného adresáře s názvem "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg".

### Ukázkový zdrojový kód pro Get Jpeg Page Range pomocí Aspose.Words For .NET

```csharp 
 // Cesta k vašemu adresáři dokumentů
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Chcete-li převést pouze první stránku dokumentu, nastavte "PageSet" na "0".
options.PageSet = new PageSet(0);

// Změňte jas a kontrast obrázku.
// Oba jsou na stupnici 0-1 a ve výchozím nastavení jsou na 0,5.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Změňte horizontální rozlišení.
// Výchozí hodnota pro tyto vlastnosti je 96,0 pro rozlišení 96 dpi.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Závěr

V tomto tutoriálu jsme prozkoumali funkčnost získání rozsahu stránek JPEG pomocí Aspose.Words pro .NET. Naučili jsme se, jak převést konkrétní rozsah stránek dokumentu na obrázky ve formátu JPEG a zároveň upravit možnosti uložení.

Tato funkce je užitečná, když chcete z dokumentu extrahovat konkrétní stránky a uložit je jako obrázky JPEG. Můžete také upravit jas, kontrast a horizontální rozlišení obrázků, abyste dosáhli personalizovaných výsledků.

Aspose.Words for .NET nabízí širokou škálu pokročilých funkcí pro manipulaci a generování dokumentů. Získání rozsahu stránek JPEG je jedním z mnoha výkonných nástrojů, které máte k dispozici.

Neváhejte a integrujte tuto funkci do svých projektů Aspose.Words for .NET, abyste ze svých dokumentů získali vysoce kvalitní obrázky JPEG.