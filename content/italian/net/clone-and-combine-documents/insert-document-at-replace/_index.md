---
title: Inserisci documento in Sostituisci
linktitle: Inserisci documento in Sostituisci
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire senza problemi un documento Word in un altro utilizzando Aspose.Words per .NET con la nostra guida dettagliata passo passo. Perfetto per gli sviluppatori che desiderano semplificare l'elaborazione dei documenti.
type: docs
weight: 10
url: /it/net/clone-and-combine-documents/insert-document-at-replace/
---
## introduzione

Ehi, maestri dei documenti! Ti sei mai trovato immerso nel codice, cercando di capire come inserire un documento Word in un altro senza problemi? Non temere, perché oggi ci tufferemo nel mondo di Aspose.Words per .NET per rendere questo compito un gioco da ragazzi. Esamineremo una guida dettagliata passo passo su come utilizzare questa potente libreria per inserire documenti in punti specifici durante un'operazione di ricerca e sostituzione. Pronto a diventare un mago di Aspose.Words? Iniziamo!

## Prerequisiti

Prima di addentrarci nel codice, ci sono alcune cose che devi avere a posto:

-  Visual Studio: assicurati di avere Visual Studio installato sul tuo computer. Se non lo hai ancora, puoi scaricarlo da[Qui](https://visualstudio.microsoft.com/).
-  Aspose.Words per .NET: avrai bisogno della libreria Aspose.Words. Puoi ottenerlo da[Sito web Aspose](https://releases.aspose.com/words/net/).
- Conoscenza di base di C#: una conoscenza di base di C# e .NET ti aiuterà a seguire questo tutorial.

Va bene, una volta tolti quelli, sporchiamoci le mani con un po' di codice!

## Importa spazi dei nomi

Per prima cosa, dobbiamo importare gli spazi dei nomi necessari per lavorare con Aspose.Words. È come raccogliere tutti gli strumenti prima di iniziare un progetto. Aggiungi queste direttive using nella parte superiore del file C#:

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

Ora che abbiamo i prerequisiti, suddividiamo il processo in piccoli passaggi. Ogni passo è cruciale e ci porterà più vicini al nostro obiettivo.

## Passaggio 1: impostazione della directory dei documenti

Innanzitutto, dobbiamo specificare la directory in cui sono archiviati i nostri documenti. È come allestire il palco prima della grande esibizione.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della tua directory. Qui è dove i tuoi documenti vivranno e respireranno.

## Passaggio 2: caricare il documento principale

Successivamente, carichiamo il documento principale in cui vogliamo inserire un altro documento. Pensa a questo come al nostro palcoscenico principale in cui si svolgerà tutta l'azione.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

Questo codice carica il documento principale dalla directory specificata.

## Passaggio 3: imposta le opzioni Trova e sostituisci

Per trovare la posizione specifica in cui vogliamo inserire il nostro documento, utilizziamo la funzionalità trova e sostituisci. È come usare una mappa per trovare il punto esatto della nostra nuova aggiunta.

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

Qui impostiamo la direzione su indietro e specifichiamo un gestore di callback personalizzato che definiremo successivamente.

## Passaggio 4: eseguire l'operazione di sostituzione

Ora diciamo al nostro documento principale di cercare un testo segnaposto specifico e di sostituirlo con nulla, mentre utilizziamo il nostro callback personalizzato per inserire un altro documento.

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

Questo codice esegue l'operazione di ricerca e sostituzione, quindi salva il documento aggiornato.

## Passaggio 5: creare un gestore di callback di sostituzione personalizzato

Il nostro gestore di richiamata personalizzato è il luogo in cui avviene la magia. Questo gestore definirà come verrà effettuato l'inserimento del documento durante l'operazione di ricerca e sostituzione.

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // Inserisci un documento dopo il paragrafo contenente il testo della corrispondenza.
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // Rimuovi il paragrafo con il testo della corrispondenza.
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

Qui carichiamo il documento da inserire e quindi chiamiamo un metodo helper per eseguire l'inserimento.

## Passaggio 6: definire il metodo di inserimento del documento

L'ultimo pezzo del nostro puzzle è il metodo che inserisce effettivamente il documento nella posizione specificata.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// Passa attraverso tutti i nodi a livello di blocco nel corpo della sezione,
		// quindi clona e inserisci ogni nodo che non sia l'ultimo paragrafo vuoto di una sezione.
		foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
		foreach (Node srcNode in srcSection.Body)
		{
			if (srcNode.NodeType == NodeType.Paragraph)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.IsEndOfSection && !para.HasChildNodes)
					continue;
			}

			Node newNode = importer.ImportNode(srcNode, true);

			destinationParent.InsertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new ArgumentException("The destination node should be either a paragraph or table.");
	}
}
```

Questo metodo si occupa di importare i nodi dal documento da inserire e di posizionarli nel punto giusto nel documento principale.

## Conclusione

E il gioco è fatto! Una guida completa per inserire un documento in un altro utilizzando Aspose.Words per .NET. Seguendo questi passaggi è possibile automatizzare facilmente le attività di assemblaggio e manipolazione dei documenti. Che tu stia costruendo un sistema di gestione dei documenti o semplicemente abbia bisogno di semplificare il flusso di lavoro di elaborazione dei documenti, Aspose.Words è il tuo fidato assistente.

## Domande frequenti

### Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una potente libreria per manipolare i documenti Word a livello di codice. Ti consente di creare, modificare, convertire ed elaborare documenti Word con facilità.

### Posso inserire più documenti contemporaneamente?
Sì, puoi modificare il gestore di callback per gestire più inserimenti eseguendo l'iterazione su una raccolta di documenti.

### È disponibile una prova gratuita?
 Assolutamente! È possibile scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).

### Come posso ottenere supporto per Aspose.Words?
Puoi ottenere supporto visitando il[Forum Aspose.Words](https://forum.aspose.com/c/words/8).

### Posso mantenere la formattazione del documento inserito?
 Sì, il`NodeImporter` La classe consente di specificare come viene gestita la formattazione durante l'importazione di nodi da un documento a un altro.