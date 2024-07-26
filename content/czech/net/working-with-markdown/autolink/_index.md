---
title: Automatické propojení
linktitle: Automatické propojení
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vkládat automatické odkazy pomocí Aspose.Words for .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/autolink/
---

V tomto příkladu vysvětlíme, jak používat funkci "Autolink" s Aspose.Words pro .NET. Tato funkce umožňuje vkládat hypertextové odkazy do dokumentu automaticky.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Vložení hypertextového odkazu

 Můžeme vložit hypertextový odkaz pomocí`InsertHyperlink` metoda generátoru dokumentů. Určíme adresu URL a text, který se má odkazu zobrazit.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", nepravda);
```

## Krok 3: Vložení e-mailové adresy jako odkazu

Můžeme také vložit e-mailovou adresu jako odkaz pomocí předpony „mailto:“. To uživatelům umožní kliknutím na odkaz otevřít jejich výchozího e-mailového klienta.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Krok 4: Uložení dokumentu

Nakonec můžeme dokument uložit v požadovaném formátu.

### Příklad zdrojového kódu pro Autolink pomocí Aspose.Words pro .NET


```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

//Vložit hypertextový odkaz.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", nepravda);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


gratuluji! Nyní jste se naučili, jak používat funkci "Autolink" s Aspose.Words pro .NET.


### FAQ

#### Otázka: Jak mohu vytvořit automatický odkaz na URL adresu v Aspose.Words?

 A: Chcete-li vytvořit automatický odkaz na URL adresu v Aspose.Words, můžete použít`<a>` značka s`href` atribut obsahující adresu URL. Můžete například použít`<a href="https://www.aspose.com">https://www.aspose.com</a>` automaticky odkazovat na „https: //www.aspose.com“.

#### Otázka: Je možné upravit zobrazovaný text automatického odkazu v Aspose.Words?

 Odpověď: Ano, můžete upravit zobrazovaný text automatického odkazu v Aspose.Words. Místo použití adresy URL jako zobrazovaného textu můžete použít jakýkoli jiný text nahrazením obsahu mezi`<a>` značky. Můžete například použít`<a href="https://www.aspose.com">Click here</a>` pro zobrazení textu „Klikněte sem“ jako automatického odkazu.

#### Otázka: Jak mohu přidat další atributy k automatickému odkazu v Aspose.Words?

A: Chcete-li přidat další atributy k automatickému odkazu v Aspose.Words, můžete použít další atributy HTML uvnitř`<a>` štítek. Můžete například použít`<a href="https://www.aspose.com" target="_blank">Link</a>` pro otevření odkazu v novém okně nebo na kartě pomocí` attribute target="_blank"`.