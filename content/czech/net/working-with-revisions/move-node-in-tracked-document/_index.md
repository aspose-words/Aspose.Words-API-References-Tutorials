---
title: Přesunout uzel ve sledovaném dokumentu
linktitle: Přesunout uzel ve sledovaném dokumentu
second_title: Aspose.Words API pro zpracování dokumentů
description: Přesunout uzly ve sledovaném dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-revisions/move-node-in-tracked-document/
---

V tomto podrobném průvodci vás provedeme tím, jak přesunout uzel ve sledovaném dokumentu aplikace Word pomocí Aspose.Words for .NET. Poskytneme vám kompletní zdrojový kód a ukážeme vám, jak formátovat výstup markdown.

## Krok 1: Vytvoření dokumentu

Prvním krokem je vytvoření nového dokumentu a přidání odstavců.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Krok 2: Sledujte revize

V dokumentu povolíme sledování revizí.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Krok 3: Přesuňte uzel

Při generování revizí přesuneme uzel (odstavec) z jedné pozice na druhou.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Krok 4: Zastavte sledování recenzí

Přestaneme sledovat revize v dokumentu.

```csharp
doc.StopTrackRevisions();
```

## Krok 5: Uložení dokumentu

 Po vložení textového pole formuláře uložte dokument na požadované místo pomocí`Save` metoda. Ujistěte se, že jste zadali správnou cestu k souboru:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Příklad zdrojového kódu pro Move Node In Tracked Document pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro přesun uzlu ve sledovaném dokumentu pomocí Aspose.Words pro .NET:


```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Začněte sledovat revize.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Generujte revize při přesunu uzlu z jednoho umístění do druhého.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Zastavte proces sledování revizí.
doc.StopTrackRevisions();

// V rozsahu přesunu od jsou 3 další odstavce.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Závěr

V tomto tutoriálu jsme se naučili, jak přesunout uzel ve sledovaném dokumentu Word pomocí Aspose.Words for .NET. Sledováním kroků vytvoření dokumentu, povolení sledování revizí, přesunutí uzlu a zastavení sledování revizí jsme byli schopni tuto manipulaci úspěšně provést. Aspose.Words for .NET je výkonný nástroj pro zpracování textu s dokumenty aplikace Word a nabízí pokročilé funkce pro správu revizí. Nyní můžete tyto znalosti využít k přesunu uzlů ve vašich vlastních dokumentech aplikace Word při sledování revizí pomocí Aspose.Words for .NET.

### FAQ

#### Otázka: Jak mohu povolit sledování revizí v dokumentu Aspose.Words for .NET?

A: Chcete-li povolit sledování revizí v dokumentu Aspose.Words for .NET, můžete použít`StartTrackRevisions` metoda`Document` objekt. Tato metoda bere jako parametry jméno autora revizí a datum zahájení sledování revizí.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### Otázka: Jak mohu přesunout uzel ve sledovaném dokumentu bez generování revizí?

 Odpověď: Pokud chcete přesunout uzel ve sledovaném dokumentu bez generování revizí, můžete použít`Remove` a`InsertAfter` nebo`InsertBefore` metody`Node` objekt. Chcete-li například přesunout odstavec za jiným odstavcem, můžete použít následující kód:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### Otázka: Jak mohu zastavit sledování revizí v dokumentu Aspose.Words for .NET?

 Odpověď: Chcete-li zastavit sledování revizí v dokumentu Aspose.Words for .NET, můžete použít`StopTrackRevisions` metoda`Document` objekt.

```csharp
doc.StopTrackRevisions();
```