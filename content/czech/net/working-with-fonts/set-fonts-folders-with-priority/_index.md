---
title: Nastavte složky písem s prioritou
linktitle: Nastavte složky písem s prioritou
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce nastavením složek písem s prioritou při vykreslování dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/set-fonts-folders-with-priority/
---

V tomto tutoriálu vás provedeme krok za krokem procesem nastavení prioritních složek písem při vykreslování dokumentu pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak určit více složek písem s vlastní prioritou vyhledávání při vykreslování dokumentů pomocí Aspose.Words for .NET.

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Toto je umístění, kam chcete uložit upravený vykreslený dokument. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Nastavte složky písem s prioritou
 Potom můžete nastavit prioritu složek písem pomocí`FontSettings` třída a`SetFontsSources()`metoda. Pomocí instancí můžete určit více zdrojů písem`SystemFontSource`a`FolderFontSource`. V tomto příkladu jsme definovali dva zdroje písem: výchozí systémový zdroj písem a vlastní složku písem s prioritou 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Krok 3: Načtěte dokument k vykreslení
 Nyní můžete načíst dokument k vykreslení pomocí`Document` třída. Ujistěte se, že jste zadali správnou cestu dokumentu.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 4: Uložte vykreslený dokument
 Nakonec můžete vykreslený dokument uložit do souboru pomocí`Save()` metoda`Document` třída. Ujistěte se, že jste zadali správnou cestu a název souboru.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Ukázkový zdrojový kód pro Nastavit složky písem s prioritou pomocí Aspose.Words pro .NET 
```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak nastavit složky písem s prioritou při vykreslování dokumentu pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno určit více složek písem s vlastní prioritou vyhledávání při vykreslování dokumentů. Aspose.Words nabízí výkonné a flexibilní API pro zpracování textu s písmy ve vašich dokumentech. S těmito znalostmi můžete ovládat a přizpůsobovat zdroje písem používané při vykreslování dokumentů podle vašich specifických potřeb.

### FAQ

#### Otázka: Jak mohu nastavit prioritu složek písem v Aspose.Words?

 A: Chcete-li nastavit prioritu složek písem v Aspose.Words, můžete použít`SetFontsFoldersWithPriority` metoda`Fonts` třídy zadáním umístění složek písem a jejich pořadí priority.

#### Otázka: Co se stane, když je písmo přítomno v několika složkách s různou prioritou?

Odpověď: Pokud je písmo přítomno ve více složkách s různou prioritou, Aspose.Words použije při zpracování dokumentů verzi ze složky s nejvyšší prioritou.

#### Otázka: Mohu v Aspose.Words zadat více složek písem se stejnou prioritou?

Odpověď: Ano, v Aspose.Words můžete zadat více složek písem se stejnou prioritou. Aspose.Words je všechny zváží se stejnou prioritou při hledání písem ve vašich dokumentech.

#### Otázka: Jak mohu zkontrolovat složky písem definované s prioritou v Aspose.Words?

 A: Chcete-li zkontrolovat složky písem definované s prioritou v Aspose.Words, můžete použít`GetFolders` metoda`Fonts` třídy, abyste získali seznam nakonfigurovaných složek písem včetně pořadí jejich priorit.

#### Otázka: K čemu slouží nastavení složek písem s prioritou v Aspose.Words?

Odpověď: Nastavení složek písem s prioritou v Aspose.Words vám umožňuje řídit pořadí vyhledávání písem v dokumentech aplikace Word. To vám pomůže zajistit, že se používají požadovaná písma, a vyhnout se nežádoucím problémům s nahrazováním písem.