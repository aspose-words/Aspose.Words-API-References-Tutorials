---
title: Vytvořte projekt Vba v dokumentu aplikace Word
linktitle: Vytvořte projekt Vba v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: V tomto kurzu se dozvíte, jak vytvořit projekt VBA v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-vba-macros/create-vba-project/
---

V tomto tutoriálu vám řekneme, jak vytvořit projekt VBA v dokumentu aplikace Word pomocí knihovny Aspose.Words pro .NET. Vytvoření projektu VBA vám umožní přidat vlastní kód VBA do dokumentu aplikace Word. Provedeme vás krok za krokem, abychom vám pomohli pochopit a implementovat kód ve vašem projektu .NET.

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

## Krok 2: Vytvořte nový dokument a projekt VBA
 Dále vytvoříme nový dokument vytvořením instance`Document` třídy a prázdný projekt VBA vytvořením instance`VbaProject` třída.

```csharp
// Vytvořte nový dokument
Document doc = new Document();

//Vytvořte nový projekt VBA
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
```

## Krok 3: Vytvořte nový modul a zadejte zdrojový kód makra
 Vytvoříme nový modul vytvořením instance`VbaModule` třídy a uvedením názvu makra, typu (procedurálního modulu) a zdrojového kódu.

```csharp
// Vytvořte nový modul
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New Source Code";

// Přidejte modul do projektu VBA
doc.VbaProject.Modules.Add(module);
```

## Krok 4: Uložte dokument
Nakonec dokument s vytvořeným projektem VBA uložíme do souboru.

```csharp
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");
```

### Ukázkový zdrojový kód pro Create Vba Project pomocí Aspose.Words for .NET 

```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
// Vytvořte nový modul a zadejte zdrojový kód makra.
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";
// Přidejte modul do projektu VBA.
doc.VbaProject.Modules.Add(module);
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");

```

## Závěr
V tomto tutoriálu jsme viděli, jak vytvořit projekt VBA v dokumentu aplikace Word pomocí Aspose.Words for .NET. Vytvoření projektu VBA vám umožní přidat a upravit kód VBA do dokumentu aplikace Word. Neváhejte použít tuto funkci k automatizaci úloh nebo přidání vlastních funkcí do dokumentů aplikace Word.

### FAQ

#### Otázka: Co je projekt VBA v dokumentu aplikace Word?

Odpověď: Projekt VBA v dokumentu aplikace Word je kolekce modulů VBA obsahující kód, který lze použít k automatizaci úloh, přidání vlastních funkcí nebo provádění specifických operací v dokumentu aplikace Word.

#### Otázka: Jaké jsou předpoklady pro vytvoření projektu VBA v dokumentu aplikace Word?

A: Než budete moci vytvořit projekt VBA v dokumentu aplikace Word, musíte mít pracovní znalost programovacího jazyka C#. Do projektu je také potřeba nainstalovat knihovnu Aspose.Words for .NET.

#### Otázka: Jak nastavit adresář dokumentů v kódu?

 Odpověď: V poskytnutém kódu musíte nahradit`"YOUR DOCUMENTS DIRECTORY"` s příslušnou cestou k adresáři, kam chcete uložit dokument aplikace Word s projektem VBA.

#### Otázka: Jak specifikovat zdrojový kód makra v modulu VBA?

 Odpověď: Chcete-li zadat zdrojový kód makra v modulu VBA, můžete použít`SourceCode` majetek z`VbaModule` třídy tak, že jí přiřadíte znakový řetězec obsahující kód VBA.

#### Otázka: Mohu přidat více modulů VBA do projektu VBA v dokumentu aplikace Word?

Odpověď: Ano, do projektu VBA v dokumentu aplikace Word můžete přidat více modulů VBA vytvořením instance více`VbaModule` objektů a jejich přidání do`Modules` sbírka`VbaProject` objekt. To vám umožní uspořádat váš kód VBA do různých modulů pro lepší správu a opětovné použití.