---
title: Skaffa variabler
linktitle: Skaffa variabler
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg guide för att hämta dokumentvariabler med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-properties/get-variables/
---

I den här handledningen går vi igenom C#-källkoden för att hämta variabler från ett dokument med Aspose.Words för .NET. Denna funktion låter dig komma åt variabler som definieras i ett dokument.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet från vilket vi vill hämta variablerna. Använd följande kod för att ladda dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Hämta variabler

Nu ska vi hämta de variabler som definierats i dokumentet. Använd följande kod:

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

Den här koden itererar över varje nyckel-värdepar i dokumentvariablerna och hämtar namnet och värdet på varje variabel. Variablerna sammanfogas sedan för att visa informationen för varje variabel.

### Exempel på källkod för Get Variables med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
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

 Var noga med att ange rätt dokumentsökväg i`dataDir` variabel.

Du har nu lärt dig hur du hämtar variabler från ett dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt komma åt och visa variabler från dina egna dokument.