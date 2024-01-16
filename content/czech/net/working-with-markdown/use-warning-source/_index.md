---
title: Použijte zdroj varování
linktitle: Použijte zdroj varování
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat zdroj varování s Aspose.Words for .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/use-warning-source/
---

V tomto příkladu vám ukážeme, jak používat zdroj varování s Aspose.Words pro .NET. Zdroj varování udává původ varování při použití funkce zpětného volání.

## Krok 1: Načtení dokumentu

 Načteme existující dokument, který obsahuje varování pomocí`Load` metoda`Document` třída.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Krok 3: Použití zdroje varování

 Použijeme zdroj varování nastavením dokumentu`WarningCallback` majetku do sbírky`WarningInfo` objektů.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Krok 4: Uložení dokumentu

Nakonec můžeme dokument uložit v požadovaném formátu.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Příklad zdrojového kódu pro použití zdroje varování s Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

gratuluji! Nyní jste se naučili, jak používat zdroj varování s Aspose.Words pro .NET.

### FAQ

#### Otázka: Můžeme přizpůsobit vzhled štítku „Upozornění“?

 A: Formátování tagu "Warning" závisí na použitém vykreslovacím programu Markdown. Ve většině případů můžete upravit vzhled pomocí CSS k cílení`blockquote` tag ve vašem dokumentu.

#### Otázka: Je možné přidat ikony do štítku "Upozornění"?

Odpověď: Ano, je možné přidat ikony do tagu "Warning" pomocí HTML kódu ve vašem dokumentu Markdown. Můžete vložit a`span` tag s příslušnou třídou, aby se vedle textu upozornění zobrazila ikona.

#### Otázka: Je značka „Warning“ kompatibilní se všemi čtečkami Markdown?

 Odpověď: Kompatibilita značky „Warning“ závisí na použitém vykreslování Markdown. Většina čtenářů Markdown bude podporovat`blockquote` tag pro zobrazení zvýrazněného textu, ale přesný vzhled se může lišit.