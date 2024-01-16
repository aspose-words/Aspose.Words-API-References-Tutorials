---
title: Odebrat omezení pouze pro čtení
linktitle: Odebrat omezení pouze pro čtení
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak odstranit omezení pouze pro čtení z dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/document-protection/remove-read-only-restriction/
---
tomto tutoriálu vás provedeme kroky k použití funkce odstranění omezení Aspose.Words for .NET pouze pro čtení. Tato funkce umožňuje odstranit omezení pouze pro čtení z dokumentu aplikace Word, aby jej bylo možné upravovat. Postupujte podle následujících kroků:

## Krok 1: Vytvoření dokumentu a nastavení ochrany

Začněte vytvořením instance třídy Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Nastavte heslo pro dokument pomocí vlastnosti SetPassword() objektu WriteProtection:

Nezapomeňte nahradit „MyPassword“ skutečným heslem, které jste použili k ochraně dokumentu.

## Krok 2: Odstraňte omezení pouze pro čtení

Chcete-li odstranit omezení pouze pro čtení, nastavte vlastnost ReadOnlyRecommended na false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Krok 3: Použijte neomezenou ochranu

Nakonec použijte neomezenou ochranu pomocí metody Protect() objektu dokumentu:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Nezapomeňte zadat správnou cestu a název souboru, aby se dokument uložil bez omezení pouze pro čtení.

### Příklad zdrojového kódu pro Remove Read Only Restriction pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro odstranění omezení pouze pro čtení pomocí Aspose.Words pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// Zadejte heslo dlouhé až 15 znaků.
doc.WriteProtection.SetPassword("MyPassword");

//Odeberte možnost pouze pro čtení.
doc.WriteProtection.ReadOnlyRecommended = false;

// Použijte ochranu proti zápisu bez ochrany.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Pomocí těchto kroků můžete snadno odstranit omezení pouze pro čtení z dokumentu aplikace Word pomocí Aspose.Words for .NET.


## Závěr

V tomto tutoriálu jsme se naučili, jak odstranit omezení pouze pro čtení z dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle uvedených kroků můžete omezení snadno odstranit a dokument znovu upravit. Aspose.Words for .NET nabízí komplexní sadu funkcí pro správu ochrany a omezení dokumentů a poskytuje vám flexibilitu a kontrolu nad zabezpečením a možnostmi úprav vašich dokumentů Word.

### FAQ

#### Otázka: Jaké je omezení pouze pro čtení v Aspose.Words pro .NET?

Odpověď: Omezení pouze pro čtení v Aspose.Words for .NET se týká funkce, která vám umožňuje nastavit dokument Word jako pouze pro čtení, což uživatelům brání v provádění jakýchkoli úprav obsahu nebo formátování. Toto omezení pomáhá chránit integritu dokumentu a zajišťuje, že nebude náhodně nebo úmyslně upraven.

#### Otázka: Jak mohu odstranit omezení pouze pro čtení pomocí Aspose.Words for .NET?

Odpověď: Chcete-li odstranit omezení pouze pro čtení z dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete postupovat takto:
1.  Vytvořte instanci souboru`Document` třídy a nastavte heslo pro dokument pomocí`SetPassword` metoda`WriteProtection` objekt.
2.  Nastav`ReadOnlyRecommended` vlastnictvím`WriteProtection` namítat proti`false` k odstranění doporučení pouze pro čtení.
3.  Aplikujte na dokument neomezenou ochranu pomocí`Protect` metoda`Document` objekt s`NoProtection` typ ochrany.
4.  Uložte dokument bez omezení pouze pro čtení pomocí`Save` metoda`Document` objekt.

#### Otázka: Mohu odstranit omezení pouze pro čtení z dokumentu aplikace Word bez hesla?

Odpověď: Ne, z dokumentu aplikace Word nemůžete odstranit omezení pouze pro čtení, aniž byste zadali správné heslo. Omezení pouze pro čtení je nastaveno z bezpečnostních důvodů a jeho odstranění bez hesla by podkopalo účel ochrany integrity dokumentu.

#### Otázka: Mohu odstranit omezení pouze pro čtení z dokumentu aplikace Word s nesprávným heslem?

Odpověď: Ne, nemůžete odstranit omezení pouze pro čtení z dokumentu aplikace Word s nesprávným heslem. Aby bylo možné odstranit omezení pouze pro čtení a bylo možné dokument znovu upravovat, musíte zadat správné heslo. Tím je zajištěno, že dokument mohou upravovat pouze oprávnění uživatelé se správným heslem.

#### Otázka: Je možné pomocí Aspose.Words for .NET odstranit jiné typy ochrany dokumentů?

Odpověď: Ano, Aspose.Words for .NET poskytuje různé metody k odstranění jiných typů ochrany dokumentů, jako je ochrana heslem, ochrana formuláře nebo omezení úprav dokumentů. V závislosti na typu ochrany použité na dokument můžete použít odpovídající metody a vlastnosti poskytované Aspose.Words k odstranění specifické ochrany a umožnění úpravy dokumentu.
