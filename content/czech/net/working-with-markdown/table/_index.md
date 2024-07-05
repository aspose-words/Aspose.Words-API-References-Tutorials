---
title: Stůl
linktitle: Stůl
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit tabulku pomocí Aspose.Words for .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/table/
---


V tomto příkladu vás provedeme vytvořením tabulky pomocí Aspose.Words for .NET. Tabulka je datová struktura, která organizuje informace do řádků a sloupců.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## Krok 2: Přidejte buňky a data

 Buňky a data přidáme do naší tabulky pomocí`InsertCell` metoda a`Writeln` metoda generátoru dokumentů.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### Příklad zdrojového kódu pro vytvoření tabulky pomocí Aspose.Words pro .NET

```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

// Přidejte první řádek.
builder.InsertCell();
builder.Writeln("a");
builder.InsertCell();
builder.Writeln("b");

// Přidejte druhou řadu.
builder.InsertCell();
builder.Writeln("c");
builder.InsertCell();
builder.Writeln("d");
```

gratuluji! Nyní jste se naučili, jak vytvořit tabulku pomocí Aspose.Words pro .NET.

### FAQ

#### Otázka: Jak vytvořím tabulku v Markdown?

A: Chcete-li vytvořit tabulku v Markdown, použijte syntaxi potrubí (`|`k oddělení buněk a pomlček (`-`) k vymezení záhlaví tabulky.

#### Otázka: Můžeme přizpůsobit vzhled stolu v Markdown?

Odpověď: Ve standardním Markdown jsou možnosti přizpůsobení tabulky omezené. Některé editory Markdown vám však umožňují přidávat styly CSS do tabulek a přizpůsobit tak jejich vzhled.

#### Otázka: Jak sloučit buňky v tabulce v Markdown?

Odpověď: Sloučení buněk v tabulce v Markdown závisí na použitém editoru Markdown. Některé editory Markdown podporují slučování buněk pomocí specifické syntaxe.

#### Otázka: Podporují tabulky v Markdown styly CSS?

Odpověď: Ve standardním Markdownu nenabízejí tabulky přímou podporu pro styly CSS. Některé editory Markdown vám však umožňují přidávat styly CSS do tabulek a přizpůsobit tak jejich vzhled.

#### Otázka: Můžeme přidat odkazy nebo text v inline formátu do buněk tabulky v Markdown?

Odpověď: Ano, do buněk tabulky v Markdown můžete přidat odkazy nebo vložený text pomocí příslušné syntaxe Markdown.