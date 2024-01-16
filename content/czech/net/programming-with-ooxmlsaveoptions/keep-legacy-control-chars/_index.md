---
title: Udržujte starší ovládací znaky
linktitle: Udržujte starší ovládací znaky
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak zachovat starší řídicí znaky při ukládání dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

V tomto tutoriálu prozkoumáme poskytnutý zdrojový kód C#, abychom zachovali starší řídicí znaky při ukládání dokumentu pomocí Aspose.Words for .NET. Tato funkce umožňuje zachovat speciální řídicí znaky při převodu nebo ukládání dokumentu.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že jste nastavili své vývojové prostředí s Aspose.Words for .NET. Ujistěte se, že jste přidali potřebné reference a importovali příslušné jmenné prostory.

## Krok 2: Načtení dokumentu

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 V tomto kroku načteme dokument pomocí`Document` a předání cesty k souboru obsahujícímu zděděné řídicí znaky.

## Krok 3: Konfigurace možností zálohování OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

 V tomto kroku nakonfigurujeme možnosti uložení OOXML vytvořením nového`OoxmlSaveOptions` objekt. Zadáme požadovaný formát uložení (zde,`FlatOpc` ) a povolte`KeepLegacyControlChars` možnost zachovat starší řídicí znaky.

## Krok 4: Uložení dokumentu se staršími řídicími znaky

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 V tomto posledním kroku dokument uložíme pomocí`Save` a předání cesty k výstupnímu souboru pomocí`.docx` rozšíření spolu se zadanými možnostmi uložení.

Nyní můžete spouštět zdrojový kód pro zachování starších řídicích znaků při ukládání dokumentu. Výsledný soubor bude uložen do zadaného adresáře s názvem "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Ukázkový zdrojový kód pro Keep Legacy Control Chars pomocí Aspose.Words pro .NET 
```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Závěr

V tomto tutoriálu jsme prozkoumali funkčnost zachování starších řídicích znaků při ukládání dokumentu pomocí Aspose.Words for .NET. Naučili jsme se, jak zachovat ty speciální znaky, které mohou být důležité pro správné formátování nebo zobrazení dokumentu.

 Zachování starších řídicích znaků je užitečné zejména při zpracování textu s dokumenty, které používají starší nebo specifické funkce, jako jsou speciální řídicí znaky. Povolením`KeepLegacyControlChars` Při ukládání dokumentu zajistíte zachování těchto znaků.

Aspose.Words for .NET nabízí řadu flexibilních a výkonných možností zálohování, které splní vaše potřeby manipulace s dokumenty. Pomocí vhodných možností můžete přizpůsobit proces zálohování tak, aby byly zachovány specifické vlastnosti vašich dokumentů.

Neváhejte začlenit tuto funkci do svých projektů Aspose.Words for .NET, abyste zajistili integritu a zachování starších řídicích znaků ve vašich dokumentech.