---
title: Variabelen ophalen
linktitle: Variabelen ophalen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het ophalen van documentvariabelen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-properties/get-variables/
---

In deze zelfstudie leiden we u door de C#-broncode om variabelen op te halen uit een document met Aspose.Words voor .NET. Met deze functie hebt u toegang tot variabelen die in een document zijn gedefinieerd.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het Word-document waaruit we de variabelen willen ophalen. Gebruik de volgende code om het document te laden:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waar uw document zich bevindt.

## Stap 3: Variabelen ophalen

Nu gaan we de variabelen ophalen die in het document zijn gedefinieerd. Gebruik de volgende code:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

Deze code herhaalt elk sleutel-waardepaar in de documentvariabelen en haalt de naam en waarde van elke variabele op. De variabelen worden vervolgens samengevoegd om de informatie voor elke variabele weer te geven.

### Voorbeeldbroncode voor Get Variables met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 Zorg ervoor dat u het juiste documentpad opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u variabelen uit een document kunt ophalen met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u eenvoudig variabelen uit uw eigen documenten openen en bekijken.