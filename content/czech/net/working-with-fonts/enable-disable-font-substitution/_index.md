---
title: Povolit Zakázat nahrazování písem
linktitle: Povolit Zakázat nahrazování písem
second_title: Aspose.Words API pro zpracování dokumentů
description: tomto kurzu se dozvíte, jak povolit nebo zakázat nahrazování písem v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fonts/enable-disable-font-substitution/
---
V tomto tutoriálu vás provedeme tím, jak povolit nebo zakázat nahrazování písem v dokumentu aplikace Word při vykreslování pomocí knihovny Aspose.Words pro .NET. Povolení nebo zakázání nahrazování písem vám umožňuje řídit, zda budou chybějící písma automaticky nahrazena výchozím písmem. Provedeme vás krok za krokem, abychom vám pomohli pochopit a implementovat kód ve vašem projektu .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words pro .NET nainstalovaná ve vašem projektu
- Dokument aplikace Word, který chcete vykreslit s nebo bez nahrazení písem

## Krok 1: Definujte adresář dokumentů
 Nejprve musíte nastavit cestu k adresáři na umístění vašeho dokumentu aplikace Word. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s příslušnou cestou.

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Nahrajte dokument a nakonfigurujte nastavení písma
 Dále načteme dokument aplikace Word, který chcete vykreslit, a vytvoříme instanci souboru`FontSettings` třída pro zpracování nastavení písma. Výchozí přepsání písma nastavíme zadáním názvu písma v`DefaultFontName` a zakázat přepsání informací o písmech pomocí`Enabled` nastaven na`false`.

```csharp
// Vložte dokument
Document doc = new Document(dataDir + "Rendering.docx");

// Konfigurace nastavení písma
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Použijte nastavení písma na dokument
doc.FontSettings = fontSettings;
```

## Krok 3: Uložte vykreslený dokument
Nakonec uložíme vykreslený dokument, který bude respektovat definovaná nastavení přepisu písma.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Ukázkový zdrojový kód pro Enable Disable Font Substitution pomocí Aspose.Words for .NET 

```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Závěr
V tomto tutoriálu jsme viděli, jak povolit nebo zakázat nahrazování písem v dokumentu aplikace Word při vykreslování pomocí Aspose.Words for .NET. Řízením nahrazování písem můžete ovlivnit, jak bude ve vašich vykreslených dokumentech naloženo s chybějícími písmy. Neváhejte použít tuto funkci k přizpůsobení správy písem v dokumentech aplikace Word.

### FAQ

#### Otázka: Jak mohu povolit nahrazování písem v dokumentu aplikace Word pomocí Aspose.Words?

A: Chcete-li povolit nahrazování písem v dokumentu aplikace Word pomocí Aspose.Words, můžete použít rozhraní API k určení náhradních písem, která se mají použít, když požadovaná písma nejsou k dispozici. To zajistí konzistentní vizualizaci textu i bez původních písem.

#### Otázka: Je možné zakázat nahrazování písem v dokumentu aplikace Word pomocí Aspose.Words?

Odpověď: Ano, pomocí Aspose.Words můžete zakázat nahrazování písem v dokumentu aplikace Word. Pomocí rozhraní API můžete zabránit Wordu v nahrazení požadovaných písem jinými písmy, čímž se zachová původní vzhled textu.

#### Otázka: Co se stane, když během nahrazování v dokumentu aplikace Word chybí požadovaná písma?

Odpověď: Pokud během nahrazování v dokumentu aplikace Word chybí požadovaná písma, Aspose.Words dokáže tento problém detekovat a poskytnout vám možnosti, jak jej opravit. Můžete se rozhodnout nahradit chybějící písma alternativními písmy nebo zahrnout chybějící písma do dokumentu a zajistit tak správné zobrazení.

#### Otázka: Jak mohu vyřešit chybějící písma při nahrazování v dokumentu aplikace Word pomocí Aspose.Words?

Odpověď: Chcete-li vyřešit chybějící písma při nahrazování v dokumentu aplikace Word pomocí Aspose.Words, můžete použít rozhraní API ke zjištění chybějících písem a poskytnutí možností rozlišení. Můžete se rozhodnout nahradit chybějící písma alternativními písmy nebo zahrnout chybějící písma do dokumentu v závislosti na vašich potřebách.

#### Otázka: Je důležité řídit nahrazování písem v dokumentu aplikace Word?

Odpověď: Ano, je důležité řídit nahrazování písem v dokumentu aplikace Word, aby byla zachována vizuální integrita textu. Použitím Aspose.Words k povolení nebo zakázání nahrazování písem můžete zajistit použití požadovaných písem a vyhnout se problémům s chybějícími nebo nahrazenými písmy.