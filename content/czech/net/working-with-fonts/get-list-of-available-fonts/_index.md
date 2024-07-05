---
title: Získejte seznam dostupných písem
linktitle: Získejte seznam dostupných písem
second_title: Aspose.Words API pro zpracování dokumentů
description: tomto tutoriálu se dozvíte, jak získat seznam písem dostupných v Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/get-list-of-available-fonts/
---
V tomto tutoriálu vysvětlíme, jak získat seznam písem dostupných v Aspose.Words pro .NET. Seznam dostupných písem vám dává vědět, která písma můžete použít ve svých dokumentech. Provedeme vás krok za krokem, abychom vám pomohli pochopit a implementovat kód ve vašem projektu .NET.

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

## Krok 2: Nakonfigurujte zdroje písem
 Dále vytvoříme instanci`FontSettings` a získat existující zdroje písem pomocí`GetFontsSources()` metoda. Přidáme také nový zdroj písem zadáním složky obsahující písma.

```csharp
// Konfigurace zdrojů písem
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Přidejte nový zdroj písem
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Krok 3: Získejte seznam dostupných písem
 Nyní budeme procházet dostupná písma pomocí`GetAvailableFonts()` metoda na prvním aktualizovaném zdroji písem.

```csharp
// Získejte seznam dostupných písem
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Ukázka zdrojového kódu pro získání seznamu dostupných písem pomocí Aspose.Words pro .NET 

```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Přidejte nový zdroj složky, který dá Aspose.Words pokyn k hledání písem v následující složce.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
//Přidejte vlastní složku, která obsahuje naše písma, do seznamu existujících zdrojů písem.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Závěr
V tomto tutoriálu jsme viděli, jak získat seznam písem dostupných v Aspose.Words pro .NET. Díky tomu zjistíte, která písma můžete ve svých dokumentech použít. Neváhejte použít tuto funkci k výběru vhodných písem pro vaše potřeby.

### FAQ

#### Otázka: Jak mohu získat seznam písem dostupných v Aspose.Words?

 A: Chcete-li získat seznam písem dostupných v Aspose.Words, můžete použít`FontsProvider` třída a`GetAvailableFonts` metoda. Tato metoda vrátí seznam všech písem nainstalovaných ve vašem systému.

#### Otázka: Mohu filtrovat seznam dostupných písem podle určitých kritérií v Aspose.Words?

Odpověď: Ano, můžete filtrovat seznam písem dostupných v Aspose.Words pomocí specifických kritérií. Můžete například filtrovat písma podle rodiny, stylu nebo jazyka.

#### Otázka: Jak mohu použít seznam dostupných písem v dokumentech aplikace Word?

Odpověď: Chcete-li použít seznam písem dostupných ve vašich dokumentech aplikace Word, můžete procházet seznam a vybrat vhodná písma pomocí metod a vlastností`FontSettings` třídy v Aspose.Words.