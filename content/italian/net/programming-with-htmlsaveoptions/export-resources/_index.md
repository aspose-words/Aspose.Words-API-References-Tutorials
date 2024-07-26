---
title: Esporta risorse
linktitle: Esporta risorse
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come esportare risorse come CSS e caratteri salvando documenti Word come HTML utilizzando Aspose.Words per .NET. Segui la nostra guida passo passo.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/export-resources/
---
## introduzione

Ehi, amico appassionato di tecnologia! Se ti è mai capitato di dover convertire documenti Word in HTML, sei nel posto giusto. Oggi ci immergiamo nel meraviglioso mondo di Aspose.Words per .NET. Questa potente libreria semplifica il lavoro con i documenti Word a livello di codice. In questo tutorial, esamineremo i passaggi per esportare risorse, come caratteri e CSS, quando salvi un documento Word come HTML utilizzando Aspose.Words per .NET. Allacciate le cinture per un giro divertente e informativo!

## Prerequisiti

Prima di immergerci nel codice, assicuriamoci di avere tutto il necessario per iniziare. Ecco una rapida lista di controllo:

1.  Visual Studio: assicurati di avere Visual Studio installato sul tuo computer. Puoi scaricarlo da[Sito Web di Visual Studio](https://visualstudio.microsoft.com/).
2.  Aspose.Words per .NET: avrai bisogno della libreria Aspose.Words per .NET. Se non l'hai ancora ricevuto, ottieni una prova gratuita da[Rilasci Aspose](https://releases.aspose.com/words/net/) oppure acquistalo da[Aspose Store](https://purchase.aspose.com/buy).
3. Conoscenza di base di C#: una conoscenza fondamentale di C# ti aiuterà a seguire gli esempi di codice.

Capito tutto? Grande! Passiamo all'importazione degli spazi dei nomi necessari.

## Importa spazi dei nomi

Per utilizzare Aspose.Words per .NET, è necessario includere gli spazi dei nomi pertinenti nel progetto. Ecco come farlo:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Questi spazi dei nomi sono cruciali per accedere alle classi e ai metodi Aspose.Words che utilizzeremo nel nostro tutorial.

Analizziamo il processo di esportazione delle risorse quando si salva un documento Word come HTML. Lo faremo passo dopo passo, quindi è facile da seguire.

## Passaggio 1: imposta la directory dei documenti

Per prima cosa, devi specificare il percorso della directory dei tuoi documenti. Qui è dove si trova il tuo documento Word e dove verrà salvato il file HTML.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory.

## Passaggio 2: caricare il documento Word

 Successivamente, carichiamo il documento Word che desideri convertire in HTML. Per questo tutorial utilizzeremo un documento denominato`Rendering.docx`.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Questa riga di codice carica il documento dalla directory specificata.

## Passaggio 3: configura le opzioni di salvataggio HTML

Per esportare risorse come CSS e caratteri, è necessario configurare il file`HtmlSaveOptions`. Questo passaggio è fondamentale per garantire che l'output HTML sia ben strutturato e includa le risorse necessarie.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ResourceFolder = dataDir + "Resources",
    ResourceFolderAlias = "http://esempio.com/resources"
};
```

Analizziamo cosa fa ciascuna opzione:
- `CssStyleSheetType = CssStyleSheetType.External`: questa opzione specifica che gli stili CSS devono essere salvati in un foglio di stile esterno.
- `ExportFontResources = true`: consente l'esportazione delle risorse dei caratteri.
- `ResourceFolder = dataDir + "Resources"`: specifica la cartella locale in cui verranno salvate le risorse (come caratteri e file CSS).
- `ResourceFolderAlias = "http://example.com/resources"`: imposta un alias per la cartella delle risorse, che verrà utilizzato nel file HTML.

## Passaggio 4: salva il documento come HTML

Con le opzioni di salvataggio configurate, il passaggio finale è salvare il documento come file HTML. Ecco come farlo:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Questa riga di codice salva il documento in formato HTML, insieme alle risorse esportate.

## Conclusione

il gioco è fatto! Hai esportato con successo risorse durante il salvataggio di un documento Word come HTML utilizzando Aspose.Words per .NET. Con questa potente libreria, gestire i documenti Word a livello di codice diventa un gioco da ragazzi. Che tu stia lavorando su un'applicazione Web o abbia semplicemente bisogno di convertire documenti per l'utilizzo offline, Aspose.Words ti copre.

## Domande frequenti

### Posso esportare immagini insieme a caratteri e CSS?
 Si, puoi! Aspose.Words per .NET supporta anche l'esportazione di immagini. Assicurati solo di configurare il file`HtmlSaveOptions` di conseguenza.

### C'è un modo per incorporare CSS invece di utilizzare un foglio di stile esterno?
 Assolutamente. Puoi impostare`CssStyleSheetType` A`CssStyleSheetType.Embedded` se preferisci gli stili incorporati.

### Come posso personalizzare il nome del file HTML di output?
 Puoi specificare qualsiasi nome di file che preferisci nel file`doc.Save` metodo. Per esempio,`doc.Save(dataDir + "CustomFileName.html", saveOptions);`.

### Aspose.Words supporta altri formati oltre all'HTML?
 Sì, supporta vari formati tra cui PDF, DOCX, TXT e altri. Dai un'occhiata a[documentazione](https://reference.aspose.com/words/net/) per un elenco completo.

### Dove posso ottenere ulteriore supporto e risorse?
Per ulteriore assistenza, visitare il[Forum di supporto di Aspose.Words](https://forum.aspose.com/c/words/8) . È inoltre possibile trovare documentazione dettagliata ed esempi su[Sito web Aspose](https://reference.aspose.com/words/net/).