---
title: Nekomprimujte malé metasoubory
linktitle: Nekomprimujte malé metasoubory
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat Aspose.Words for .NET k povolení funkce Nekomprimovat malé metasoubory při ukládání dokumentů.
type: docs
weight: 10
url: /cs/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

Komprese metadat v dokumentu je běžnou funkcí při zpracování textu se soubory v aplikaci C#. Může však být nutné nekomprimovat metadata malých souborů, aby byla zachována jejich kvalita. V tomto podrobném průvodci vám ukážeme, jak pomocí zdrojového kódu C# Aspose.Words for .NET povolit funkci „Nekomprimovat malé metasoubory“ v možnostech uložení dokumentu.

## Porozumění knihovně Aspose.Words

Než se ponoříte do kódu, je důležité porozumět knihovně Aspose.Words pro .NET. Aspose.Words je výkonná knihovna pro vytváření, úpravu, převod a ochranu dokumentů aplikace Word na různých platformách včetně .NET. Nabízí mnoho funkcí pro manipulaci s dokumenty, jako je vkládání textu, změna formátování, přidávání oddílů a mnoho dalšího.

## Krok 1: Nastavte adresář dokumentů

Prvním krokem je definování adresáře, kam chcete dokument uložit. Musíte zadat úplnou cestu k adresáři. Například :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 2: Vložte oddíly a text

Poté můžete do dokumentu vložit oddíly a text. K vytvoření obsahu dokumentu použijte třídu DocumentBuilder poskytovanou Aspose.Words. Zde je jednoduchý příklad:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

tomto příkladu vytvoříme nový prázdný dokument a poté pomocí DocumentBuilder přidáme řádek textu.

## Krok 3: Možnosti nastavení

'Registrace

Nyní nakonfigurujeme možnosti uložení pro náš dokument. Pomocí třídy DocSaveOptions zadejte nastavení uložení. Například :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

V tomto příkladu vytváříme nový objekt DocSaveOptions pro nastavení možností uložení.

## Krok 4: Povolte funkci „Nekomprimovat malé metasoubory“.

 Chcete-li povolit funkci "Nekomprimovat malé metasoubory", musíte nastavit`Compliance` vlastnost objektu DocSaveOptions na hodnotu`PdfCompliance.PdfA1a`. Zde je postup:

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

Tato konfigurace zajišťuje, že metadata malých souborů nebudou při ukládání dokumentu komprimována.

## Krok 5: Uložte dokument

Nakonec můžete dokument uložit pomocí`Save` metoda třídy Document. Zadejte úplnou cestu k souboru a požadovaný název souboru. Například :

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

Nezapomeňte nahradit "dataDir" cestou k adresáři dokumentů.

### Příklad zdrojového kódu pro DocSaveOptions s funkcí Nekomprimovat malé metasoubory pomocí Aspose.Words for .NET

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dvě sekce s nějakým textem.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Nakonfigurujte možnosti ukládání pomocí funkce „Nekomprimovat malé metasoubory“.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

// Uložte dokument se zadanými možnostmi
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## Závěr

V této příručce jsme vysvětlili, jak pomocí knihovny Aspose.Words pro .NET povolit funkci „Nekomprimovat malé metasoubory“ při ukládání dokumentu. Dodržováním uvedených kroků a použitím poskytnutého zdrojového kódu C# můžete tuto funkci snadno použít ve své aplikaci C#. Zachování nekomprimovaných metadat malých souborů může být důležité pro zachování kvality a integrity dokumentu.