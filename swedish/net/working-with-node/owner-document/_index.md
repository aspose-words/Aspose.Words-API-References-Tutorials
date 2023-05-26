---
title: Ägardokument
linktitle: Ägardokument
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder ägardokumentet i Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-node/owner-document/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som illustrerar hur man använder proprietära dokumentfunktioner med Aspose.Words för .NET.

## Steg 1: Importera nödvändiga referenser
Innan du börjar, se till att du har importerat de nödvändiga referenserna för att använda Aspose.Words för .NET i ditt projekt. Detta inkluderar att importera Aspose.Words-biblioteket och lägga till de nödvändiga namnområdena till din källfil.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## Steg 2: Skapa ett nytt dokument
 I det här steget kommer vi att skapa ett nytt dokument med hjälp av`Document` klass.

```csharp
Document doc = new Document();
```

## Steg 3: Skapa en nod med ägardokumentet
 När du skapar en ny nod av någon typ måste du skicka dokumentet till konstruktorn. I det här exemplet skapar vi en ny styckenod med hjälp av dokumentet`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## Steg 4: Kontrollera överordnad nod och ägardokument
 Nu när vi har skapat styckenoden kan vi kontrollera om den har en överordnad nod och om det ägande dokumentet är detsamma som`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## Steg 5: Ändra nodegenskaper med dokumentdata
Relationen mellan en nod och ett dokument tillåter åtkomst och modifiering av egenskaper som refererar till dokumentspecifika data, såsom stilar eller listor. I det här exemplet ställer vi in styckeformatnamnet som "Rubrik 1".

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## Steg 6: Lägg till stycket i dokumentet
Nu kan vi lägga till styckenoden till huvuddelen av dokumentet.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Steg 7: Verifiera överordnad nod efter tillägg
Efter att ha lagt till stycket i dokumentet kontrollerar vi igen om det nu har en överordnad nod.

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### Exempel på källkod för ägardokument med Aspose.Words för .NET

```csharp
	Document doc = new Document();

	// Att skapa en ny nod av vilken typ som helst kräver att ett dokument skickas till konstruktorn.
	Paragraph para = new Paragraph(doc);

	// Den nya styckenoden har ännu ingen förälder.
	Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

	// Men paragrafnoden känner till sitt dokument.
	Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

	// Det faktum att en nod alltid tillhör ett dokument gör att vi kan komma åt och ändra
	// egenskaper som refererar till dokumentomfattande data, som stilar eller listor.
	para.ParagraphFormat.StyleName = "Heading 1";

	// Lägg nu till stycket i huvudtexten i det första avsnittet.
	doc.FirstSection.Body.AppendChild(para);

	//Paragrafnoden är nu ett underordnat till Body-noden.
	Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
            
```



