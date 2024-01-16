---
title: Odebrat ochranu dokumentu v dokumentu aplikace Word
linktitle: Odebrat ochranu dokumentu v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak odstranit ochranu v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/document-protection/remove-document-protection/
---
V tomto tutoriálu vás provedeme kroky k použití funkce odemknutí dokumentu Aspose.Words pro .NET. Tato funkce umožňuje odstranit ochranu v dokumentu aplikace Word a zpřístupnit jej pro další úpravy. Postupujte podle následujících kroků:

## Krok 1: Vytvoření dokumentu a přidání obsahu

Začněte vytvořením instance třídy Document a objektu DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Přidejte obsah do dokumentu

K přidání obsahu do dokumentu použijte objekt DocumentBuilder:

```csharp
builder.Writeln("Text added to a document.");
```

## Krok 3: Zrušte ochranu dokumentu

Chcete-li zrušit ochranu dokumentu, můžete použít metodu Unprotect() objektu Document. Můžete se rozhodnout odstranit ochranu bez hesla nebo se správným heslem. Odebrání ochrany bez hesla:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Nezapomeňte nahradit „newPassword“ správným heslem dokumentu.

## Krok 4: Uložte dokument bez ochrany

Nakonec uložte dokument nechráněný pomocí metody Save() objektu Document:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Chcete-li dokument uložit nechráněný, nezapomeňte zadat správnou cestu a název souboru.

### Příklad zdrojového kódu pro Remove Document Protection pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro odblokování dokumentu pomocí Aspose.Words pro .NET:

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

// U dokumentů lze ochranu odstranit buď bez hesla, nebo se správným heslem.
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

Pomocí následujících kroků můžete snadno odstranit ochranu z dokumentu aplikace Word pomocí Aspose.Words for .NET.

## Závěr

V tomto tutoriálu jsme prozkoumali, jak odstranit ochranu dokumentu v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle uvedených kroků můžete snadno zrušit ochranu dokumentu a zpřístupnit jej pro další úpravy. Aspose.Words for .NET poskytuje výkonné rozhraní API, které vám umožňuje manipulovat s nastavením ochrany dokumentů a přizpůsobovat úroveň zabezpečení vašich dokumentů aplikace Word. Odstranění ochrany dokumentu vám dává flexibilitu upravovat obsah dokumentu a formátování podle potřeby.

### Časté dotazy pro odstranění ochrany dokumentů v dokumentu aplikace Word

#### Otázka: Co je ochrana dokumentů v Aspose.Words pro .NET?

Odpověď: Ochrana dokumentů v Aspose.Words for .NET se týká funkce, která vám umožňuje aplikovat bezpečnostní opatření na dokument aplikace Word a omezit tak úpravy, formátování a úpravy obsahu. Pomáhá zajistit integritu a důvěrnost dokumentu.

#### Otázka: Jak mohu odstranit ochranu dokumentů pomocí Aspose.Words for .NET?

A: Chcete-li odstranit ochranu dokumentů pomocí Aspose.Words pro .NET, můžete postupovat takto:
1.  Vytvořte instanci souboru`Document` třída a a`DocumentBuilder` objekt.
2.  Použijte`DocumentBuilder` pro přidání obsahu do dokumentu.
3.  Zavolej`Unprotect` metoda`Document` objekt odstranit jakoukoli existující ochranu z dokumentu. To lze provést bez hesla nebo zadáním správného hesla.
4.  Uložte nechráněný dokument pomocí`Save` metoda`Document` objekt.

#### Otázka: Mohu odstranit ochranu z dokumentu aplikace Word bez hesla?

 Odpověď: Ano, můžete odstranit ochranu z dokumentu aplikace Word bez hesla pomocí Aspose.Words for .NET. Zavoláním na`Unprotect` metoda`Document`objektu bez zadání hesla, můžete odstranit ochranu z dokumentu, pokud byl dříve chráněn bez hesla.

#### Otázka: Jak mohu odstranit ochranu z dokumentu aplikace Word pomocí hesla?

 Odpověď: Chcete-li odstranit ochranu z dokumentu aplikace Word, který byl chráněn heslem, musíte při volání na číslo zadat správné heslo`Unprotect` metoda`Document` objekt. To zajišťuje, že pouze uživatelé se správným heslem mohou odstranit ochranu a přistupovat k dokumentu pro úpravy.

#### Otázka: Mohu z dokumentu aplikace Word odebrat konkrétní typy ochrany?

 Odpověď: Ano, pomocí Aspose.Words for .NET můžete selektivně odstranit konkrétní typy ochrany z dokumentu aplikace Word. Zavoláním na`Unprotect` metoda`Document` objektu, můžete odebrat požadovaný typ ochrany, jako je ochrana pouze pro čtení nebo ochrana formuláře, zatímco ostatní typy ochrany zůstanou nedotčené.