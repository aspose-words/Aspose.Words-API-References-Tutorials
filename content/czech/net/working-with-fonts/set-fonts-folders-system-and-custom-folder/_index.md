---
title: Nastavit systém složek písem a vlastní složku
linktitle: Nastavit systém složek písem a vlastní složku
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce nastavením systémových a vlastních složek písem při vykreslování dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

tomto tutoriálu vás provedeme krok za krokem procesem nastavení systémových složek písem a vlastní složky při vykreslování dokumentu pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak určit více složek písem, včetně systémové složky a vlastní složky, které se mají použít při vykreslování dokumentů pomocí Aspose.Words for .NET.

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Toto je umístění, kam chcete uložit upravený vykreslený dokument. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Načtěte dokument k vykreslení
 Poté můžete načíst dokument k vykreslení pomocí`Document` třída. Ujistěte se, že jste zadali správnou cestu dokumentu.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Nastavte systémové a vlastní složky písem
 Nyní můžete nastavit systémové složky písem a vlastní složku pomocí`FontSettings` třída a`SetFontsSources()` metoda. Nejprve musíte získat seznam zdrojů písem závislých na prostředí, které používáte`GetFontsSources()` a uložit jej do seznamu. Poté můžete vytvořit novou instanci`FolderFontSource` zadáním cesty k vlastní složce obsahující vaše písma. Přidejte tuto instanci do seznamu existujících zdrojů písem. Nakonec použijte`SetFontsSources()` pro aktualizaci zdrojů písem novým seznamem.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Krok 4: Použijte nastavení písma
 Dále musíte použít nastavení písma na váš dokument pomocí`FontSettings` vlastnictvím`Document` třída.

```csharp
doc.FontSettings = fontSettings;
```

## Krok 5: Uložte vykreslený dokument
Nakonec můžete vykreslený dokument uložit do souboru pomocí

   za použití`Save()` metoda`Document` třída. Ujistěte se, že jste zadali správnou cestu a název souboru.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Ukázkový zdrojový kód pro systém nastavení složek písem a vlastní složku pomocí Aspose.Words pro .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Načte pole zdrojů písem závislých na prostředí, které jsou standardně prohledávány.
// Například to bude obsahovat zdroj "Windows\Fonts\" na počítačích se systémem Windows.
// Toto pole přidáváme do nového seznamu, aby bylo přidávání nebo odstraňování položek písem mnohem jednodušší.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Přidejte nový zdroj složky, který dá Aspose.Words pokyn k hledání písem v následující složce.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
// Přidejte vlastní složku, která obsahuje naše písma, do seznamu existujících zdrojů písem.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak nastavit systémové složky písem a vlastní složku při vykreslování dokumentu pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno určit více složek písem, včetně systémové složky a vlastní složky, které se mají použít při vykreslování dokumentů. Aspose.Words nabízí výkonné a flexibilní API pro zpracování textu s písmy ve vašich dokumentech. S těmito znalostmi můžete ovládat a přizpůsobovat zdroje písem používané při vykreslování dokumentů podle vašich specifických potřeb.

### FAQ

#### Otázka: Jak mohu nastavit systémové složky písem v Aspose.Words?

A: Pro nastavení systémových složek písem v Aspose.Words nemusíte nic dělat. Aspose.Words automaticky používá systémová písma nainstalovaná ve vašem operačním systému.

#### Otázka: Jak mohu nastavit vlastní složky písem v Aspose.Words?

 A: Chcete-li nastavit vlastní složky písem v Aspose.Words, můžete použít`SetFontsFolders` metoda`Fonts` třída určující umístění vlastních složek písem.

#### Otázka: Mohu zadat více vlastních složek písem v Aspose.Words?

 Odpověď: Ano, můžete zadat více vlastních složek písem v Aspose.Words pomocí`SetFontsFolders` metoda`Fonts` třída se seznamem umístění složek.

#### Otázka: Jak mohu zkontrolovat složky písem definované v Aspose.Words?

 Chcete-li zkontrolovat složky písem definované v Aspose.Words, můžete použít`GetFolders` metoda`Fonts` třídy, abyste získali seznam nakonfigurovaných složek písem.

#### Otázka: Mají písma vlastní složky přednost před systémovými písmy v Aspose.Words?

Odpověď: Ano, písma vlastní složky mají v Aspose.Words přednost před systémovými písmy. Pokud je písmo přítomno ve vlastních složkách i v systémových písmech, Aspose.Words použije verzi z vlastní složky.