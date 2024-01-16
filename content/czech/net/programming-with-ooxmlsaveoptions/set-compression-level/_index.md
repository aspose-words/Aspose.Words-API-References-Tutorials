---
title: Nastavte úroveň komprese
linktitle: Nastavte úroveň komprese
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit úroveň komprese při ukládání dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
V tomto tutoriálu prozkoumáme poskytnutý zdrojový kód C# pro nastavení úrovně komprese při ukládání dokumentu pomocí Aspose.Words for .NET. Tato funkce umožňuje ovládat úroveň komprese generovaného dokumentu.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 V tomto kroku nakonfigurujeme možnosti uložení OOXML pomocí`OoxmlSaveOptions` třída. Nastavíme úroveň komprese na`SuperFast` pro rychlejší kompresi.

## Krok 4: Uložte dokument se zadanou úrovní komprese

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 V tomto posledním kroku dokument uložíme pomocí`Save` a předání cesty k výstupnímu souboru pomocí`.docx` rozšíření spolu se zadanými možnostmi uložení.

Nyní můžete spustit zdrojový kód a nastavit úroveň komprese při ukládání dokumentu. Výsledný soubor bude uložen do zadaného adresáře s názvem "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### Ukázkový zdrojový kód pro nastavení úrovně komprese pomocí Aspose.Words pro .NET 

```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Závěr

V tomto tutoriálu jsme prozkoumali funkčnost nastavení úrovně komprese při ukládání dokumentu pomocí Aspose.Words for .NET. Zadáním vhodné úrovně komprese můžete optimalizovat velikost dokumentu a rychlost generování.

 The`OoxmlSaveOptions` třída poskytuje flexibilitu pro ovládání úrovně komprese nastavením`CompressionLevel` majetek na odpovídající hodnotu, jako je např`SuperFast`. To vám umožní dosáhnout správné rovnováhy mezi velikostí souboru a rychlostí zálohování na základě vašich konkrétních potřeb.

Použití komprese může být výhodné, když potřebujete zmenšit velikost generovaných souborů, zejména u velkých dokumentů. To může usnadnit ukládání, sdílení a přenos dokumentů.

Aspose.Words for .NET nabízí řadu výkonných možností a funkcí pro manipulaci s dokumenty. Pomocí vhodných možností zálohování můžete přizpůsobit proces generování dokumentů a optimalizovat výkon vaší aplikace.

Neváhejte a prozkoumejte další funkce Aspose.Words for .NET, abyste zlepšili svůj pracovní postup generování dokumentů.
