---
title: Export struktury dokumentu Word do dokumentu PDF
linktitle: Export struktury dokumentu Word do dokumentu PDF
second_title: Aspose.Words API pro zpracování dokumentů
description: Krok za krokem průvodce exportem struktury dokumentu Word do dokumentu PDF pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/export-document-structure/
---

Tento článek obsahuje podrobného průvodce, jak používat funkci Export struktury dokumentu Word do dokumentu PDF s Aspose.Words pro .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto tutoriálu budete schopni porozumět tomu, jak exportovat strukturu dokumentu a vygenerovat PDF s viditelnou strukturou dokumentu.

Než začnete, ujistěte se, že jste ve svém projektu nainstalovali a nakonfigurovali knihovnu Aspose.Words for .NET. Knihovnu a pokyny k instalaci najdete na webu Aspose.

## Krok 1: Definujte adresář dokumentů

 Chcete-li začít, musíte definovat cestu k adresáři, kde jsou umístěny vaše dokumenty. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Nahrajte dokument

Dále musíme načíst dokument, který chceme zpracovat. V tomto příkladu předpokládáme, že dokument se nazývá "Paragraphs.docx" a je umístěn v určeném adresáři dokumentů.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Krok 3: Nakonfigurujte možnosti uložení jako PDF

 Chcete-li exportovat strukturu dokumentu a zviditelnit strukturu v navigačním panelu „Obsah“ aplikace Adobe Acrobat Pro při úpravách souboru PDF, musíme nakonfigurovat`PdfSaveOptions` objekt s`ExportDocumentStructure` vlastnost nastavena na`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Krok 4: Uložte dokument jako PDF se strukturou dokumentu

Nakonec můžeme dokument uložit ve formátu PDF pomocí dříve nakonfigurovaných možností uložení.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

To je vše ! Úspěšně jste exportovali strukturu dokumentu a vygenerovali PDF s viditelnou strukturou dokumentu pomocí Aspose.Words for .NET.

### Ukázka zdrojového kódu pro export struktury dokumentu pomocí Aspose.Words pro .NET


```csharp

            // Cesta k adresáři dokumentů.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // Velikost souboru se zvětší a struktura bude viditelná v navigačním panelu "Obsah".
            // Adobe Acrobat Pro při úpravě souboru .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## Závěr

V tomto tutoriálu jsme vysvětlili, jak exportovat strukturu dokumentu Word do dokumentu PDF pomocí Aspose.Words for .NET. Podle uvedených kroků můžete snadno vygenerovat PDF s viditelnou strukturou dokumentu, což usnadní navigaci a prohledávání dokumentu. Pomocí funkcí Aspose.Words for .NET můžete exportovat strukturu dokumentů aplikace Word a vytvářet dobře strukturované soubory PDF.

### Často kladené otázky

#### Otázka: Co je export struktury dokumentu aplikace Word do dokumentu PDF?
Odpověď: Exportováním struktury dokumentu aplikace Word do dokumentu PDF se vytvoří PDF s viditelnou strukturou dokumentu. Struktura dokumentu obvykle zahrnuje věci, jako jsou nadpisy, oddíly, odstavce a další strukturované prvky dokumentu. Tato struktura může být užitečná pro navigaci a vyhledávání v dokumentu PDF.

#### Otázka: Jak mohu exportovat strukturu dokumentu aplikace Word do dokumentu PDF pomocí Aspose.Words for .NET?
Odpověď: Chcete-li exportovat strukturu dokumentu aplikace Word do dokumentu PDF pomocí Aspose.Words for .NET, postupujte takto:

 Vytvořte instanci souboru`Document` třídy určující cestu k dokumentu aplikace Word.

 Vytvořte instanci souboru`PdfSaveOptions` třídu a nastavte`ExportDocumentStructure`majetek do`true`. Tím se exportuje struktura dokumentu a při úpravě souboru PDF se zviditelní v navigačním panelu „Obsah“ aplikace Adobe Acrobat Pro.

 Použijte`Save` metoda`Document`třídy pro uložení dokumentu ve formátu PDF zadáním možností uložení.

#### Otázka: Jak mohu zobrazit strukturu dokumentu PDF pomocí aplikace Adobe Acrobat Pro?
Odpověď: Chcete-li zobrazit strukturu dokumentu PDF pomocí aplikace Adobe Acrobat Pro, postupujte takto:

Otevřete dokument PDF v aplikaci Adobe Acrobat Pro.

levém navigačním panelu klikněte na ikonu "Obsah" pro zobrazení navigačního panelu "Obsah".

V navigačním panelu "Obsah" uvidíte strukturu dokumentu s nadpisy, sekcemi a dalšími strukturovanými prvky.