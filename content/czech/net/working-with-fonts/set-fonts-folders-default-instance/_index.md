---
title: Nastavit výchozí instanci složek písem
linktitle: Nastavit výchozí instanci složek písem
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce nastavením výchozí složky písem při vykreslování dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/set-fonts-folders-default-instance/
---

V tomto tutoriálu vás provedeme krok za krokem procesem nastavení výchozí složky písem při vykreslování dokumentu pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak nastavit výchozí složku písem, která se použije při vykreslování dokumentů pomocí Aspose.Words for .NET.

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Toto je umístění, kam chcete uložit upravený vykreslený dokument. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Nastavte výchozí složku písem
 Poté můžete nastavit výchozí složku písem pomocí`FontSettings.DefaultInstance` třída a`SetFontsFolder()`metoda. Zadejte cestu ke složce písem, kterou chcete použít jako výchozí složku.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Krok 3: Načtěte dokument k vykreslení
 Nyní můžete načíst dokument k vykreslení pomocí`Document` třída. Ujistěte se, že jste zadali správnou cestu dokumentu.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 4: Uložte vykreslený dokument
 Nakonec můžete vykreslený dokument uložit do souboru pomocí`Save()` metoda`Document` třída. Ujistěte se, že jste zadali správnou cestu a název souboru.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Ukázkový zdrojový kód pro výchozí instanci Set Fonts Folders pomocí Aspose.Words for .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak nastavit výchozí složku písem při vykreslování dokumentu pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno určit, kterou složku písem použít jako výchozí složku při vykreslování dokumentů. Aspose.Words nabízí výkonné a flexibilní API pro zpracování textu s písmy ve vašich dokumentech. S těmito znalostmi můžete ovládat a přizpůsobovat zdroje písem používané při vykreslování dokumentů podle vašich specifických potřeb.

### FAQ

#### Otázka: Jak mohu nastavit výchozí složky písem v Aspose.Words?

 A: Chcete-li nastavit výchozí složky písem v Aspose.Words, musíte použít`Fonts` třída a`SetFontsFolders` metoda k určení umístění vlastních složek písem.

#### Otázka: Má nastavení výchozích složek písem vliv na všechny dokumenty aplikace Word zpracované pomocí Aspose.Words?

Odpověď: Ano, nastavení výchozích složek písem ovlivní všechny dokumenty aplikace Word zpracované pomocí Aspose.Words. Jakmile nastavíte výchozí složky písem, Aspose.Words použije tato umístění k vyhledání písem ve všech dokumentech.

#### Otázka: Mohu v Aspose.Words nastavit více výchozích složek písem?

 Odpověď: Ano, v Aspose.Words můžete nastavit více výchozích složek písem. Stačí zadat umístění vlastních složek písem pomocí`SetFontsFolders` metoda`Fonts` třída.

#### Otázka: Jak mohu zkontrolovat výchozí složky písem aktuálně nastavené v Aspose.Words?

 A: Chcete-li zkontrolovat výchozí složky písem aktuálně definované v Aspose.Words, můžete použít`GetFolders` metoda`Fonts` třídy, abyste získali umístění nakonfigurovaných složek písem.

#### Otázka: Umožňuje mi nastavení výchozích složek písem používat vlastní písma v dokumentech aplikace Word?

Odpověď: Ano, nastavením výchozích složek písem můžete v dokumentech aplikace Word používat vlastní písma. Stačí umístit písma do určených složek a Aspose.Words je použije při generování nebo manipulaci s dokumenty.