---
title: Mostra Nascondi contenuto con segnalibro nel documento di Word
linktitle: Mostra Nascondi contenuto con segnalibro nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come mostrare e nascondere il contenuto con segnalibri nei documenti Word utilizzando Aspose.Words per .NET con questa guida dettagliata passo passo.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/show-hide-bookmarked-content/
---
## Introduzione

Pronti a tuffarvi nel mondo della manipolazione dei documenti con Aspose.Words per .NET? Che tu sia uno sviluppatore che desidera automatizzare le attività sui documenti o semplicemente qualcuno curioso di gestire i file di Word a livello di programmazione, sei nel posto giusto. Oggi esploreremo come mostrare e nascondere il contenuto con segnalibri in un documento Word utilizzando Aspose.Words per .NET. Questa guida passo passo ti renderà un professionista nel controllo della visibilità dei contenuti in base ai segnalibri. Iniziamo!

## Prerequisiti

Prima di passare al nocciolo della questione, ci sono alcune cose di cui avrai bisogno:

1. Visual Studio: qualsiasi versione compatibile con .NET.
2.  Aspose.Words per .NET: scaricalo[Qui](https://releases.aspose.com/words/net/).
3. Comprensione di base di C#: se riesci a scrivere un semplice programma "Hello World", sei a posto.
4. Un documento Word con segnalibri: utilizzeremo un documento di esempio con segnalibri per questo tutorial.

## Importa spazi dei nomi

Per prima cosa, importiamo gli spazi dei nomi necessari. Ciò garantisce che disponiamo di tutti gli strumenti necessari per il nostro compito.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

Con questi spazi dei nomi in atto, siamo pronti per iniziare il nostro viaggio.

## Passaggio 1: impostazione del progetto

Va bene, iniziamo configurando il nostro progetto in Visual Studio.

### Crea un nuovo progetto

Aprire Visual Studio e creare un nuovo progetto di app console (.NET Core). Chiamalo con qualcosa di accattivante, come "BookmarkVisibilityManager".

### Aggiungi Aspose.Words per .NET

Dovrai aggiungere Aspose.Words per .NET al tuo progetto. È possibile farlo tramite Gestione pacchetti NuGet.

1. Vai a Strumenti > Gestione pacchetti NuGet > Gestisci pacchetti NuGet per la soluzione.
2. Cerca "Aspose.Words".
3. Installa il pacchetto.

Grande! Ora che il nostro progetto è impostato, passiamo al caricamento del nostro documento.

## Passaggio 2: caricamento del documento

Dobbiamo caricare il documento Word che contiene i segnalibri. Per questo tutorial utilizzeremo un documento di esempio denominato "Bookmarks.docx".

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Questo frammento di codice imposta il percorso della directory dei documenti e carica il documento nel file`doc` oggetto.

## Passaggio 3: mostra/nascondi contenuto aggiunto ai segnalibri

Ora arriva la parte divertente: mostrare o nascondere il contenuto in base ai segnalibri. Creeremo un metodo chiamato`ShowHideBookmarkedContent` per gestire questa cosa.

Ecco il metodo che attiverà la visibilità dei contenuti aggiunti ai segnalibri:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    Node currentNode = bm.BookmarkStart;
    while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
    {
        if (currentNode.NodeType == NodeType.Run)
        {
            Run run = currentNode as Run;
            run.Font.Hidden = isHidden;
        }
        currentNode = currentNode.NextSibling;
    }
}
```

### Scomposizione del metodo

-  Recupero dei segnalibri:`Bookmark bm = doc.Range.Bookmarks[bookmarkName];` recupera il segnalibro.
- Attraversamento dei nodi: attraversiamo i nodi all'interno del segnalibro.
-  Attiva/disattiva visibilità: se il nodo è a`Run` (una sequenza di testo contigua), impostiamo its`Hidden` proprietà.

## Passaggio 4: applicazione del metodo

Con il nostro metodo in atto, applichiamolo per mostrare o nascondere il contenuto in base a un segnalibro.

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true);
```

Questa riga di codice nasconderà il contenuto del segnalibro denominato "MyBookmark1".

## Passaggio 5: salvataggio del documento

Infine, salviamo il nostro documento modificato.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

Ciò salva il documento con le modifiche che abbiamo apportato.

## Conclusione

Ed ecco qua! Hai appena imparato come mostrare e nascondere il contenuto con segnalibri in un documento Word utilizzando Aspose.Words per .NET. Questo potente strumento semplifica la manipolazione dei documenti, sia che tu stia automatizzando report, creando modelli o semplicemente armeggiando con file Word. Buona programmazione!

## Domande frequenti

### Posso attivare o disattivare più segnalibri contemporaneamente?
 Sì, puoi chiamare il`ShowHideBookmarkedContent` per ciascun segnalibro che desideri attivare/disattivare.

### Nascondere il contenuto influisce sulla struttura del documento?
No, nascondere il contenuto influisce solo sulla sua visibilità. Il contenuto rimane nel documento.

### Posso utilizzare questo metodo per altri tipi di contenuti?
Questo metodo attiva/disattiva specificamente le sequenze di testo. Per altri tipi di contenuto, dovrai modificare la logica di attraversamento del nodo.

### Aspose.Words per .NET è gratuito?
 Aspose.Words offre una prova gratuita[Qui](https://releases.aspose.com/) , ma per l'uso in produzione è necessaria una licenza completa. Puoi acquistarlo[Qui](https://purchase.aspose.com/buy).

### Come posso ottenere supporto se riscontro problemi?
 Puoi ottenere supporto dalla comunità Aspose[Qui](https://forum.aspose.com/c/words/8).