---
title: Přerušit odkaz vpřed v dokumentu aplikace Word
linktitle: Přerušit odkaz vpřed v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak přerušit odkazy vpřed v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET je výkonná knihovna, která nabízí různé funkce pro zpracování textu s dokumenty Microsoft Word programově. Jednou z jeho užitečných funkcí je schopnost přerušit odkazy vpřed ve wordovém dokumentu. V tomto tutoriálu prozkoumáme zdrojový kód v C#, který demonstruje, jak přerušit dopředný odkaz v dokumentu aplikace Word pomocí Aspose.Words for .NET.

## Krok 1: Náhled zdrojového kódu C#

Poskytnutý zdrojový kód C# se zaměřuje na funkci "Break A Link" Aspose.Words for .NET. Ukazuje, jak přerušit odkaz ve tvaru textového pole uvnitř dokumentu. Kód představuje různé scénáře pro přerušení odkazů a poskytuje jasné pokyny, jak dosáhnout požadovaných výsledků.

## Krok 2: Nastavení dokumentu a vytvoření tvaru textového pole

 Chcete-li začít, musíme nastavit dokument a vytvořit tvar TextBox. Následující kód inicializuje novou instanci souboru`Document` třídy a vytvoří tvar textového pole:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Krok 3: Přerušit odkaz v textovém poli

 K přerušení dopředného odkazu v TextBoxu můžeme použít`BreakForwardLink()` metoda. Tato metoda přeruší vazbu na další obrazec v sekvenci. Následující kód ukazuje, jak přerušit dopředný odkaz:

```csharp
textBox.BreakForwardLink();
```

## Krok 4: Přerušte dopředný odkaz nastavením hodnoty null

 Případně můžeme přerušit dopředný odkaz nastavením textového pole`Next`majetek do`null`. Tím se efektivně odstraní napojení na další tvar. Následující kód demonstruje tento přístup:

```csharp
textBox. Next = null;
```

## Krok 5: Přerušte odkaz, který vede do textového pole

 V některých případech musíme přerušit odkaz, který vede k tvaru TextBox. Toho můžeme dosáhnout voláním`BreakForwardLink()` metoda na`Previous` formulář, který přeruší odkaz na TextBox. Zde je příklad, jak přerušit takový odkaz:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Ukázka zdrojového kódu pro přerušení spojení s Aspose.Words pro .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Přerušit odkaz.
textBox.BreakForwardLink();

// Přerušení dopředného odkazu nastavením hodnoty null.
textBox. Next = null;

// Přerušte odkaz, který vede do tohoto textového pole.
textBox.Previous?.BreakForwardLink();
```

## Závěr

gratuluji! Nyní jste se naučili, jak přerušit odkazy přesměrování v dokumentu aplikace Word pomocí knihovny Aspose.Words pro .NET. Podle kroků v této příručce jste byli schopni nastavit dokument, vytvořit tvar TextBox a přerušit přesměrování pomocí různých metod.

### Nejčastější dotazy pro odkaz vpřed v dokumentu aplikace Word

#### Otázka: Jaká knihovna se používá k přerušení odkazů přesměrování v dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Chcete-li přerušit odkazy přesměrování v dokumentu aplikace Word pomocí Aspose.Words pro .NET, použije se knihovna Aspose.Words for .NET.

#### Otázka: Jak přerušit přesměrování v textovém poli?

 A: Chcete-li přerušit odkaz vpřed v textovém poli, můžete použít`BreakForwardLink()` metoda. Tato metoda přeruší vazbu na další obrazec v sekvenci.

#### Otázka: Jak přerušit odkaz přesměrování nastavením hodnoty null?

A: Alternativně můžete odkaz přesměrování přerušit nastavením`Next` vlastnost TextBox to`null`. Tím se efektivně odstraní napojení na další tvar.

#### Otázka: Jak přerušit odkaz, který vede do textového pole?

 Odpověď: V některých případech musíte přerušit odkaz, který vede do TextBoxu. Toho můžete dosáhnout zavoláním na`BreakForwardLink()` metoda na`Previous` formulář, který přeruší odkaz na TextBox.

#### Otázka: Můžeme přerušit přesměrovací odkazy na jiné prvky než textová pole?

Odpověď: Ano, s Aspose.Words pro .NET je možné přerušit přesměrování na různé prvky, jako jsou odstavce, tabulky, obrázky atd. Proces se může lišit v závislosti na konkrétní položce, na kterou chcete odkaz přerušit.