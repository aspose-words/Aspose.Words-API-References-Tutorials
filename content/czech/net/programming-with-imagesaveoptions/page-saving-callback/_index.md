---
title: Zpětné volání pro ukládání stránky
linktitle: Zpětné volání pro ukládání stránky
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak přizpůsobit ukládání stránek dokumentu do obrázků pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-imagesaveoptions/page-saving-callback/
---

V tomto tutoriálu prozkoumáme zdrojový kód C#, který je k dispozici pro použití zpětného volání uložení stránky s možnostmi uložení obrázku Aspose.Words pro .NET. Tato funkce umožňuje provádět vlastní akce při ukládání každé stránky dokumentu jako obrázku.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 V tomto kroku nakonfigurujeme možnosti uložení obrázku vytvořením nového`ImageSaveOptions` objekt. Zadáme požadovaný formát zálohy, zde "Png" pro formát PNG. Používáme`PageSet` k určení rozsahu stránek, které se mají uložit, zde od první stránky po poslední stránku dokumentu (`doc.PageCount - 1`). Také jsme nastavili`PageSavingCallback` k instanci`HandlePageSavingCallback`, což je vlastní třída pro zpracování zpětného volání ukládání stránky.

## Krok 4: Implementace zpětného volání pro uložení stránky

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Zde implementujte své vlastní akce
         // K informacím o stránce můžete přistupovat prostřednictvím vlastnosti „args.PageIndex“.
         // Můžete také změnit možnosti uložení pro každou stránku jednotlivě.
     }
}
```

 V tomto kroku implementujeme`HandlePageSavingCallback` třída, která implementuje`IPageSavingCallback` rozhraní. Tuto třídu si můžete přizpůsobit přidáním svých konkrétních akcí do`PageSaving` metoda. K informacím o stránce můžete přistupovat prostřednictvím`args.PageIndex` vlastnictvím`PageSavingArgs` objekt předán jako argument.

## Krok 5: Uložení stránek jako obrázků

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 V tomto posledním kroku uložíme každou stránku dokumentu jako obrázek pomocí`Save` a předání cesty k výstupnímu souboru pomocí`.png` rozšíření spolu se zadanými možnostmi uložení.

Nyní můžete spustit zdrojový kód a provést vlastní akce při ukládání každé stránky dokumentu jako obrázku. Výsledný soubor bude uložen do zadaného adresáře s názvem "WorkingWithImageSaveOptions.PageSavingCallback.png".

### Ukázkový zdrojový kód pro Page Saving Callback pomocí Aspose.Words pro .NET


```csharp 
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Závěr

V tomto tutoriálu jsme prozkoumali funkci zpětného volání uložení stránky s možnostmi uložení obrázku Aspose.Words pro .NET. Naučili jsme se, jak provádět vlastní akce při ukládání každé stránky dokumentu jako obrázku.

Tato funkce je užitečná, když chcete při převodu na obrázky provádět specifické operace na každé stránce. Můžete přistupovat k informacím o stránce a používat je k přizpůsobení možností zálohování nebo k provádění jiného zpracování specifického pro stránku.

Aspose.Words for .NET nabízí širokou škálu pokročilých funkcí pro manipulaci a generování dokumentů. Save Page Reminder je jedním z mnoha výkonných nástrojů, které vám poskytuje k přizpůsobení procesu ukládání stránek do obrázků.