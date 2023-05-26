---
title: Aggiungi proprietà documento personalizzate
linktitle: Aggiungi proprietà documento personalizzate
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida passo passo per aggiungere proprietà personalizzate a un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-properties/add-custom-document-properties/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per aggiungere proprietà personalizzate a un documento con Aspose.Words per .NET. Questa funzione consente di aggiungere informazioni personalizzate al documento.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento Word a cui vogliamo aggiungere proprietà personalizzate. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: aggiungi proprietà personalizzate

Ora aggiungiamo proprietà personalizzate al documento. Utilizzare il codice seguente per aggiungere le proprietà:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Questo codice controlla innanzitutto se la proprietà "Autorizzata" esiste già nelle proprietà personalizzate. Se esiste, il processo viene interrotto. In caso contrario, le proprietà personalizzate vengono aggiunte al documento.

### Esempio di codice sorgente per Aggiungi proprietà documento personalizzate utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Assicurarsi di specificare il percorso del documento corretto nel file`dataDir` variabile.

Ora hai imparato come aggiungere proprietà personalizzate a un documento utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi facilmente aggiungere le tue proprietà personalizzate ai tuoi documenti.