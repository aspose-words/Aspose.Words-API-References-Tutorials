---
title: Inserisci documento in unione posta
linktitle: Inserisci documento in unione posta
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire documenti nei campi di stampa unione utilizzando Aspose.Words per .NET in questo tutorial completo e dettagliato.
type: docs
weight: 10
url: /it/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## Introduzione

Benvenuti nel mondo dell'automazione dei documenti con Aspose.Words per .NET! Vi siete mai chiesti come inserire dinamicamente documenti in campi specifici all'interno di un documento principale durante un'operazione di unione di posta? Bene, siete nel posto giusto. Questo tutorial vi guiderà passo dopo passo attraverso il processo di inserimento di documenti nei campi di unione di posta utilizzando Aspose.Words per .NET. È come mettere insieme i pezzi di un puzzle, dove ogni pezzo va perfettamente al suo posto. Quindi, tuffiamoci!

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1.  Aspose.Words per .NET: puoi[scarica l'ultima versione qui](https://releases.aspose.com/words/net/) Se hai bisogno di acquistare una licenza, puoi farlo[Qui](https://purchase.aspose.com/buy) In alternativa, puoi ottenere un[licenza temporanea](https://purchase.aspose.com/temporary-license/) oppure provalo con un[prova gratuita](https://releases.aspose.com/).
2. Ambiente di sviluppo: Visual Studio o qualsiasi altro IDE C#.
3. Conoscenza di base di C#: la familiarità con la programmazione C# renderà questo tutorial un gioco da ragazzi.

## Importazione degli spazi dei nomi

Per prima cosa, dovrai importare i namespace necessari. Sono come i mattoni del tuo progetto.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

Scomponiamo il processo in passaggi gestibili. Ogni passaggio si baserà sul precedente, portandoti a una soluzione completa.

## Passaggio 1: impostazione della directory

Prima di poter iniziare a inserire documenti, devi definire il percorso della tua directory dei documenti. È qui che sono archiviati i tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Fase 2: Caricamento del documento principale

Successivamente, caricherai il documento principale. Questo documento contiene i campi di unione in cui verranno inseriti altri documenti.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## Passaggio 3: impostazione del callback di unione dei campi

Per gestire il processo di unione, dovrai impostare una funzione di callback. Questa funzione sarà responsabile dell'inserimento dei documenti nei campi di unione specificati.

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Fase 4: Esecuzione della stampa unione

Ora è il momento di eseguire la stampa unione. È qui che avviene la magia. Specificherai il campo di unione e il documento che deve essere inserito in questo campo.

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## Passaggio 5: salvataggio del documento

Una volta completata la stampa unione, salverai il documento modificato. Questo nuovo documento avrà il contenuto inserito esattamente dove lo desideri.

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## Passaggio 6: creazione del gestore di callback

Il gestore di callback è una classe che esegue un'elaborazione speciale per il campo di unione. Carica il documento specificato nel valore del campo e lo inserisce nel campo di unione corrente.

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

## Fase 7: Inserimento del documento

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

Ed ecco fatto! Hai inserito con successo documenti in campi specifici durante un'operazione di unione di posta usando Aspose.Words per .NET. Questa potente funzionalità può farti risparmiare un sacco di tempo e fatica, specialmente quando hai a che fare con grandi volumi di documenti. Immagina di avere un assistente personale che si occupa di tutto il lavoro pesante per te. Quindi, vai avanti e provalo. Buona codifica!

## Domande frequenti

### Posso inserire più documenti in campi di unione diversi?
Sì, puoi. Specifica semplicemente i campi di unione appropriati e i percorsi dei documenti corrispondenti nel`MailMerge.Execute` metodo.

### È possibile formattare il documento inserito in modo diverso dal documento principale?
 Assolutamente! Puoi usare il`ImportFormatMode` parametro nel`NodeImporter` per controllare la formattazione.

### Cosa succede se il nome del campo unione è dinamico?
È possibile gestire i nomi dei campi di unione dinamici passandoli come parametri al gestore di callback.

### Posso usare questo metodo con formati di file diversi?
Sì, Aspose.Words supporta vari formati di file, tra cui DOCX, PDF e altri.

### Come gestisco gli errori durante il processo di inserimento del documento?
Implementa la gestione degli errori nel gestore di callback per gestire eventuali eccezioni che potrebbero verificarsi.