---
title: Nastavte verzi MS Word
linktitle: Nastavte verzi MS Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se načíst dokument se zadanou verzí MS Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-loadoptions/set-ms-word-version/
---
Při zpracování textu s dokumenty Word v aplikaci C# může být nutné určit verzi aplikace Microsoft Word, která se má použít při načítání dokumentu. S knihovnou Aspose.Words pro .NET můžete snadno nastavit, jakou verzi MS Word používat, pomocí LoadOptions. V tomto podrobném průvodci vás provedeme tím, jak používat zdrojový kód Aspose.Words for .NET C# k načtení dokumentu se zadanou verzí MS Word pomocí možností načítání LoadOptions.

## Porozumění knihovně Aspose.Words

Než se ponoříte do kódu, je důležité porozumět knihovně Aspose.Words pro .NET. Aspose.Words je výkonná knihovna pro vytváření, úpravu, převod a ochranu dokumentů aplikace Word na různých platformách včetně .NET. Nabízí mnoho funkcí pro manipulaci s dokumenty, jako je vkládání textu, změna formátování, přidávání oddílů a mnoho dalšího.

## Konfigurace možností načítání

Prvním krokem je konfigurace možností načítání pro náš dokument. Pomocí třídy LoadOptions zadejte parametry načítání. V našem případě musíme nastavit vlastnost MswVersion na požadovanou verzi MS Word. Například používáme verzi Microsoft Word 2010. Jak na to:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Vytvoříme nový objekt LoadOptions a nastavíme vlastnost MswVersion na MsWordVersion.Word2010 pro určení verze MS Word 2010.

## Načítání dokumentu se zadanou verzí MS Word

Nyní, když jsme nakonfigurovali možnosti načtení, můžeme načíst dokument pomocí třídy Dokument a určit možnosti načtení. Zde je příklad:

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

tomto příkladu načteme dokument "Document.docx" umístěný v adresáři dokumentů pomocí zadaných možností načtení.

### Příklad zdrojového kódu pro LoadOptions s funkcí "Nastavit verzi MS Word" pomocí Aspose.Words for .NET

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Nakonfigurujte možnosti načítání pomocí funkce "Nastavit verzi MS Word".
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Načtěte dokument se zadanou verzí MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Uložte dokument
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Závěr

V této příručce jsme vysvětlili, jak nahrát dokument specifikující konkrétní verzi MS Word pomocí knihovny Aspose.Words pro .NET. Podle uvedených kroků a pomocí poskytnutého zdroje kódu C# můžete tuto funkci snadno použít ve své aplikaci C#. Načtení dokumentu pomocí zadané verze MS Word vám umožní zajistit správnou kompatibilitu a zpracování dokumentu ve vaší aplikaci.


### FAQ

#### Otázka: Proč bych měl při načítání dokumentu v aplikaci C# specifikovat verzi MS Word?

Určení verze MS Word zajistí, že se dokument načte a zpracuje správně, zejména pokud se jedná o specifické formátování nebo funkce, které se mohou mezi různými verzemi lišit.

#### Otázka: Jaké verze MS Word podporuje Aspose.Words?

Odpověď: Aspose.Words for .NET podporuje různé verze MS Word, včetně Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 a další.

#### Otázka: Mohu načíst dokument s jinou verzí MS Word, než která je nainstalovaná v mém systému?

Odpověď: Ano, Aspose.Words vám umožňuje určit jinou verzi MS Word při načítání dokumentu, což zajišťuje kompatibilitu, i když má cílový systém jinou verzi MS Word.

#### Otázka: Jak nastavení verze MS Word prospěje mé aplikaci v jazyce C#?

Odpověď: Nastavení verze MS Word zajistí, že dokument bude zpracován v souladu se zamýšleným formátováním a funkcemi dané konkrétní verze a zajistí konzistentní výstup.

#### Otázka: Je Aspose.Words omezena na zpracování pouze dokumentů DOCX?

Odpověď: Ne, Aspose.Words podporuje různé formáty dokumentů, včetně DOC, RTF, HTML, PDF a dalších, což z něj činí všestranný nástroj pro práci s různými typy dokumentů.