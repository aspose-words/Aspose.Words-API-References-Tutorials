---
title: Neomezená sekce v dokumentu aplikace Word
linktitle: Neomezená sekce v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se definovat neomezené sekce v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/document-protection/unrestricted-section/
---
V tomto tutoriálu vás provedeme kroky k použití funkce neomezené sekce Aspose.Words for .NET. Tato funkce umožňuje definovat konkrétní části v dokumentu aplikace Word, které nejsou chráněny, i když je chráněn zbytek dokumentu. Postupujte podle následujících kroků:

## Krok 1: Vytvoření dokumentu a oddílů

Začněte vytvořením instance třídy Document a objektu DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Přidejte obsah do dokumentu
Pomocí objektu DocumentBuilder přidejte obsah do dokumentu a vložte konce oddílů:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Krok 3: Ochrana dokumentu a oddílů

Ochrana oddílů funguje pouze v případě, že je povolena ochrana dokumentu a jsou povoleny pouze úpravy v polích formuláře. Dokument můžete chránit pomocí metody Protect() objektu Document:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Nezapomeňte zadat správný typ ochrany a nastavit požadované heslo.

## Krok 4: Deaktivace ochrany pro konkrétní sekci

Ve výchozím nastavení jsou chráněny všechny sekce, ale ochranu pro konkrétní sekci můžete selektivně zakázat pomocí vlastnosti ProtectedForms objektu Section:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

V tomto příkladu je ochrana pro první sekci deaktivována.

## Krok 5: Uložte dokument

Nakonec upravený dokument uložte:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Nezapomeňte zadat správnou cestu a název souboru, aby se dokument uložil s neomezenými sekcemi.

### Příklad zdrojového kódu pro Unrestricted Section pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro neomezenou sekci pomocí Aspose.Words pro .NET:


```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Vložte dvě sekce s nějakým textem.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// Ochrana sekcí funguje pouze tehdy, když je zapnutá ochrana dokumentu a jsou povoleny pouze úpravy v polích formuláře.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//Ve výchozím nastavení jsou chráněny všechny sekce, ale ochranu můžeme selektivně vypnout.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Podle těchto kroků budete moci snadno definovat neomezené sekce v dokumentu aplikace Word pomocí Aspose.Words for .NET.

## Závěr

V tomto tutoriálu jsme prozkoumali funkci neomezených sekcí Aspose.Words for .NET, která umožňuje, aby určité sekce v dokumentu aplikace Word zůstaly nechráněné, zatímco zbytek dokumentu je chráněn. Podle uvedených kroků můžete snadno definovat sekce v dokumentu, kde mohou uživatelé volně upravovat obsah při zachování ochrany pro ostatní sekce. Aspose.Words for .NET nabízí výkonné funkce pro ochranu a přizpůsobení dokumentů, což vám dává kontrolu nad oprávněními k úpravám v dokumentech aplikace Word.

### Časté dotazy pro neomezenou sekci v dokumentu aplikace Word

#### Otázka: Jaké jsou neomezené sekce v Aspose.Words pro .NET?

Odpověď: Neomezené sekce v Aspose.Words pro .NET jsou specifické sekce v dokumentu aplikace Word, které nejsou chráněny, i když je chráněn zbytek dokumentu. Tyto sekce umožňují uživatelům upravovat obsah v nich při zachování ochrany pro zbývající části dokumentu.

#### Otázka: Jak mohu vytvořit neomezené sekce pomocí Aspose.Words pro .NET?

Odpověď: Chcete-li vytvořit neomezené sekce v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete postupovat takto:
1.  Vytvořte instanci souboru`Document` třída a a`DocumentBuilder` objekt.
2.  Použijte`DocumentBuilder` přidat obsah do dokumentu a vložit konce oddílů.
3.  Chraňte dokument pomocí`Protect` metoda`Document` objekt s uvedením požadovaného typu ochrany a hesla.
4.  Vypněte ochranu pro konkrétní sekci nastavením`ProtectedForForms` vlastnost odpovídající`Section` namítat proti`false`.
5. Uložte upravený dokument.

#### Otázka: Mohu mít v dokumentu aplikace Word více neomezených sekcí?

 Odpověď: Ano, v dokumentu aplikace Word můžete mít více neomezených sekcí. Selektivním vypnutím ochrany pro konkrétní sekce pomocí`ProtectedForForms` vlastnictvím`Section`objektu, můžete definovat více sekcí, kde mohou uživatelé libovolně upravovat obsah, zatímco ostatní sekce budou chráněny.

#### Q4. Mohu odstranit ochranu ze sekce, která byla původně chráněna?
 Ano, můžete odstranit ochranu ze sekce, která byla původně chráněna nastavením`ProtectedForForms` vlastnost odpovídající`Section` namítat proti`false`. To umožňuje uživatelům upravovat obsah v této konkrétní sekci bez jakýchkoli omezení.

#### Otázka: Jaké typy ochrany lze použít na dokument aplikace Word?

Odpověď: Aspose.Words for .NET poskytuje různé typy ochrany, které lze použít na dokument aplikace Word, včetně:
- NoProtection: Není aplikována žádná ochrana.
- AllowOnlyRevisions: Uživatelé mohou provádět pouze revize dokumentu.
- AllowOnlyComments: Uživatelé mohou k dokumentu přidávat pouze komentáře.
- AllowOnlyFormFields: Uživatelé mohou v dokumentu upravovat pouze pole formuláře.
- ReadOnly: Dokument je pouze pro čtení a nejsou povoleny žádné úpravy.


