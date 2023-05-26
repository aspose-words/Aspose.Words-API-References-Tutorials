---
title: Da Doc a Docx
linktitle: Da Doc a Docx
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come convertire i documenti di Word dal formato .doc al formato Docx utilizzando Aspose.Words per .NET. Tutorial passo passo con codice sorgente di esempio.
type: docs
weight: 10
url: /it/net/basic-conversions/doc-to-docx/
---

In questo tutorial, ti guideremo attraverso il processo passo-passo dell'utilizzo di Aspose.Words per .NET per convertire un documento Word in formato .doc nel formato Docx. Spiegheremo il codice sorgente C# fornito e ti guideremo su come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: configurazione dell'ambiente di sviluppo

Prima di iniziare a programmare, assicurati di disporre di un ambiente di sviluppo adatto. Apri Visual Studio o il tuo IDE C# preferito e crea un nuovo progetto.

## Passaggio 2: aggiunta di riferimenti e importazione di spazi dei nomi

Per utilizzare Aspose.Words per .NET, è necessario aggiungere riferimenti alla libreria nel progetto. Fai clic con il pulsante destro del mouse sulla cartella Riferimenti nel tuo progetto, seleziona "Aggiungi riferimento" e vai alla posizione in cui hai installato la libreria Aspose.Words per .NET. Selezionare la versione appropriata e fare clic su "OK" per aggiungere il riferimento.

Successivamente, importa gli spazi dei nomi necessari nella parte superiore del file C#:

```csharp
using Aspose.Words;
```

## Passaggio 3: inizializzazione dell'oggetto documento

 In questo passaggio, inizializzerai il file`Document` oggetto con il percorso del documento di origine in formato .doc. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento e`"Document.doc"` con il nome del documento di origine. Ecco lo snippet di codice:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.doc");
```

## Passaggio 4: conversione del documento in formato Docx

 Ora che hai inizializzato il file`Document`oggetto, puoi procedere con il processo di conversione. Aspose.Words per .NET offre varie opzioni e impostazioni per la personalizzazione, ma per una conversione di base non sono richiesti parametri aggiuntivi.

## Passaggio 5: salvare il documento convertito

 Per salvare il documento convertito in formato Docx, è necessario chiamare il file`Save` metodo sul`Document` oggetto. Fornire il percorso e il nome del file per il documento di output. In questo esempio, lo salveremo come`"BaseConversions.DocToDocx.docx"`. Ecco lo snippet di codice:

```csharp
doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
```

Questo è tutto! Hai convertito con successo un documento Word in formato .doc nel formato Docx utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Doc To Docx utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.doc");

	doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
	
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.




