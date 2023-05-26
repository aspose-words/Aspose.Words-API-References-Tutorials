---
title: Enumera proprietà
linktitle: Enumera proprietà
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata all'enumerazione delle proprietà del documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-properties/enumerate-properties/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per enumerare le proprietà del documento con Aspose.Words per .NET. Questa funzione consente di accedere alle proprietà integrate e personalizzate di un documento.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento Word di cui vogliamo elencare le proprietà. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: enumerazione delle proprietà

Elenchiamo ora le proprietà del documento, sia predefinite che personalizzate. Usa il seguente codice:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Questo codice visualizza il nome del documento e quindi elenca le proprietà predefinite e personalizzate che ne mostrano il nome e il valore.

### Codice sorgente di esempio per Enumerate Properties utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Assicurarsi di specificare il percorso del documento corretto nel file`dataDir` variabile.

Ora hai imparato come enumerare le proprietà del documento usando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi facilmente accedere e visualizzare le proprietà dei tuoi documenti.

