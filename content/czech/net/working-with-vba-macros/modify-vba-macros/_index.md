---
title: Upravit makra Vba dokumentu aplikace Word
linktitle: Upravit makra Vba dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: V tomto kurzu se dozvíte, jak upravit makra VBA dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-vba-macros/modify-vba-macros/
---
V tomto tutoriálu vysvětlíme, jak upravit makra VBA dokumentu aplikace Word pomocí knihovny Aspose.Words pro .NET. Úpravy maker VBA umožňují aktualizovat stávající kód VBA v dokumentu aplikace Word. Provedeme vás krok za krokem, abychom vám pomohli pochopit a implementovat kód ve vašem projektu .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words pro .NET nainstalovaná ve vašem projektu
- Dokument aplikace Word obsahující makra VBA, která chcete upravit

## Krok 1: Definujte adresář dokumentů
 Nejprve musíte nastavit cestu k adresáři na umístění vašeho dokumentu aplikace Word. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s příslušnou cestou.

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Načtěte dokument obsahující makra VBA
Dále načteme dokument aplikace Word obsahující makra VBA, která chceme upravit.

```csharp
// Načtěte dokument obsahující makra VBA
Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
```

## Krok 3: Upravte zdrojový kód makra
Nyní upravíme zdrojový kód prvního makra projektu VBA. Nahradit`newSourceCode` proměnnou s novým zdrojovým kódem, který chcete použít.

```csharp
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
```

## Krok 4: Uložte upravený dokument
Nakonec upravený dokument s aktualizovanými makry VBA uložíme do souboru.

```csharp
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");
```

### Ukázka zdrojového kódu pro úpravu maker Vba pomocí Aspose.Words pro .NET
 
```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");

```

## Závěr
V tomto tutoriálu jsme viděli, jak upravit makra VBA v dokumentu aplikace Word pomocí Aspose.Words for .NET. Úpravy maker VBA vám umožňují aktualizovat stávající kód VBA v dokumentu a provádět změny nebo vylepšení. Neváhejte použít tuto funkci k dalšímu přizpůsobení a automatizaci dokumentů aplikace Word.

### FAQ

#### Otázka: Co je makro VBA v dokumentu aplikace Word?

Odpověď: Makro VBA v dokumentu aplikace Word je část kódu, kterou lze spustit k provedení konkrétních akcí v dokumentu. Makra VBA umožňují automatizovat úlohy, přidávat vlastní funkce a pracovat s obsahem dokumentu.

#### Otázka: Jaké jsou předpoklady pro úpravy maker jazyka VBA v dokumentu aplikace Word?

Odpověď: Než budete moci upravovat makra VBA v dokumentu aplikace Word, musíte mít pracovní znalost programovacího jazyka C#. Do projektu je také potřeba nainstalovat knihovnu Aspose.Words for .NET. Potřebujete také dokument aplikace Word obsahující makra jazyka VBA, která chcete upravit.

#### Otázka: Jak nastavit adresář dokumentů v kódu?

 Odpověď: V poskytnutém kódu musíte nahradit`"YOUR DOCUMENTS DIRECTORY"` s příslušnou cestou k adresáři, kde se nachází váš dokument aplikace Word obsahující makra VBA.

#### Otázka: Jak určit nový zdrojový kód makra, které chcete upravit?

 Odpověď: Chcete-li zadat nový zdrojový kód makra, které chcete upravit, můžete použít`SourceCode` vlastnost odpovídající`VbaModule` objekt tak, že mu přiřadíte znakový řetězec obsahující nový kód VBA.

#### Otázka: Mohu upravit více maker VBA v dokumentu aplikace Word najednou?

 Odpověď: Ano, můžete upravit více maker VBA v dokumentu aplikace Word pomocí smyčky nebo přímým přístupem k odpovídajícím`VbaModule` objekty v`Modules` sbírka`VbaProject` objekt. To vám umožní aktualizovat více maker VBA současně v jedné operaci.