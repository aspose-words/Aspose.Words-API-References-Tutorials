---
title: Odebrat obsah v dokumentu aplikace Word
linktitle: Odebrat obsah v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak odstranit obsah v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/remove-content/remove-table-of-contents/
---
V tomto tutoriálu vás provedeme tím, jak odstranit obsah v dokumentu aplikace Word pomocí knihovny Aspose.Words pro .NET. Obsah může být někdy nadbytečný nebo nepotřebný a tento kód vám pomůže jej efektivně odstranit. Poskytneme vám podrobného průvodce, který vám pomůže pochopit a implementovat kód ve vašem vlastním projektu .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words pro .NET nainstalovaná ve vašem projektu
- Dokument aplikace Word obsahující obsah, který chcete odstranit

## Krok 1: Definujte adresář dokumentů
 Nejprve musíte nastavit cestu k adresáři na umístění vašeho dokumentu aplikace Word. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s příslušnou cestou.

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Nahrajte dokument
 Dále načteme dokument aplikace Word do instance souboru`Document` třídy pomocí`Load` metoda.

```csharp
// Vložte dokument
Document doc = new Document(dataDir + "your-document.docx");
```

## Krok 3: Odstraňte obsah
 Abychom odstranili obsah, projdeme smyčkou typu TOC (table of content).`FieldStart` uzly v dokumentu. Tyto uzly uložíme, abychom k nim měli rychlý přístup a vytvořili seznam uzlů ke smazání.

```csharp
// Uložte FieldStart uzly TOC polí v dokumentu pro rychlý přístup.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Toto je seznam pro uložení uzlů nalezených uvnitř zadaného obsahu. Na konci této metody budou odstraněny.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Zkontrolujte, zda zadaný index TOC existuje.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Je bezpečnější tyto uzly uložit a na konci je všechny smazat.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Když narazíme na uzel FieldEnd typu FieldTOC,
     //víme, že jsme na konci aktuálního TOC a tady se zastavíme.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Ukázkový zdrojový kód pro Remove Table Of Contents pomocí Aspose.Words for .NET 
```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Vložte dokument
Document doc = new Document(dataDir + "your-document.docx");

// Uložte uzly FieldStart polí obsahu v dokumentu pro rychlý přístup.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Toto je seznam pro uložení uzlů nalezených uvnitř zadaného obsahu. Na konci této metody budou odstraněny.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Ujistěte se, že TOC určený předaným indexem existuje.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Je bezpečnější tyto uzly uložit a později je všechny najednou smazat.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Jakmile narazíme na uzel FieldEnd typu FieldTOC,
	// víme, že jsme na konci aktuálního obsahu a zastavíme se zde.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## Závěr
V tomto tutoriálu jsme představili podrobného průvodce odstraněním obsahu z dokumentu aplikace Word pomocí knihovny Aspose.Words pro .NET. Dodržováním poskytnutého kódu a pokynů můžete snadno odstranit obsah a zlepšit rozvržení dokumentu. Nezapomeňte upravit cestu k adresáři a názvy souborů tak, aby vyhovovaly vašim konkrétním potřebám.

### FAQ

#### Otázka: Proč bych měl používat Aspose.Words k odstranění obsahu v dokumentu aplikace Word?

A: Aspose.Words je výkonná a všestranná knihovna tříd pro manipulaci s dokumenty Wordu v aplikacích .NET. Pomocí Aspose.Words můžete efektivně odstranit obsah ze svých dokumentů, což může být užitečné, pokud je obsah nadbytečný nebo nepotřebný. To vám umožní přizpůsobit obsah dokumentu a zlepšit jeho celkovou prezentaci.

#### Otázka: Jak mohu nahrát dokument do Aspose.Words pro .NET?

Odpověď: Chcete-li odstranit obsah v dokumentu aplikace Word, musíte nejprve načíst dokument do paměti pomocí metody Load() Aspose.Words. Zde je ukázkový kód pro načtení dokumentu z konkrétního adresáře:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "your-document.docx");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k vašemu dokumentu.

#### Otázka: Jak odstraním obsah v dokumentu pomocí Aspose.Words?

 A: Chcete-li odstranit TOC, musíte iterovat přes`FieldStart` zadejte uzly obsahu v dokumentu. Tyto uzly můžete uložit pro rychlý přístup a vytvořit seznam uzlů, které chcete odstranit. Zde je ukázkový kód:

```csharp
// Uložte FieldStart uzly TOC polí v dokumentu pro rychlý přístup.
List<FieldStart> fieldStarts = new List<FieldStart>();
//Toto je seznam pro uložení uzlů nalezených uvnitř zadaného obsahu. Na konci této metody budou odstraněny.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Zkontrolujte, zda zadaný index obsahu existuje.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// Je bezpečnější tyto uzly uložit a na konci je všechny smazat.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Když narazíme na uzel FieldEnd typu FieldTOC,
//víme, že jsme na konci aktuálního TOC a tady se zastavíme.
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### Otázka: Jak uložit upravený dokument v Aspose.Words pro .NET?

Odpověď: Po odstranění obsahu musíte upravený dokument uložit pomocí metody Save(). Zadejte požadovanou cestu k výstupnímu souboru a formát (např. DOCX) pro upravovaný dokument. Zde je ukázkový kód:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```