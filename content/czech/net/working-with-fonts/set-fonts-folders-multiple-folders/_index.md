---
title: Nastavit složky písem více složek
linktitle: Nastavit složky písem více složek
second_title: Aspose.Words API pro zpracování dokumentů
description: Krok za krokem průvodce nastavením více složek písem při vykreslování dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

V tomto tutoriálu vás provedeme krok za krokem procesem nastavení více složek písem při vykreslování dokumentu pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak určit více složek písem, které se mají použít při vykreslování dokumentů pomocí Aspose.Words for .NET.

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

## Krok 3: Nastavte složky písem
 Nyní můžete nastavit více složek písem pomocí`FontSettings` třída a`SetFontsFolders()` metoda. Můžete zadat cesty ke složkám písem, které chcete použít v poli. V tomto příkladu jsme zadali dvě složky písem: "C:\MyFonts\" a "D:\Misc\Fonts\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Krok 4: Použijte nastavení písma
 Dále musíte použít nastavení písma na váš dokument pomocí`FontSettings` majetek z`Document` třída.

```csharp
doc.FontSettings = fontSettings;
```

## Krok 5: Uložte vykreslený dokument
 Nakonec můžete vykreslený dokument uložit do souboru pomocí`Save()` metoda`Document` třída. Ujistěte se, že jste zadali správnou cestu a název souboru.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Ukázkový zdrojový kód pro Set Fonts Folders Multiple Folders pomocí Aspose.Words for .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Upozorňujeme, že toto nastavení přepíše všechny výchozí zdroje písem, které jsou ve výchozím nastavení prohledávány. Nyní se budou hledat pouze tyto složky
// písma při vykreslování nebo vkládání písem. Chcete-li přidat další zdroj písem při zachování systémových zdrojů písem, použijte FontSettings.GetFontSources a
// Místo toho FontSettings.SetFontSources.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Závěr
tomto tutoriálu jsme se naučili, jak nastavit více složek písem při vykreslování dokumentu pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno určit více složek písem, které se mají použít při vykreslování dokumentů. Aspose.Words nabízí výkonné a flexibilní API pro zpracování textu s písmy ve vašich dokumentech. S těmito znalostmi můžete ovládat a přizpůsobovat zdroje písem používané při vykreslování dokumentů podle vašich specifických potřeb.

### FAQ

#### Otázka: Jak mohu v Aspose.Words nastavit více složek písem?

 A: Chcete-li nastavit více složek písem v Aspose.Words, můžete použít`SetFontsFolders` metoda`Fonts` třídy poskytující seznam umístění složek vlastních písem.

#### Otázka: Má nastavení více složek písem vliv na všechny dokumenty zpracovávané pomocí Aspose.Words?

Odpověď: Ano, nastavení více složek písem ovlivní všechny dokumenty zpracované pomocí Aspose.Words. Jakmile definujete složky písem, Aspose.Words použije tato umístění k vyhledání písem ve všech dokumentech.

#### Otázka: Kolik složek písem mohu definovat v Aspose.Words?

Odpověď: V Aspose.Words můžete definovat tolik složek písem, kolik potřebujete. Neexistuje žádný konkrétní limit na počet složek písem, které můžete definovat.

#### Otázka: Jak mohu zkontrolovat složky písem definované v Aspose.Words?

 A: Chcete-li zkontrolovat složky písem definované v Aspose.Words, můžete použít`GetFolders` metoda`Fonts` třídy, abyste získali umístění nakonfigurovaných složek písem.

#### Otázka: Musí složky písem obsahovat konkrétní písma?

Odpověď: Ano, složky písem by měly obsahovat písma, která chcete použít ve svých dokumentech aplikace Word. Aspose.Words bude při zpracování dokumentů hledat písma v zadaných složkách.