---
title: Tučné písmo
linktitle: Tučné písmo
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se zvýraznit text tučným písmem pomocí Aspose.Words for .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/bold-text/
---

V tomto příkladu vám řekneme, jak zvýraznit tučný text pomocí Aspose.Words pro .NET. Tučný text jej zviditelní a zvýrazňuje.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Tučný text

 Nastavením tvůrce dokumentů můžeme text zvýraznit tučným písmem`Font.Bold`majetek do`true`.

```csharp
builder.Font.Bold = true;
```

## Krok 3: Přidejte obsah do dokumentu

 Nyní můžeme do dokumentu přidat obsah pomocí metod tvůrce dokumentů, jako je např`Writeln`, který přidá řádek textu.

```csharp
builder.Writeln("This text will be bold");
```

## Příklad zdrojového kódu pro tučný text pomocí Aspose.Words pro .NET


```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

// Udělejte text tučným písmem.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

gratuluji! Nyní jste se naučili, jak zvýraznit tučný text pomocí Aspose.Words pro .NET.


### FAQ

#### Otázka: Jak mohu v Aspose.Words nastavit tučný text?

 A: Chcete-li, aby byl text v Aspose.Words tučný, můžete použít`Font.Bold` majetek z`Run` objekt. Tuto vlastnost můžete nastavit na`true` na tučný konkrétní text. Můžete například použít`run.Font.Bold=true` zvýraznit text uvnitř`Run` objekt.

#### Otázka: Je možné zvýraznit několik částí textu ve stejném odstavci tučně?

 Odpověď: Ano, můžete použít tučné písmo více kusů textu v jednom odstavci pomocí více`Run` objektů. Můžete vytvořit více`Run` objekty a nastavte`Font.Bold`majetek do`true` pro každý objekt zvýraznit požadované části textu tučně. Poté je můžete přidat do odstavce pomocí`Paragraph.AppendChild(run)` metoda.

#### Otázka: Mohu zvýraznit tučný text, který je v tabulce nebo buňce v Aspose.Words?

 Odpověď: Ano, text v tabulce nebo buňce v Aspose.Words můžete zvýraznit tučným písmem. Pomocí vhodných metod můžete přejít na požadovanou buňku nebo odstavec a poté použít tučné formátování pomocí`Font.Bold` majetek z`Run` nebo`Paragraph` objekt.