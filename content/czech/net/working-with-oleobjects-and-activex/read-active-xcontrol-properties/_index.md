---
title: Číst vlastnosti Active XControl ze souboru aplikace Word
linktitle: Číst vlastnosti Active XControl ze souboru aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Číst vlastnosti ovládacích prvků ActiveX v souboru aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

tomto podrobném průvodci vám ukážeme, jak číst vlastnosti ovládacích prvků ActiveX v souboru aplikace Word pomocí Aspose.Words for .NET. Poskytneme vám kompletní zdrojový kód a ukážeme vám, jak formátovat výstup markdown.

## Krok 1: Inicializace dokumentu

 Prvním krokem je inicializace`Document` objekt načtením dokumentu aplikace Word obsahující ovládací prvky ActiveX. Nezapomeňte vyměnit`MyDir` se skutečnou cestou k adresáři obsahujícímu dokument.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Krok 2: Obnovte ovládací prvky ActiveX

 V tomto kroku projdeme každou z nich`Shape` dokumentu k načtení ovládacích prvků ActiveX a čtení jejich vlastností.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Příklad zdrojového kódu pro čtení Active XControl Properties pomocí Aspose.Words pro .NET

Zde je kompletní zdrojový kód pro čtení vlastností ovládacích prvků ActiveX pomocí Aspose.Words pro .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## Závěr

Tato příručka vám ukázala, jak číst vlastnosti ovládacích prvků ActiveX v souboru aplikace Word pomocí Aspose.Words for .NET. Podle popsaných kroků můžete inicializovat dokument, načíst ovládací prvky ActiveX a číst jejich vlastnosti. Jako výchozí bod použijte poskytnutý ukázkový kód a přizpůsobte jej svým konkrétním potřebám.

Čtení vlastností ovládacích prvků ActiveX umožňuje extrahovat důležité informace ze souborů aplikace Word obsahující tyto ovládací prvky. Aspose.Words for .NET nabízí výkonné funkce pro zpracování textu s ovládacími prvky ActiveX a automatizaci zpracování vašich dokumentů.

### Nejčastější dotazy

#### Otázka: Jaký je první krok ke čtení vlastností ovládacích prvků ActiveX v souboru aplikace Word?

 Odpověď: Prvním krokem je inicializace`Document` objekt načtením dokumentu aplikace Word obsahující ovládací prvky ActiveX. Nezapomeňte vyměnit`MyDir` se skutečnou cestou k adresáři obsahujícímu dokument.

#### Otázka: Jak dostanu ovládací prvky ActiveX do dokumentu?

 A: Chcete-li načíst ovládací prvky ActiveX, musíte každý z nich iterovat`Shape` dokumentu a zkontrolujte, zda se jedná o ovládací prvek ActiveX. Použijte`OleFormat` majetek`Shape` pro přístup k`OleControl` objekt a získat potřebné vlastnosti.

#### Otázka: Jaké vlastnosti ovládacích prvků ActiveX mohu číst?

Odpověď: Můžete číst různé vlastnosti ovládacích prvků ActiveX, jako je titulek, hodnota, stav povoleno nebo zakázáno, typ a podřízené uzly přidružené k ovládacímu prvku.

#### Otázka: Jak mohu získat celkový počet ovládacích prvků ActiveX v dokumentu?

 A: Chcete-li získat celkový počet ovládacích prvků ActiveX v dokumentu, můžete použít`GetChildNodes` metoda`Document` objekt určující`NodeType.Shape` typu a včetně podřízených uzlů.