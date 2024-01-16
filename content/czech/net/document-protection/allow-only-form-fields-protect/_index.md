---
title: Povolit ochranu pouze polí formuláře v dokumentu aplikace Word
linktitle: Povolit ochranu pouze polí formuláře v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat Aspose.Words for .NET k ochraně v dokumentu aplikace Word a povolit pouze úpravy polí formuláře.
type: docs
weight: 10
url: /cs/net/document-protection/allow-only-form-fields-protect/
---
Ochrana dokumentů je základní funkcí při zpracování textu se soubory ve vaší aplikaci C#. S knihovnou Aspose.Words pro .NET můžete snadno chránit své dokumenty a povolit pouze úpravy polí formuláře. V tomto podrobném průvodci vás provedeme tím, jak používat zdrojový kód C#, aby bylo možné upravovat pouze pole formuláře pomocí funkce Povolit pouze ochranu polí formuláře Aspose.Words for .NET.

## Krok 1: Nastavení adresáře dokumentů

Prvním krokem je definovat adresář vašeho dokumentu. Musíte zadat cestu, kam chcete uložit chráněný dokument. Například :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 2: Vložení sekcí a textu

Dále musíte do dokumentu vložit oddíly a text. K vytvoření obsahu dokumentu použijte třídu DocumentBuilder poskytovanou Aspose.Words. Zde je jednoduchý příklad:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

tomto příkladu vytvoříme nový prázdný dokument a poté pomocí DocumentBuilder přidáme řádek textu.

## Krok 3: Povolení ochrany dokumentů

 Ochrana dokumentů funguje pouze tehdy, když je povolena ochrana dokumentů. Ochranu dokumentů můžete povolit pomocí`Protect` metoda třídy Document. Zde je postup:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

V tomto příkladu povolíme ochranu dokumentů zadáním typu ochrany `

AllowOnlyFormFields` a nastavení hesla.

## Krok 4: Povolení pouze polí formuláře

Nyní, když je povolena ochrana dokumentů, musíme určit, že jsou povoleny pouze úpravy polí formuláře. To zajišťuje, že uživatelé mohou upravovat pouze části dokumentu, které jsou poli formuláře. Zde je postup:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Nezapomeňte nahradit „heslo“ heslem, které jste nastavili dříve.

## Krok 5: Uložení chráněného dokumentu

 Nakonec můžete chráněný dokument uložit pomocí`Save` metoda třídy Document. Zadejte úplnou cestu k souboru a požadovaný název souboru. Například :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Nezapomeňte nahradit "dataDir" cestou k adresáři dokumentů.

### Příklad zdrojového kódu pro funkci Povolit pouze ochranu polí formuláře pomocí Aspose.Words for .NET

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vložte dvě sekce s nějakým textem.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Ochrana dokumentů funguje pouze v případě, že je ochrana dokumentů zapnutá a jsou povoleny pouze úpravy v polích formuláře.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Uložte chráněný dokument.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Závěr

V této příručce jsme prozkoumali, jak používat knihovnu Aspose.Words pro .NET k ochraně dokumentu a umožnit pouze úpravy polí formuláře. Podle uvedených kroků můžete tuto funkci snadno implementovat do své aplikace C#. Ochrana dokumentů je nezbytná pro zajištění bezpečnosti a důvěrnosti vašich dokumentů.

### Časté dotazy pro povolují ochranu pouze polí formuláře v dokumentu aplikace Word

#### Otázka: Co je ochrana dokumentů v Aspose.Words pro .NET?

A: Ochrana dokumentů v Aspose.Words for .NET je funkce, která vám umožňuje zabezpečit vaše dokumenty omezením určitých akcí, jako jsou úpravy, formátování nebo úpravy obsahu. Pomáhá udržovat integritu a důvěrnost vašich dokumentů tím, že zabraňuje neoprávněným změnám.

#### Otázka: Jak mohu chránit dokument a povolit úpravy pouze polí formuláře pomocí Aspose.Words for .NET?

Odpověď: Chcete-li chránit dokument a povolit úpravy pouze polí formuláře pomocí Aspose.Words for .NET, můžete postupovat takto:
1. Definujte cestu k adresáři pro váš dokument.
2.  Vložte oddíly a text do dokumentu pomocí`DocumentBuilder` třída.
3.  Povolte ochranu dokumentů pomocí`Protect` metoda`Document` třídy s uvedením typu ochrany jako`AllowOnlyFormFields` a poskytnutí hesla.
4.  Uložte chráněný dokument pomocí`Save` metoda`Document` třída.

#### Otázka: Mohu vložit pole formuláře do chráněného dokumentu pomocí Aspose.Words for .NET?

Odpověď: Ano, pole formuláře můžete vložit do chráněného dokumentu pomocí Aspose.Words for .NET. Ochrana dokumentů pomocí`AllowOnlyFormFields` typ umožňuje uživatelům upravovat pouze pole formuláře a zároveň chránit zbytek obsahu dokumentu. Můžete použít`DocumentBuilder` třídy pro vložení polí formuláře do dokumentu před povolením ochrany.

#### Otázka: Mohu odstranit ochranu dokumentu z chráněného dokumentu?

 Odpověď: Ano, můžete odstranit ochranu dokumentu z chráněného dokumentu pomocí Aspose.Words for .NET. Chcete-li odstranit ochranu, můžete použít`Unprotect` metoda`Document` třídy a zadejte správné heslo. Tím odstraníte ochranu a umožníte neomezené úpravy dokumentu.

#### Otázka: Je možné chránit dokument několika typy ochrany?

 Odpověď: Ne, Aspose.Words for .NET umožňuje použít na dokument vždy pouze jeden typ ochrany. Nicméně,`AllowOnlyFormFields` typ ochrany může účinně omezit úpravy na pole formuláře a zároveň povolit jiné typy ochrany, jako např`AllowOnlyComments` nebo`AllowOnlyRevisions`který má být kombinován s ochranou pole formuláře.

#### Otázka: Mohu v dokumentu nastavit různá hesla pro různé typy ochrany?

Odpověď: Ne, Aspose.Words for .NET vám umožňuje nastavit jedno heslo pro ochranu dokumentů bez ohledu na typ ochrany. Pro aktivaci a deaktivaci ochrany dokumentů bude použito stejné heslo.