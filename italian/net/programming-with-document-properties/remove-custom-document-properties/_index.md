---
title: Rimuovi proprietà documento personalizzate
linktitle: Rimuovi proprietà documento personalizzate
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per rimuovere le proprietà personalizzate da un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-properties/remove-custom-document-properties/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per rimuovere le proprietà personalizzate da un documento con Aspose.Words per .NET. Questa funzione consente di rimuovere una specifica proprietà personalizzata da un documento.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento Word da cui vogliamo rimuovere le proprietà personalizzate. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: eliminazione delle proprietà personalizzate

Ora rimuoviamo una specifica proprietà personalizzata dal documento. Usa il seguente codice:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Questo codice rimuove la proprietà personalizzata "Data di autorizzazione" dal documento. Puoi sostituire "Data di autorizzazione" con il nome della proprietà personalizzata che desideri rimuovere.

### Esempio di codice sorgente per Rimuovi proprietà documento personalizzate utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Assicurarsi di specificare il percorso del documento corretto nel file`dataDir` variabile.

Ora hai imparato come rimuovere le proprietà personalizzate da un documento utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi rimuovere facilmente le proprietà personalizzate dai tuoi documenti.