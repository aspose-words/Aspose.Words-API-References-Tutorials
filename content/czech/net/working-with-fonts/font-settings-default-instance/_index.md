---
title: Nastavení písma Výchozí instance
linktitle: Nastavení písma Výchozí instance
second_title: Aspose.Words API pro zpracování dokumentů
description: V tomto kurzu se dozvíte, jak nakonfigurovat výchozí nastavení písma v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/font-settings-default-instance/
---

V tomto tutoriálu vás provedeme tím, jak nakonfigurovat výchozí nastavení písma v dokumentu aplikace Word pomocí knihovny Aspose.Words pro .NET. Výchozí nastavení písma vám umožňuje určit zdroje písem použité při načítání a vykreslování dokumentů. Provedeme vás krok za krokem, abychom vám pomohli pochopit a implementovat kód ve vašem projektu .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words pro .NET nainstalovaná ve vašem projektu

## Krok 1: Definujte adresář dokumentů
 Nejprve musíte nastavit cestu k adresáři na umístění vašeho dokumentu aplikace Word. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s příslušnou cestou.

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Nakonfigurujte výchozí nastavení písma
 Dále vytvoříme instanci`FontSettings` použitím`FontSettings.DefaultInstance`a poté určíme zdroje písem použité při načítání a vykreslování dokumentů. V tomto příkladu používáme zdroj systémových písem a zdroj písem složky.

```csharp
// Nakonfigurujte výchozí nastavení písma
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Krok 3: Nahrajte dokument s nastavením písma
 Nyní načteme dokument pomocí`LoadOptions` a určení nastavení písma, které se má použít.

```csharp
// Vložte dokument s nastavením písma
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Ukázkový zdrojový kód pro výchozí instanci nastavení písma pomocí Aspose.Words pro .NET 
```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Závěr
V tomto tutoriálu jsme viděli, jak nakonfigurovat výchozí nastavení písma v dokumentu aplikace Word pomocí Aspose.Words for .NET. Zadáním zdrojů písem používaných při načítání a vykreslování dokumentů můžete ovládat vzhled písem ve svých dokumentech. Neváhejte použít tuto funkci k přizpůsobení nastavení písma ve vašich projektech.

### FAQ

#### Otázka: Jak mohu nastavit výchozí písmo v Aspose.Words?

 A: Chcete-li nastavit výchozí písmo v Aspose.Words, můžete použít`FontSettings` třída a`DefaultFontName` vlastnost určující název požadovaného písma.

#### Otázka: Mohu určit výchozí velikost písma v Aspose.Words?

 Odpověď: Ano, můžete zadat výchozí velikost písma v Aspose.Words pomocí`DefaultFontSize` vlastnictvím`FontSettings` třída. Můžete nastavit požadovanou velikost bodu.

#### Otázka: Je možné nastavit výchozí barvu písma v Aspose.Words?

 Odpověď: Ano, můžete nastavit výchozí barvu písma v Aspose.Words pomocí`DefaultColor` vlastnictvím`FontSettings` třída. Barvu můžete určit pomocí hodnot RGB nebo předdefinovaných názvů.

#### Otázka: Platí výchozí nastavení písma pro všechny dokumenty?

Odpověď: Ano, výchozí nastavení písma platí pro všechny dokumenty vytvořené nebo upravované v Aspose.Words, pokud nejsou nastavena specifická nastavení pro jednotlivý dokument.