---
title: Aggiungi prefisso nome classe CSS
linktitle: Aggiungi prefisso nome classe CSS
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere un prefisso del nome di classe CSS quando salvi documenti Word come HTML utilizzando Aspose.Words per .NET. Guida passo passo, frammenti di codice e domande frequenti incluse.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---
## Introduzione

Benvenuto! Se ti stai immergendo nel mondo di Aspose.Words per .NET, ti aspetta una sorpresa. Oggi esploreremo come aggiungere un prefisso del nome di una classe CSS quando si salva un documento Word come HTML utilizzando Aspose.Words per .NET. Questa funzione è molto utile quando vuoi evitare conflitti tra i nomi delle classi nei tuoi file HTML.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

-  Aspose.Words per .NET: se non l'hai ancora installato,[scaricalo qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: Visual Studio o qualsiasi altro IDE C#.
-  Un documento Word: utilizzeremo un documento denominato`Rendering.docx`. Inseriscilo nella directory del tuo progetto.

## Importa spazi dei nomi

Innanzitutto assicurati di aver importato gli spazi dei nomi necessari nel tuo progetto C#. Aggiungi questi nella parte superiore del file di codice:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

Ora tuffiamoci nella guida passo passo!

## Passaggio 1: imposta il tuo progetto

Prima di poter iniziare ad aggiungere il prefisso del nome di una classe CSS, impostiamo il nostro progetto.

### Passaggio 1.1: crea un nuovo progetto

 Avvia Visual Studio e crea un nuovo progetto di app console. Chiamalo con qualcosa di accattivante, ad esempio`AsposeCssPrefixExample`.

### Passaggio 1.2: aggiungere Aspose.Words per .NET

Se non lo hai già fatto, aggiungi Aspose.Words per .NET al tuo progetto tramite NuGet. È sufficiente aprire la console di gestione pacchetti NuGet ed eseguire:

```bash
Install-Package Aspose.Words
```

Grande! Ora siamo pronti per iniziare a scrivere codice.

## Passaggio 2: carica il documento

La prima cosa che dobbiamo fare è caricare il documento Word che vogliamo convertire in HTML.

### Passaggio 2.1: definire il percorso del documento

 Imposta il percorso della directory dei documenti. Per il bene di questo tutorial, supponiamo che il tuo documento sia in una cartella denominata`Documents` nella directory del tuo progetto.

```csharp
string dataDir = @"C:\YourProject\Documents\";
```

### Passaggio 2.2: caricare il documento

Ora carichiamo il documento utilizzando Aspose.Words:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: configura le opzioni di salvataggio HTML

Successivamente, dobbiamo configurare le opzioni di salvataggio HTML per includere un prefisso del nome della classe CSS.

### Passaggio 3.1: creazione delle opzioni di salvataggio HTML

 Istanziare il`HtmlSaveOptions` oggetto e impostare il tipo di foglio di stile CSS su`External`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External
};
```

### Passaggio 3.2: impostare il prefisso del nome della classe CSS

 Ora impostiamo il`CssClassNamePrefix` proprietà al prefisso desiderato. Per questo esempio useremo`"pfx_"`.

```csharp
saveOptions.CssClassNamePrefix = "pfx_";
```

## Passaggio 4: salva il documento come HTML

Infine, salviamo il documento come file HTML con le nostre opzioni configurate.


Specificare il percorso del file HTML di output e salvare il documento.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

## Passaggio 5: verificare l'output

 Dopo aver eseguito il progetto, vai al tuo`Documents` cartella. Dovresti trovare un file HTML denominato`WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html` . Apri questo file in un editor di testo o in un browser per verificare che le classi CSS abbiano il prefisso`pfx_`.

## Conclusione

Ed ecco qua! Seguendo questi passaggi, hai aggiunto con successo un prefisso del nome di classe CSS all'output HTML utilizzando Aspose.Words per .NET. Questa funzionalità semplice ma potente può aiutarti a mantenere stili puliti e privi di conflitti nei tuoi documenti HTML.

## Domande frequenti

### Posso utilizzare un prefisso diverso per ciascuna operazione di salvataggio?
 Sì, puoi personalizzare il prefisso ogni volta che salvi un documento modificando il file`CssClassNamePrefix` proprietà.

### Questo metodo supporta i CSS in linea?
 IL`CssClassNamePrefix`la proprietà funziona con CSS esterni. Per i CSS in linea, avrai bisogno di un approccio diverso.

### Come posso includere altre opzioni di salvataggio HTML?
 È possibile configurare varie proprietà di`HtmlSaveOptions` per personalizzare l'output HTML. Controlla il[documentazione](https://reference.aspose.com/words/net/) per maggiori dettagli

### È possibile salvare l'HTML in uno stream?
 Assolutamente! È possibile salvare il documento in uno stream passando l'oggetto stream al file`Save` metodo.

### Come posso ottenere supporto se riscontro problemi?
 Puoi ottenere supporto da[Aspose forum](https://forum.aspose.com/c/words/8).