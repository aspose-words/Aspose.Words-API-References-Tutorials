---
title: Neomezené upravitelné oblasti v dokumentu aplikace Word
linktitle: Neomezené upravitelné oblasti v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit neomezené upravitelné oblasti v dokumentu Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/document-protection/unrestricted-editable-regions/
---
V tomto tutoriálu vás provedeme kroky k použití funkce neomezených upravitelných oblastí Aspose.Words for .NET. Tato funkce umožňuje definovat oblasti v dokumentu aplikace Word, kde lze obsah upravovat bez omezení, i když je zbytek dokumentu pouze pro čtení. Postupujte podle následujících kroků:

## Krok 1: Vložení dokumentu a nastavení ochrany

Začněte načtením existujícího dokumentu:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Chraňte dokument nastavením typu ochrany pouze pro čtení a hesla

## Krok 2: Vytvoření upravitelné oblasti

Začněte vytvořením upravitelné oblasti pomocí objektů EditableRangeStart a EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Pro EditableRangeStart, který jsme právě vytvořili, je vytvořen objekt EditableRange.
EditableRange editableRange = edRangeStart.EditableRange;

// Vložte něco do upravitelného rozsahu.
builder.Writeln("Paragraph inside first editable range");

// Upravitelný rozsah je dobře tvarovaný, pokud má začátek a konec.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Krok 3: Přidejte obsah mimo upravitelné oblasti

Můžete přidat obsah mimo upravitelné oblasti, které zůstanou pouze pro čtení:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Krok 4: Uložte dokument

Nakonec upravený dokument uložte:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Chcete-li dokument uložit s upravitelnými oblastmi, nezapomeňte zadat správnou cestu a název souboru.

### Příklad zdrojového kódu pro neomezené upravitelné oblasti pomocí Aspose.Words pro .NET

Zde je kompletní zdrojový kód pro neomezené upravitelné oblasti pomocí Aspose.Words pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nahrajte dokument a vytvořte jej pouze pro čtení.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// Spusťte upravitelný rozsah.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Pro EditableRangeStart, který jsme právě vytvořili, je vytvořen objekt EditableRange.
EditableRange editableRange = edRangeStart.EditableRange;

// Vložte něco do upravitelného rozsahu.
builder.Writeln("Paragraph inside first editable range");

// Upravitelný rozsah je dobře tvarovaný, pokud má začátek a konec.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Podle těchto kroků můžete snadno vytvořit neomezené upravitelné oblasti v dokumentu aplikace Word pomocí Aspose.Words for .NET.

## Závěr
V tomto tutoriálu jsme se naučili, jak vytvořit neomezené upravitelné oblasti v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle uvedených kroků můžete definovat konkrétní oblasti v dokumentu, kde mohou uživatelé volně upravovat obsah, zatímco zbytek dokumentu zůstane pouze pro čtení. Aspose.Words for .NET nabízí výkonné funkce pro ochranu a přizpůsobení dokumentů a poskytuje vám kontrolu nad možnostmi úprav vašich dokumentů aplikace Word.

### Časté dotazy pro neomezené upravitelné oblasti v dokumentu aplikace Word

#### Otázka: Jaké jsou neomezené upravitelné oblasti v Aspose.Words pro .NET?

Odpověď: Neomezené upravitelné oblasti v Aspose.Words pro .NET jsou oblasti v dokumentu Word, kde lze obsah upravovat bez jakýchkoli omezení, i když je zbytek dokumentu nastaven jako pouze pro čtení. Tyto oblasti poskytují způsob, jak definovat konkrétní části dokumentu, které mohou uživatelé upravovat při zachování celkové ochrany dokumentu.

#### Otázka: Jak mohu vytvořit neomezené upravitelné oblasti pomocí Aspose.Words for .NET?

Odpověď: Chcete-li vytvořit neomezené upravitelné oblasti v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete postupovat takto:
1.  Načtěte existující dokument pomocí`Document` třída.
2.  Nastavte ochranu dokumentu na pouze pro čtení pomocí`Protect` metoda`Document` objekt.
3.  Použijte`DocumentBuilder` třídy k vytvoření upravitelného rozsahu přidáním`EditableRangeStart` objekt a an`EditableRangeEnd` objekt.
4.  Přidejte obsah v rámci upravitelného rozsahu pomocí`DocumentBuilder`.
5.  Uložte upravený dokument pomocí`Save` metoda`Document` objekt.

#### Otázka: Mohu mít v dokumentu aplikace Word více neomezených upravitelných oblastí?

Odpověď: Ano, v dokumentu aplikace Word můžete mít více neomezených upravitelných oblastí. Chcete-li toho dosáhnout, můžete vytvořit více sad`EditableRangeStart` a`EditableRangeEnd` objekty pomocí`DocumentBuilder` třída. Každá sada objektů bude definovat samostatnou upravitelnou oblast, kde mohou uživatelé upravovat obsah bez jakýchkoli omezení.

#### Otázka: Mohu do sebe vnořit upravitelné oblasti?

 Odpověď: Ne, pomocí Aspose.Words for .NET nemůžete do sebe vnořovat upravitelné oblasti. Každá editovatelná oblast definovaná pomocí an`EditableRangeStart` a`EditableRangeEnd` pár by měl být nezávislý a neměl by se překrývat ani být vnořený do jiné upravitelné oblasti. Vnořené upravitelné oblasti nejsou podporovány.

#### Otázka: Mohu odstranit ochranu pouze pro čtení z dokumentu v rámci upravitelné oblasti?

Odpověď: Ne, nemůžete odstranit ochranu pouze pro čtení z dokumentu v rámci upravitelné oblasti. Ochrana pouze pro čtení je aplikována na celý dokument a nelze ji selektivně odstranit v rámci určitých upravitelných oblastí. Účelem upravitelných oblastí je umožnit úpravu obsahu a zároveň zachovat celý dokument pouze pro čtení.