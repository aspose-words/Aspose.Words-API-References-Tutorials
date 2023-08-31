---
title: Rimuovi proprietà documento personalizzate
linktitle: Rimuovi proprietà documento personalizzate
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per rimuovere proprietà personalizzate da un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-properties/remove-custom-document-properties/
---

In questo tutorial ti guideremo attraverso il codice sorgente C# per rimuovere le proprietà personalizzate da un documento con Aspose.Words per .NET. Questa funzionalità consente di rimuovere una proprietà personalizzata specifica da un documento.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurati che nel tuo progetto venga fatto riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio caricheremo il documento Word da cui vogliamo rimuovere le proprietà personalizzate. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: eliminazione delle proprietà personalizzate

Ora rimuoviamo una proprietà personalizzata specifica dal documento. Utilizza il seguente codice:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Questo codice rimuove la proprietà personalizzata "Data autorizzata" dal documento. Puoi sostituire "Data autorizzata" con il nome della proprietà personalizzata che desideri rimuovere.

### Codice sorgente di esempio per rimuovere le proprietà del documento personalizzato utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Assicurati di specificare il percorso corretto del documento nel file`dataDir` variabile.

Ora hai imparato come rimuovere le proprietà personalizzate da un documento utilizzando Aspose.Words per .NET. Seguendo la guida passo passo fornita in questo tutorial, puoi rimuovere facilmente le proprietà personalizzate dai tuoi documenti.