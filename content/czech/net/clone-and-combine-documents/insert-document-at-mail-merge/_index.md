---
title: Vložit dokument při hromadné korespondenci
linktitle: Vložit dokument při hromadné korespondenci
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit dokument do jiného během hromadné korespondence pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
V tomto tutoriálu vás provedeme tím, jak vložit dokument do jiného dokumentu během hromadné korespondence pomocí funkce Vložit dokument během hromadné korespondence Aspose.Words for .NET. Chcete-li porozumět zdrojovému kódu a provést vložení dokumentu, postupujte podle následujících kroků.

## Krok 1: Načtení hlavního dokumentu

Chcete-li začít, zadejte adresář pro vaše dokumenty a načtěte hlavní dokument do objektu Document. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Krok 2: Nakonfigurujte hromadnou korespondenci

Nyní nakonfigurujeme hromadnou korespondenci a určete zpětné volání sloučení polí pro vložení dokumentu do jiného dokumentu. Zde je postup:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Krok 3: Spuštění hromadné korespondence

Hromadnou korespondenci spustíme zadáním názvů slučovacích polí a odpovídajících dat. Zde je postup:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Příklad zdrojového kódu pro Insert Document At Hromadná korespondence pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro funkci Vložit dokument do hromadné korespondence Aspose.Words pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// Hlavní dokument obsahuje slučovací pole s názvem "Document_1".
// Odpovídající data pro toto pole obsahují plně kvalifikovanou cestu k dokumentu.
// To by mělo být vloženo do tohoto pole.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

S tímto kódem budete moci vložit dokument do jiného dokumentu během hromadné korespondence pomocí Aspose.Words for .NET. Výsledný dokument bude uložen pod novým názvem


## Závěr

tomto tutoriálu jsme prozkoumali, jak vložit dokument do jiného dokumentu během hromadné korespondence pomocí funkce Vložit dokument během hromadné korespondence Aspose.Words for .NET. Nakonfigurováním hromadné korespondence a poskytnutím potřebných dat můžete dynamicky sestavit dokumenty sloučením různých šablon dokumentů nebo oddílů. Aspose.Words for .NET poskytuje flexibilní a výkonný způsob správy složitých scénářů generování dokumentů, díky čemuž je cenným nástrojem pro automatizaci úkolů při vytváření dokumentů a manipulaci s nimi.

### FAQ

#### Otázka: Jaký je účel vložení dokumentu do jiného dokumentu během hromadné korespondence?

Odpověď: Vložení dokumentu do jiného dokumentu během hromadné korespondence umožňuje dynamicky kombinovat různé šablony dokumentů nebo oddíly na základě dat poskytnutých během procesu hromadné korespondence. Tato funkce je zvláště užitečná, když chcete sestavit složité dokumenty sloučením různých předdefinovaných šablon nebo oddílů do konečného dokumentu.

#### Otázka: Jak vložím dokument do jiného dokumentu během hromadné korespondence pomocí Aspose.Words for .NET?

A: Chcete-li vložit dokument do jiného dokumentu během hromadné korespondence pomocí Aspose.Words for .NET, postupujte takto:
1. Načtěte hlavní dokument, který bude sloužit jako základ, do objektu dokumentu.
2. Nakonfigurujte hromadnou korespondenci a zadejte zpětné volání hromadné korespondence pro zpracování vkládání dokumentu.
3. Spusťte hromadnou korespondenci s názvy slučovacích polí a odpovídajícími daty (cesta k dokumentu, který má být vložen).

#### Otázka: Jak mohu přizpůsobit chování vkládání během hromadné korespondence?

Odpověď: Chcete-li přizpůsobit chování vkládání během hromadné korespondence, můžete implementovat vlastní FieldMergingCallback zděděním z rozhraní IFieldMergingCallback. To vám umožňuje řídit, jak se dokumenty vkládají a spojují na základě vašich specifických požadavků.

#### Otázka: Mohu během hromadné korespondence vložit více dokumentů?

Odpověď: Ano, během hromadné korespondence můžete vložit více dokumentů poskytnutím příslušných dat pro každé pole hromadné korespondence. Pro každé slučovací pole, které vyžaduje vložení dokumentu, zadejte jako data cestu k odpovídajícímu dokumentu.


