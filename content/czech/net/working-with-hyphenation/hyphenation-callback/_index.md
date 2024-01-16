---
title: Zpětné volání dělení slov
linktitle: Zpětné volání dělení slov
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat zpětné volání dělení slov v Aspose.Words pro .NET ke zpracování dělení slov.
type: docs
weight: 10
url: /cs/net/working-with-hyphenation/hyphenation-callback/
---

V tomto podrobném tutoriálu vám ukážeme, jak používat funkci zpětného volání dělení slov v Aspose.Words pro .NET. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů.

 Chcete-li začít, ujistěte se, že máte Aspose.Words for .NET nainstalovaný a nakonfigurovaný ve svém vývojovém prostředí. Pokud jste tak ještě neučinili, stáhněte si a nainstalujte knihovnu z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Uložte připomenutí dělení slov

 Nejprve zaregistrujeme zpětné volání dělení slov pomocí vlastního`CustomHyphenationCallback` třída. To nám umožní zacházet s dělením slov podle našich vlastních pravidel:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Ujistěte se, že jste implementovali`CustomHyphenationCallback` třídy podle vašich konkrétních potřeb.

## Krok 2: Načtení dokumentu a použití dělení slov

Dále načtěte dokument ze zadaného adresáře a rozdělte slova pomocí Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Krok 3: Zpracování chyb chybějících slovníků

případě, že chybí slovník dělení slov, zachytíme odpovídající výjimku a zobrazíme chybovou zprávu:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Krok 4: Vyčištění a zakázání připomenutí dělení slov

Nakonec pro čistotu a vypnutí připomenutí dělení slov proveďte následující kroky:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Tím se po dokončení zpracování vyčistí a zakáže připomenutí dělení slov.

Tak ! Úspěšně jste použili zpětné volání dělení slov v Aspose.Words pro .NET.

### Ukázkový zdrojový kód pro zpětné volání dělení slov s Aspose.Words pro .NET

```csharp
try
{
	 // Zaregistrujte zpětné volání dělení slov.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Neváhejte použít tento kód ve svých vlastních projektech a upravit jej tak, aby vyhovoval vašim konkrétním potřebám.

### FAQ

#### Otázka: Co je připomenutí sylabizace v Aspose.Words?

Odpověď: Připomenutí syllabization v Aspose.Words je funkce, která vám umožňuje přizpůsobit, jak jsou slova ve vašich dokumentech slabikována. Pomocí připomenutí slabikáře můžete určit vlastní pravidla pro slabikování slov, která mohou být užitečná pro konkrétní jazyky nebo konkrétní scénáře, kde výchozí slabikování nepřináší požadované výsledky.

#### Otázka: Jak nastavit připomenutí slabikáře v Aspose.Words?

 A: Chcete-li definovat zpětné volání dělení slov v Aspose.Words, musíte vytvořit třídu, která implementuje`HyphenationCallback` rozhraní a implementovat`HandleWord()` metoda. Tato metoda bude volána pro každé slovo, na které narazíte během slabikování. Můžete na něj použít vlastní pravidla slabikování a vrátit slabikované slovo. Potom můžete svázat zpětné volání dělení slov pomocí`Document.HyphenationCallback` vlastnost vašeho dokumentu.

#### Otázka: Jaká je výhoda použití připomenutí slabikáře v Aspose.Words?

Odpověď: Výhodou použití připomenutí slabikáře v Aspose.Words je možnost přizpůsobit, jak jsou slova ve vašich dokumentech slabikována. To vám dává větší kontrolu nad slabikováním, zejména pro konkrétní jazyky nebo scénáře, kde výchozí slabikování nedává požadované výsledky. Na každé slovo můžete použít specifická pravidla, abyste získali přesné slabikování podle svých potřeb.

#### Otázka: Jaké jsou některé běžné scénáře, kdy může být užitečné připomenutí slabikáře?

Odpověď: Použití zesilovače slabikáře může být užitečné v několika scénářích, například:
- Slabikování slov v konkrétních jazycích, které mají určitá pravidla slabikování.
- Aplikace personalizovaných pravidel slabikování pro akronymy nebo odborná slova.
- Úprava slabikování podle stylistických preferencí nebo typografických norem.

#### Otázka: Jak mohu v Aspose.Words otestovat vlastní slabikování pomocí připomenutí slabikáře?

 Odpověď: Chcete-li otestovat vlastní slabikování pomocí připomenutí slabikáře v Aspose.Words, můžete vytvořit testovací dokument obsahující slova, pro která chcete použít vlastní pravidla slabikování. Poté si můžete nastavit zpětné volání pro vlastní slabiku, zavolejte`Document.Range.Replace()` způsob, jak nahradit slova v dokumentu, a použít`Hyphenate()` metoda`Hyphenation` třídy získat slabikování slov . Slabiková slova pak můžete formátovat podle potřeby, například přidáním pomlček mezi slabiky.