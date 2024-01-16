---
title: Verwijder de inhoudsopgave in een Word-document
linktitle: Verwijder de inhoudsopgave in een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de inhoudsopgave in een Word-document verwijdert met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/remove-content/remove-table-of-contents/
---
In deze zelfstudie laten we u zien hoe u de inhoudsopgave in een Word-document kunt verwijderen met behulp van de Aspose.Words-bibliotheek voor .NET. De inhoudsopgave kan soms overbodig of onnodig zijn, en deze code helpt u deze effectief te verwijderen. We bieden een stapsgewijze handleiding om u te helpen de code te begrijpen en te implementeren in uw eigen .NET-project.

## Vereisten
Zorg ervoor dat u over de volgende items beschikt voordat u begint:
- Een praktische kennis van de programmeertaal C#
- De Aspose.Words-bibliotheek voor .NET die in uw project is geïnstalleerd
- Een Word-document met een inhoudsopgave die u wilt verwijderen

## Stap 1: Definieer de documentmap
 Eerst moet u het mappad instellen op de locatie van uw Word-document. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het juiste pad.

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Upload het document
 Vervolgens laden we het Word-document in een exemplaar van het`Document` klas met behulp van de`Load` methode.

```csharp
// Laad het document
Document doc = new Document(dataDir + "your-document.docx");
```

## Stap 3: Verwijder de inhoudsopgave
 Om de inhoudsopgave te verwijderen, doorlopen we het TOC-type (inhoudsopgave).`FieldStart` knooppunten in het document. We slaan deze knooppunten op, zodat we er snel toegang toe hebben en een lijst kunnen maken met knooppunten die we moeten verwijderen.

```csharp
// Bewaar FieldStart-knooppunten van TOC-velden in het document voor snelle toegang.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Dit is een lijst waarin de knooppunten worden opgeslagen die binnen de opgegeven inhoudsopgave zijn gevonden. Ze worden aan het einde van deze methode verwijderd.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Controleer of de opgegeven TOC-index bestaat.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Het is veiliger om deze knooppunten op te slaan en ze uiteindelijk allemaal te verwijderen.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Wanneer we een FieldEnd-knooppunt van het type FieldTOC tegenkomen,
     //we weten dat we aan het einde van de huidige TOC zijn en we stoppen hier.
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


### Voorbeeldbroncode voor het verwijderen van de inhoudsopgave met Aspose.Words voor .NET 
```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Laad het document
Document doc = new Document(dataDir + "your-document.docx");

// Bewaar de FieldStart-knooppunten van TOC-velden in het document voor snelle toegang.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Dit is een lijst waarin de knooppunten worden opgeslagen die binnen de opgegeven inhoudsopgave zijn gevonden. Ze worden aan het einde van deze methode verwijderd.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Zorg ervoor dat de inhoudsopgave die door de doorgegeven index is opgegeven, bestaat.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Het is veiliger om deze knooppunten op te slaan en ze later allemaal in één keer te verwijderen.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Zodra we een FieldEnd-knooppunt van het type FieldTOC tegenkomen,
	// we weten dat we aan het einde van de huidige TOC zijn en stoppen hier.
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

## Conclusie
In deze zelfstudie presenteerden we een stapsgewijze handleiding voor het verwijderen van de inhoudsopgave uit een Word-document met behulp van de Aspose.Words-bibliotheek voor .NET. Door de meegeleverde code en instructies te volgen, kunt u eenvoudig de inhoudsopgave verwijderen en de lay-out van uw document verbeteren. Vergeet niet om het mappad en de bestandsnamen aan te passen aan uw specifieke behoeften.

### Veelgestelde vragen

#### Vraag: Waarom zou ik Aspose.Words gebruiken om de inhoudsopgave in een Word-document te verwijderen?

A: Aspose.Words is een krachtige en veelzijdige klassenbibliotheek voor het manipuleren van Word-documenten in .NET-toepassingen. Door Aspose.Words te gebruiken, kunt u de inhoudsopgave effectief uit uw documenten verwijderen, wat handig kan zijn als de inhoudsopgave overbodig of onnodig is. Hiermee kunt u de inhoud van uw document aanpassen en de algehele presentatie ervan verbeteren.

#### Vraag: Hoe upload ik een document in Aspose.Words voor .NET?

A: Om de inhoudsopgave uit een Word-document te verwijderen, moet u het document eerst in het geheugen laden met behulp van de Load()-methode van Aspose.Words. Hier is voorbeeldcode om een document uit een specifieke map te laden:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "your-document.docx");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad naar uw document.

#### Vraag: Hoe verwijder ik de inhoudsopgave van een document met Aspose.Words?

 A: Om de inhoudsopgave te verwijderen, moet u de`FieldStart` typ knooppunten van de inhoudsopgave in het document. U kunt deze knooppunten opslaan voor snelle toegang en een lijst met knooppunten maken die u wilt verwijderen. Hier is een voorbeeldcode:

```csharp
// Bewaar FieldStart-knooppunten van TOC-velden in het document voor snelle toegang.
List<FieldStart> fieldStarts = new List<FieldStart>();
//Dit is een lijst om knooppunten op te slaan die binnen de opgegeven inhoudsopgave zijn gevonden. Ze worden aan het einde van deze methode verwijderd.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Controleer of de opgegeven inhoudsopgave-index bestaat.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// Het is veiliger om deze knooppunten op te slaan en ze uiteindelijk allemaal te verwijderen.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Wanneer we een FieldEnd-knooppunt van het type FieldTOC tegenkomen,
//we weten dat we aan het einde van de huidige TOC zijn en we stoppen hier.
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

#### Vraag: Hoe kan ik een bewerkt document opslaan in Aspose.Words voor .NET?

A: Nadat u de inhoudsopgave hebt verwijderd, moet u het gewijzigde document opslaan met de Save()-methode. Specificeer het gewenste uitvoerbestandspad en de gewenste indeling (bijvoorbeeld DOCX) voor het bewerkte document. Hier is een voorbeeldcode:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```