---
title: Vložit dokument při nahrazení
linktitle: Vložit dokument při nahrazení
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit dokument při nahrazení pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/clone-and-combine-documents/insert-document-at-replace/
---
V tomto tutoriálu vás provedeme tím, jak vložit dokument do jiného dokumentu při nahrazení pomocí funkce Vložit dokument při nahrazení Aspose.Words for .NET. Chcete-li porozumět zdrojovému kódu a provést vložení dokumentu, postupujte podle následujících kroků.

## Krok 1: Načtení hlavního dokumentu

Chcete-li začít, zadejte adresář pro vaše dokumenty a načtěte hlavní dokument do objektu Document. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Krok 2: Nakonfigurujte možnosti vyhledávání a nahrazování

Nyní nakonfigurujeme možnosti hledání a nahrazení zadáním směru hledání a zpětného volání nahrazení pro vložení dokumentu do jiného dokumentu. Zde je postup:

```csharp
// Nakonfigurujte možnosti hledání a nahrazování.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Krok 3: Volání metody výměny

Nyní zavoláme metodu nahradit, abychom našli a nahradili zadaný text prázdným řetězcem pomocí nakonfigurovaných možností. Zde je postup:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Příklad zdrojového kódu pro Insert Document At Replace pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro funkci Vložit dokument při nahrazení Aspose.Words pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Nastavte možnosti hledání a nahrazení.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Zavolejte metodu nahrazení.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak vložit dokument do jiného dokumentu během nahrazování pomocí funkce Vložit dokument při nahrazení Aspose.Words for .NET. Nakonfigurováním možností hledání a nahrazení a poskytnutím potřebných dat můžete dynamicky sestavit dokumenty nahrazením určitých zástupných symbolů obsahem jiných šablon nebo oddílů dokumentů. Aspose.Words for .NET nabízí výkonný a flexibilní způsob, jak spravovat složité úlohy manipulace s dokumenty, což z něj činí cenný nástroj pro automatizaci vytváření dokumentů a scénářů vkládání obsahu.

### FAQ

#### Otázka: Jaký je účel vložení dokumentu do jiného dokumentu během výměny?

Odpověď: Vložení dokumentu do jiného dokumentu během nahrazování umožňuje dynamicky nahradit konkrétní zástupný objekt obsahem samostatného dokumentu. Tato funkce je užitečná zejména tehdy, chcete-li sestavit větší dokument kombinací různých předdefinovaných šablon dokumentu nebo oddílů do konkrétních zástupných symbolů.

#### Otázka: Jak vložím dokument do jiného dokumentu během nahrazování pomocí Aspose.Words for .NET?

A: Chcete-li vložit dokument do jiného dokumentu během nahrazování pomocí Aspose.Words for .NET, postupujte takto:
1. Načtěte hlavní dokument, který obsahuje zástupné symboly, do objektu dokumentu.
2. Nakonfigurujte možnosti hledání a nahrazování, včetně směru hledání a zpětného volání nahrazení, aby se zvládlo vkládání dokumentu.
3. Zavolejte metodu nahrazení s příslušným vyhledávacím vzorem a nahraďte zástupné symboly prázdným řetězcem pomocí nakonfigurovaných možností.

#### Otázka: Mohu přizpůsobit chování vkládání během výměny?

Odpověď: Ano, můžete přizpůsobit chování vkládání během nahrazování implementací vlastního ReplacingCallback. Děděním z rozhraní IReplacingCallback můžete řídit způsob vkládání a slučování dokumentů na základě vašich konkrétních požadavků při nahrazování zástupných symbolů.

#### Otázka: Mohu nahradit více zástupných symbolů různými dokumenty?

Odpověď: Ano, můžete nahradit více zástupných symbolů různými dokumenty zadáním vhodných vyhledávacích vzorů pro každý zástupný symbol a poskytnutím odpovídajících dokumentů, které mají být vloženy.