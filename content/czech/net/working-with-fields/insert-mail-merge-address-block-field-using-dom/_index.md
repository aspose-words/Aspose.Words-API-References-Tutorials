---
title: Vložte pole bloku adresy hromadné korespondence pomocí DOM
linktitle: Vložte pole bloku adresy hromadné korespondence pomocí DOM
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit pole bloku adresy hromadné korespondence do dokumentů aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Zde je podrobný návod k vysvětlení níže uvedeného zdrojového kódu C#, který používá funkci "Vložit pole bloku adresy hromadné korespondence" Aspose.Words for .NET. Ujistěte se, že pečlivě dodržujete každý krok, abyste dosáhli požadovaných výsledků.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém kódu musíte zadat adresář vašich dokumentů. Nahraďte hodnotu „VÁŠ ADRESÁŘ DOKUMENTŮ“ příslušnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření dokumentu a DocumentBuilderu

Začneme vytvořením nového dokumentu a inicializací DocumentBuilderu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Přesunutí kurzoru na odstavec

 Používáme DocumentBuilder's`MoveTo()` metodou přesuneme kurzor na odstavec, kam chceme vložit pole bloku adresy hromadné korespondence.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Krok 4: Vložení pole bloku adresy hromadné korespondence

 Používáme DocumentBuilder's`InsertField()` metoda pro vložení pole adresy bloku hromadné korespondence do odstavce.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Poté nakonfigurujeme vlastnosti pole bloku adresy s uvedením příslušných možností, jako je zahrnutí názvu země/oblasti, formátování adresy podle země/oblasti, vyloučení názvů zemí/oblastí, formátu jména a adresy a identifikátoru jazyka.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Nakonec zavoláme`Update()` způsob aktualizace pole.

```csharp
field. Update();
```

### Ukázkový zdrojový kód pro vložení pole adresy bloku hromadné korespondence pomocí Aspose.Words pro .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Chceme vložit blok adresy hromadné korespondence takto:
// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { ADDRESSBLOCK \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { ADDRESSBLOCK \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### FAQ

#### Otázka: Jak mohu upravit formát poštovní adresy v dokumentu aplikace Word pomocí Aspose.Words for .NET?

 Odpověď: Můžete upravit formát poštovní adresy v dokumentu aplikace Word pomocí Aspose.Words for .NET pomocí vlastností`FieldAddressBlock`objekt. Můžete nastavit možnosti formátování, jako je styl adresy, oddělovače, volitelné položky atd., abyste získali požadovaný formát.

#### Otázka: Jak mohu zadat zdrojová data pro pole poštovní adresy v Aspose.Words for .NET?

 Odpověď: Chcete-li zadat zdrojová data pro pole poštovní adresy v Aspose.Words pro .NET, můžete použít`FieldAddressBlock.StartAddress`a`FieldAddressBlock.EndAddress` vlastnosti. Tyto vlastnosti se používají k definování rozsahů adres v externím zdroji dat, jako je soubor CSV, databáze atd.

#### Otázka: Mohu zahrnout volitelné prvky do pole poštovní adresy s Aspose.Words pro .NET?

 Odpověď: Ano, můžete zahrnout volitelné prvky do pole poštovní adresy pomocí Aspose.Words for .NET. Volitelné prvky můžete definovat pomocí`FieldAddressBlock.OmitOptional` metoda k určení, zda zahrnout nebo vyloučit volitelné prvky, jako je jméno příjemce, název společnosti atd.

#### Otázka: Má vložení pole poštovní adresy pomocí DOM vliv na strukturu dokumentu aplikace Word s Aspose.Words for .NET?

Odpověď: Vložení pole poštovní adresy pomocí modelu DOM přímo neovlivňuje strukturu dokumentu aplikace Word. Do obsahu dokumentu však přidá nový prvek pole. Strukturu dokumentu můžete upravovat přidáním, odstraněním nebo úpravou stávajících prvků podle vašich potřeb.