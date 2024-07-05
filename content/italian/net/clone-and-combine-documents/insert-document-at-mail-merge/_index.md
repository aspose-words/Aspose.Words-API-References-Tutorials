---
title: Inserisci documento nella stampa unione
linktitle: Inserisci documento nella stampa unione
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire documenti nei campi di stampa unione utilizzando Aspose.Words per .NET in questo tutorial completo e dettagliato.
type: docs
weight: 10
url: /it/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## introduzione

Benvenuti nel mondo dell'automazione dei documenti con Aspose.Words per .NET! Ti sei mai chiesto come inserire dinamicamente documenti in campi specifici all'interno di un documento principale durante un'operazione di stampa unione? Bene, sei nel posto giusto. Questo tutorial ti guiderà passo dopo passo attraverso il processo di inserimento di documenti nei campi di stampa unione utilizzando Aspose.Words per .NET. È come mettere insieme i pezzi di un puzzle, dove ogni pezzo va perfettamente al suo posto. Quindi tuffiamoci!

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1.  Aspose.Words per .NET: puoi[Scarica l'ultima versione qui](https://releases.aspose.com/words/net/) . Se devi acquistare una licenza, puoi farlo[Qui](https://purchase.aspose.com/buy) . In alternativa, puoi ottenere un[licenza temporanea](https://purchase.aspose.com/temporary-license/) oppure provalo con a[prova gratuita](https://releases.aspose.com/).
2. Ambiente di sviluppo: Visual Studio o qualsiasi altro IDE C#.
3. Conoscenza di base di C#: la familiarità con la programmazione C# renderà questo tutorial un gioco da ragazzi.

## Importa spazi dei nomi

Per prima cosa, dovrai importare gli spazi dei nomi necessari. Questi sono come gli elementi costitutivi del tuo progetto.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

Suddividiamo il processo in passaggi gestibili. Ogni passaggio si baserà su quello precedente, portandoti a una soluzione completa.

## Passaggio 1: configurazione della directory

Prima di iniziare a inserire i documenti, è necessario definire il percorso della directory dei documenti. Qui è dove vengono archiviati i tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricamento del documento principale

Successivamente, caricherai il documento principale. Questo documento contiene i campi di unione in cui verranno inseriti altri documenti.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## Passaggio 3: impostazione della richiamata di unione dei campi

Per gestire il processo di fusione, dovrai impostare una funzione di callback. Questa funzione sarà responsabile dell'inserimento dei documenti nei campi di unione specificati.

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Passaggio 4: esecuzione della stampa unione

Ora è il momento di eseguire la stampa unione. Qui è dove avviene la magia. Dovrai specificare il campo di unione e il documento da inserire in questo campo.

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## Passaggio 5: salvataggio del documento

Una volta completata la stampa unione, salverai il documento modificato. Questo nuovo documento avrà il contenuto inserito esattamente dove lo desideri.

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## Passaggio 6: creazione del gestore di richiamata

Il gestore di callback è una classe che effettua un'elaborazione speciale per il campo di unione. Carica il documento specificato nel valore del campo e lo inserisce nel campo di unione corrente.

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## Passaggio 7: inserimento del documento

Questo metodo inserisce il documento specificato nel paragrafo o nella cella della tabella corrente.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

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

## Conclusione

E il gioco è fatto! Hai inserito con successo documenti in campi specifici durante un'operazione di stampa unione utilizzando Aspose.Words per .NET. Questa potente funzionalità può farti risparmiare un sacco di tempo e fatica, soprattutto quando hai a che fare con grandi volumi di documenti. Consideralo come avere un assistente personale che si prende cura di tutto il lavoro pesante per te. Quindi, vai avanti e provalo. Buona programmazione!

## Domande frequenti

### Posso inserire più documenti in diversi campi di unione?
Si, puoi. È sufficiente specificare i campi di unione appropriati e i percorsi dei documenti corrispondenti nel file`MailMerge.Execute` metodo.

### È possibile formattare il documento inserito diversamente dal documento principale?
 Assolutamente! Puoi usare il`ImportFormatMode` parametro nel`NodeImporter` per controllare la formattazione.

### Cosa succede se il nome del campo di unione è dinamico?
È possibile gestire i nomi dei campi di unione dinamici passandoli come parametri al gestore di callback.

### Posso utilizzare questo metodo con formati di file diversi?
Sì, Aspose.Words supporta vari formati di file tra cui DOCX, PDF e altri.

### Come gestisco gli errori durante il processo di inserimento del documento?
Implementa la gestione degli errori nel gestore di callback per gestire eventuali eccezioni che potrebbero verificarsi.