---
title: Nastavte složku True Type písem
linktitle: Nastavte složku True Type písem
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce nastavením složky true type fonts při vykreslování dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/set-true-type-fonts-folder/
---

V tomto tutoriálu vás provedeme krok za krokem procesem nastavení složky true type fonts při vykreslování dokumentu pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak určit vlastní složku obsahující písma True Type, která se použije při vykreslování dokumentů pomocí Aspose.Words for .NET.

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Toto je umístění, kam chcete uložit upravený vykreslený dokument. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Načtěte dokument k vykreslení
 Dále musíte načíst dokument k vykreslení pomocí`Document` třída. Ujistěte se, že jste zadali správnou cestu dokumentu.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Nastavte složku True Type písem
Nyní můžete určit složku true type fontů, která se má použít při vykreslování, vytvořením instance`FontSettings` třídy a pomocí`SetFontsFolder()` způsob nastavení složky písem. Můžete určit vlastní složku obsahující vaše písma True Type. Druhý parametr do`SetFontsFolder()` označuje, zda chcete prohledávat také podsložky zadané složky.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Krok 4: Uložte vykreslený dokument
 Nakonec můžete vykreslený dokument uložit do souboru pomocí`Save()` metoda`Document` třída. Ujistěte se, že jste zadali správnou cestu a název souboru.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Ukázkový zdrojový kód pro Set True Type Fonts Folder pomocí Aspose.Words for .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Upozorňujeme, že toto nastavení přepíše všechny výchozí zdroje písem, které jsou ve výchozím nastavení prohledávány. Nyní se budou hledat pouze tyto složky
// Písma při vykreslování nebo vkládání písem. Chcete-li přidat další zdroj písem při zachování systémových zdrojů písem, použijte FontSettings.GetFontSources a
// Místo toho FontSettings.SetFontSources
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// Nastavte nastavení písma
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Závěr
tomto tutoriálu jsme se naučili, jak nastavit složku true type fonts při vykreslování dokumentu pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno určit vlastní složku obsahující písma True Type, která se použije při vykreslování dokumentů. Aspose.Words nabízí výkonné a flexibilní API pro zpracování textu s písmy ve vašich dokumentech. S těmito znalostmi můžete ovládat a upravovat písma používaná při vykreslování dokumentů podle vašich specifických potřeb.

### FAQ

#### Otázka: Jak mohu nakonfigurovat složku písem TrueType v Aspose.Words?

 A: Chcete-li nakonfigurovat složku písem TrueType v Aspose.Words, můžete použít`SetTrueTypeFontsFolder` metoda`Fonts` třída určující umístění složky obsahující písma TrueType.

#### Otázka: Jaké typy písem jsou považovány za písma TrueType?

Odpověď: Písma TrueType jsou oblíbeným formátem písem. Často se používají v dokumentech aplikace Word a mají příponu souboru .ttf nebo .ttc.

#### Otázka: Mohu zadat více složek písem TrueType v Aspose.Words?

Odpověď: Ano, můžete zadat více složek písem TrueType v Aspose.Words pomocí`SetTrueTypeFontsFolder` metoda`Fonts` třída se seznamem umístění složek.

#### Otázka: Jak mohu zkontrolovat složku písem TrueType nakonfigurovanou v Aspose.Words?

 A: Chcete-li zkontrolovat nakonfigurovanou složku TrueType Fonts v Aspose.Words, můžete použít`GetTrueTypeFontsFolder` metoda`Fonts` třídy, abyste získali umístění nakonfigurované složky písem TrueType.

#### Otázka: Proč je důležité nakonfigurovat složku písem TrueType v Aspose.Words?

Odpověď: Nastavení složky písem TrueType v Aspose.Words je důležité, protože pomáhá Aspose.Words najít písma potřebná při zpracování dokumentů aplikace Word. To zajišťuje konzistenci formátování a vzhledu dokumentu, a to i napříč různými systémy.