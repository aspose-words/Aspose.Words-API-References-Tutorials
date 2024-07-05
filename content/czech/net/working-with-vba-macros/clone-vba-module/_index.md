---
title: Klonovat modul Vba z dokumentu aplikace Word
linktitle: Klonovat modul Vba z dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: V tomto tutoriálu se dozvíte, jak klonovat modul VBA z dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-vba-macros/clone-vba-module/
---

V tomto tutoriálu vám řekneme, jak naklonovat modul VBA z dokumentu aplikace Word pomocí maker pomocí knihovny Aspose.Words pro .NET. Klonování modulu VBA vám umožňuje znovu použít nebo zkopírovat kód VBA z jednoho zdrojového dokumentu do jiného dokumentu. Provedeme vás krok za krokem, abychom vám pomohli pochopit a implementovat kód ve vašem projektu .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words pro .NET nainstalovaná ve vašem projektu
- Dokument aplikace Word obsahující projekt VBA s modulem, který chcete klonovat

## Krok 1: Definujte adresář dokumentů
 Nejprve musíte nastavit cestu k adresáři na umístění vašeho dokumentu aplikace Word. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s příslušnou cestou.

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Načtěte zdrojový dokument
Dále načteme zdrojový dokument Word, který obsahuje projekt VBA a modul, který chceme naklonovat.

```csharp
// Načtěte zdrojový dokument
Document doc = new Document(dataDir + "VBA project.docm");
```

## Krok 3: Vytvořte nový dokument s projektem VBA a naklonujte modul
Vytvoříme nový dokument s prázdným projektem VBA a naklonujeme zadaný modul ze zdrojového dokumentu.

```csharp
// Vytvořte nový dokument s prázdným projektem VBA
Document destDoc = new Document { VbaProject = new VbaProject() };

// Naklonujte modul
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## Krok 4: Uložte cílový dokument
Nakonec cílový dokument s naklonovaným modulem VBA uložíme do souboru.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Ukázka zdrojového kódu pro modul Clone Vba pomocí Aspose.Words pro .NET 
```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Závěr
V tomto tutoriálu jsme viděli, jak klonovat modul VBA z dokumentu aplikace Word pomocí maker pomocí Aspose.Words for .NET. Klonování modulů VBA umožňuje snadno znovu použít kód VBA z jednoho zdrojového dokumentu v jiném dokumentu. Neváhejte použít tuto funkci k uspořádání a správě maker v různých dokumentech.

### FAQ

#### Otázka: Co je duplikování modulu VBA?

Odpověď: Duplikování modulu VBA spočívá v zkopírování modulu obsahujícího kód VBA ze zdrojového dokumentu aplikace Word do jiného dokumentu. To vám umožní znovu použít kód VBA v různých kontextech nebo jej sdílet s jinými dokumenty.

#### Otázka: Jaké jsou předpoklady pro klonování modulu VBA z dokumentu aplikace Word?

Odpověď: Než budete moci klonovat modul VBA z dokumentu aplikace Word, musíte mít pracovní znalost programovacího jazyka C#. Do projektu je také potřeba nainstalovat knihovnu Aspose.Words for .NET. Také potřebujete dokument aplikace Word obsahující projekt VBA s modulem, který chcete naklonovat.

#### Otázka: Jak nastavit adresář dokumentů v kódu?

 Odpověď: V poskytnutém kódu musíte nahradit`"YOUR DOCUMENTS DIRECTORY"` s příslušnou cestou k adresáři, kde se nachází váš dokument aplikace Word obsahující projekt VBA.

#### Otázka: Jak uložit cílový dokument pomocí klonovaného modulu VBA?

 A: Chcete-li uložit cílový dokument s klonovaným modulem VBA, můžete použít`Save` metoda`Document` třídy zadáním požadované cílové cesty a názvu souboru.