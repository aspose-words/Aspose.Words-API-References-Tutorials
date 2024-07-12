---
title: Převod mezi měrnými jednotkami
linktitle: Převod mezi měrnými jednotkami
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce převodem mezi měrnými jednotkami v dokumentu pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-properties/convert-between-measurement-units/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro převod mezi měrnými jednotkami pomocí Aspose.Words for .NET. Tato funkce umožňuje zadat okraje, vzdálenosti záhlaví a zápatí atd. v různých měrných jednotkách.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Vytvoření dokumentu a konstruktoru

V tomto kroku vytvoříme nový dokument a inicializujeme konstruktor. Použijte následující kód:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Nakonfigurujte měrné jednotky

Nyní převedeme hodnoty pro okraje, vzdálenosti záhlaví a zápatí atd. v různých měrných jednotkách. Pomocí následujícího kódu zadejte hodnoty v konkrétních měrných jednotkách:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Tento kód používá`ConvertUtil` třídy Aspose.Words pro převod zadaných hodnot na palce (`InchToPoint`). Můžete také použít jiné metody převodu dostupné v`ConvertUtil` třídy pro převod hodnot na jiné měrné jednotky.

### Příklad zdrojového kódu pro Convert Between Measurement Units pomocí Aspose.Words for .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Nyní jste se naučili, jak převádět mezi měrnými jednotkami při zadávání okrajů, vzdáleností záhlaví a zápatí atd. v dokumentu pomocí Aspose.Words for .NET. Podle podrobného průvodce poskytnutého v tomto tutoriálu můžete snadno zadat hodnoty v požadovaných měrných jednotkách ve svých vlastních dokumentech.