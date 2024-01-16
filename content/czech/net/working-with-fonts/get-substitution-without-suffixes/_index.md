---
title: Získejte substituci bez přípon
linktitle: Získejte substituci bez přípon
second_title: Aspose.Words API pro zpracování dokumentů
description: V tomto kurzu se dozvíte, jak získat přepsání bez přípon v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/get-substitution-without-suffixes/
---

V tomto tutoriálu vám ukážeme, jak získat přepsání bez přípon v dokumentu aplikace Word pomocí knihovny Aspose.Words pro .NET. Náhrady bez přípon se používají k řešení problémů se záměnou písem při zobrazování nebo tisku dokumentů. Provedeme vás krok za krokem, abychom vám pomohli pochopit a implementovat kód ve vašem projektu .NET.

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

## Krok 2: Načtěte dokument a nakonfigurujte náhrady bez přípon
 Dále načteme dokument pomocí`Document` třídy a nakonfigurujte bezpříponové substituce pomocí`DocumentSubstitutionWarnings` třída. Přidáme také zdroj písem zadáním složky obsahující písma.

```csharp
// Načtěte dokument a nakonfigurujte náhrady bez přípon
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Krok 3: Uložte dokument
Nakonec dokument uložíme s aplikovaným přepsáním bez přípon.

```csharp
// Uložte dokument
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Ukázkový zdrojový kód pro Get Substitution Without Suffixes pomocí Aspose.Words for .NET 
```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Závěr
V tomto tutoriálu jsme viděli, jak získat přepsání bez přípon v dokumentu aplikace Word pomocí Aspose.Words pro .NET. Náhrady bez přípon jsou užitečné při řešení problémů se záměnou písem. Neváhejte využít tuto funkci ke zlepšení zobrazení a tisku vašich dokumentů.

### FAQ

#### Otázka: Proč Aspose.Words přidává přípony k náhradám písem?

Odpověď: Aspose.Words přidává k náhradám písem přípony, aby se zabránilo konfliktům mezi původními písmy a nahrazenými písmy. To pomáhá zajistit maximální kompatibilitu při převodu a manipulaci s dokumenty.

#### Otázka: Jak mohu v Aspose.Words získat náhrady písem bez přípon?

 Odpověď: Chcete-li v Aspose.Words načíst náhrady písem bez přípon, můžete použít`FontSubstitutionSettings` třída a`RemoveSuffixes` vlastnictví. Nastavení této vlastnosti na`true` získá náhrady písem bez přidaných přípon.

#### Otázka: Je možné zakázat přidávání přípon do náhrad písem v Aspose.Words?

Odpověď: Ne, v Aspose.Words není možné zakázat přidávání přípon do substitucí písem. Ve výchozím nastavení se přidávají přípony, aby byla zajištěna kompatibilita a konzistence dokumentů.

#### Otázka: Jak mohu odfiltrovat nežádoucí přípony v náhradách písem v Aspose.Words?

 Odpověď: Chcete-li odfiltrovat nežádoucí přípony v náhradách písem v Aspose.Words, můžete použít techniky zpracování řetězců, jako je`Replace` nebo`Substring` metody k odstranění konkrétních přípon, které nechcete zahrnout.