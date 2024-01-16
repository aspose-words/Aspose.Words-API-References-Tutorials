---
title: Vložit ASKField bez Tvůrce dokumentů
linktitle: Vložit ASKField bez Tvůrce dokumentů
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit pole ASK do dokumentů aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Zde je podrobný návod k vysvětlení zdrojového kódu C# níže, který používá funkci "Vložit pole ASK bez DocumentBuilder" Aspose.Words for .NET. Ujistěte se, že pečlivě dodržujete každý krok, abyste dosáhli požadovaných výsledků.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém kódu musíte zadat adresář vašich dokumentů. Nahraďte hodnotu „VÁŠ ADRESÁŘ DOKUMENTŮ“ příslušnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření dokumentu a odstavce

Začneme vytvořením nového dokumentu a načtením prvního odstavce.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Krok 3: Vložení pole ASK

 Používáme`AppendField()` metoda pro vložení pole ASK do odstavce.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Poté nakonfigurujeme různé vlastnosti pole ASK zadáním požadovaných hodnot.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Nakonec zavoláme`Update()` způsob aktualizace pole.

```csharp
field. Update();
```

### Příklad zdrojového kódu pro vložení pole ASK bez DocumentBuilder s Aspose.Words for .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvoření dokumentu.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Vložte pole ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

tomto příkladu jsme vytvořili nový dokument, vložili pole ASK bez použití DocumentBuilder, nakonfigurovali různé vlastnosti pole a uložili dokument se zadaným názvem souboru.

Tímto končí náš průvodce používáním funkce "Vložit pole ASK bez DocumentBuilder" s Aspose.Words pro .NET.

### FAQ

#### Otázka: Co je pole ASK v Aspose.Words?

A: Pole ASK v Aspose.Words se používá k položení otázky uživateli při otevírání dokumentu. Často se používá k vyžádání konkrétních informací nebo zpětné vazby, které se mohou lišit od uživatele k uživateli.

#### Otázka: Jak vložit pole ASK do dokumentu aplikace Word bez použití Tvůrce dokumentů v Aspose.Words?

Odpověď: Chcete-li vložit pole ASK do dokumentu aplikace Word bez použití Tvůrce dokumentů v Aspose.Words, můžete postupovat takto:

1. Importujte třídu Document a Field z oboru názvů Aspose.Words.Fields.
2. Vytvořte instanci dokumentu načtením existujícího dokumentu.
3. Pomocí metody InsertField vložte pole ASK zadáním názvu otázky.
4. Uložte dokument.

#### Otázka: Jak získám uživatelskou odpověď pro pole ASK v dokumentu aplikace Word?

Odpověď: Chcete-li získat odpověď uživatele na pole ASK v dokumentu aplikace Word, můžete použít metodu GetFieldNames dostupnou ve třídě Document. Tato metoda vrací seznam názvů polí přítomných v dokumentu. Poté můžete zkontrolovat, zda je v seznamu přítomen název pole ASK, a získat přidruženou odpověď.

#### Otázka: Lze pole ASK použít k vyžádání dalších informací od uživatele?

Odpověď: Ano, pole ASK lze použít k vyžádání více informací od uživatele. Do dokumentu můžete vložit více polí ASK, každé s jinou otázkou. Po otevření dokumentu bude uživatel vyzván k zadání odpovídajících odpovědí.