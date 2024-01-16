---
title: Toon inhoud met bladwijzer verbergen in Word-document
linktitle: Toon inhoud met bladwijzer verbergen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u bladwijzerinhoud in een Word-document kunt weergeven of verbergen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

In dit artikel zullen we de bovenstaande C#-broncode verkennen om te begrijpen hoe u de functie Show Hide Bookmarked Content in de Aspose.Words voor .NET-bibliotheek kunt gebruiken. Met deze functie kunt u de inhoud van een bladwijzer in een Word-document weergeven of verbergen op basis van een specifieke voorwaarde bij het samenvoegen van gegevens.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: De bladwijzer ophalen

 Wij gebruiken de`Bookmarks` eigenschap van het documentbereik om de specifieke bladwijzer te krijgen waarop we de inhoud willen tonen of verbergen:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Stap 2: De samenvoegvelden invoegen

 Wij maken gebruik van een documentbuilder`DocumentBuilder` om de benodigde samenvoegvelden in te voegen. Deze samenvoegvelden stellen een voorwaarde in om de bladwijzerinhoud weer te geven of te verbergen, afhankelijk van de waarde van de`showHide` variabele:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Stap 3: Bladwijzerinhoud verplaatsen

We doorlopen de inhoud van de bladwijzer en verplaatsen deze zodat deze verschijnt

isse vóór de bladwijzer. Hiermee regel je het tonen of verbergen van inhoud op basis van de opgegeven voorwaarde:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## Stap 4: Verplaats de rest van de bladwijzerinhoud

We verplaatsen de rest van de bladwijzerinhoud na de bladwijzer, waarbij we het eindknooppunt van de bladwijzer als invoegpunt gebruiken:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## Stap 5: Het samenvoegen uitvoeren

 Wij gebruiken de`Execute` methode van het document`s `Mailmerge` object to execute the merge using the bookmark name and the value of the `showHide` variabele:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Voorbeeldbroncode voor Show Hide Bookmarked Content met Aspose.Words voor .NET

Hier is het volledige voorbeeld van broncode om het tonen of verbergen van bladwijzerinhoud aan te tonen met Aspose.Words voor .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD-bladwijzer}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de functie Show Hide Bookmarked Content van Aspose.Words voor .NET kunt gebruiken. We hebben een stapsgewijze handleiding gevolgd om de inhoud van een bladwijzer weer te geven of te verbergen op basis van een specifieke voorwaarde bij het samenvoegen van gegevens.

### Veelgestelde vragen over het weergeven en verbergen van bladwijzerinhoud in een Word-document

#### Vraag: Kan ik dezelfde voorwaarde gebruiken voor meerdere bladwijzers in hetzelfde document?

A: Ja, u kunt dezelfde voorwaarde gebruiken voor meerdere bladwijzers in hetzelfde document. Herhaal gewoon stap 2-5 voor elke bladwijzer, waarbij u de bladwijzernaam en optioneel de waarde van de bladwijzer aanpast`showhide` variabel als dat nodig is.

#### Vraag: Hoe kan ik meer voorwaarden toevoegen om bladwijzerinhoud weer te geven of te verbergen?

 A: Om meer voorwaarden toe te voegen, kunt u logische operatoren gebruiken, zoals`AND` En`OR` in de code voor het invoegen van de samenvoegvelden in stap 2. Bewerk de voorwaarde in de volgende code om aanvullende voorwaarden toe te voegen:

```csharp
builder. Write("\" = \"true\" ");
```

#### Vraag: Hoe kan ik een bladwijzer in een Word-document verwijderen met Aspose.Words voor .NET?

 A: Om een bladwijzer in een Word-document te verwijderen met Aspose.Words voor .NET, kunt u de`Remove` methode uit de`Bookmarks` verzameling van het documentbereik. Hier is voorbeeldcode voor het verwijderen van een specifieke bladwijzer:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### Vraag: Is de Aspose.Words-bibliotheek gratis?

 A: De Aspose.Words-bibliotheek is een commerciële bibliotheek en vereist een geldige licentie om in uw projecten te gebruiken. Je kunt controleren[Aspose.Words voor .NET API-referenties](https://reference.aspose.com/words/net/) voor meer informatie over licentieopties en prijzen.

#### Vraag: Zijn er andere bibliotheken beschikbaar voor tekstverwerking met Word-documenten in .NET?

A: Ja, er zijn andere bibliotheken beschikbaar voor woordenverwerking met Word-documenten in .NET, zoals Open XML SDK en GemBox.Document. U kunt deze bibliotheken verkennen als alternatief voor Aspose.Words op basis van uw specifieke behoeften en voorkeuren.