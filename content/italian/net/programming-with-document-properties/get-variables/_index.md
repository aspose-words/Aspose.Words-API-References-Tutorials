---
title: Ottieni variabili
linktitle: Ottieni variabili
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata per recuperare le variabili del documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-properties/get-variables/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per recuperare le variabili da un documento con Aspose.Words per .NET. Questa funzione consente di accedere alle variabili definite in un documento.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento Word da cui vogliamo recuperare le variabili. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: recupero delle variabili

Ora recupereremo le variabili definite nel documento. Usa il seguente codice:

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

Questo codice itera su ciascuna coppia chiave-valore nelle variabili del documento e recupera il nome e il valore di ciascuna variabile. Le variabili vengono quindi concatenate per visualizzare le informazioni per ogni variabile.

### Codice sorgente di esempio per ottenere variabili utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
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

 Assicurarsi di specificare il percorso del documento corretto nel file`dataDir` variabile.

Ora hai imparato come recuperare le variabili da un documento usando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi facilmente accedere e visualizzare le variabili dai tuoi documenti.