---
title: Aktualizovat vlastnost posledního uloženého času
linktitle: Aktualizovat vlastnost posledního uloženého času
second_title: Aspose.Words API pro zpracování dokumentů
description: Přečtěte si, jak automaticky aktualizovat vlastnost Last Saved Time při ukládání dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
V tomto tutoriálu prozkoumáme poskytnutý zdrojový kód C#, abychom aktualizovali vlastnost posledního času uložení při ukládání dokumentu pomocí Aspose.Words for .NET. Tato funkce umožňuje automaticky aktualizovat vlastnost času posledního uložení generovaného dokumentu.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že jste nastavili své vývojové prostředí s Aspose.Words for .NET. Ujistěte se, že jste přidali potřebné reference a importovali příslušné jmenné prostory.

## Krok 2: Načtení dokumentu

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 V tomto kroku načteme dokument pomocí`Document` a předání cesty k souboru DOCX k načtení.

## Krok 3: Konfigurace možností zálohování OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 V tomto kroku nakonfigurujeme možnosti uložení OOXML pomocí`OoxmlSaveOptions` třída. Nastavením povolíme automatickou aktualizaci vlastnosti posledního času uložení`UpdateLastSavedTimeProperty` na`true`.

## Krok 4: Uložte dokument s aktualizovanou vlastností

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 V tomto posledním kroku dokument uložíme pomocí`Save` a předání cesty k výstupnímu souboru pomocí`.docx` rozšíření spolu se zadanými možnostmi uložení.

Nyní můžete spustit zdrojový kód a automaticky aktualizovat vlastnost posledního času uložení při ukládání dokumentu. Výsledný soubor bude uložen do zadaného adresáře s názvem "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### Ukázkový zdrojový kód pro vlastnost Update Last Saved Time pomocí Aspose.Words for .NET 

```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Závěr

V tomto tutoriálu jsme prozkoumali funkci automatické aktualizace vlastnosti posledního času uložení při ukládání dokumentu pomocí Aspose.Words for .NET. Povolením této funkce s možnostmi uložení OOXML můžete zajistit, že se vlastnost času posledního uložení ve vygenerovaném dokumentu automaticky aktualizuje.

Aktualizace vlastnosti posledního uložení může být užitečná pro sledování změn a verzí dokumentu. Zaznamenává také, kdy byl dokument naposledy uložen, což může být užitečné v různých scénářích.

Aspose.Words for .NET usnadňuje automatickou aktualizaci vlastnosti Last Backup Time tím, že poskytuje flexibilní a výkonné možnosti zálohování. Tuto funkci můžete integrovat do svých projektů, abyste zajistili, že vygenerované dokumenty budou mít přesné záložní informace.