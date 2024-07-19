---
title: Converti metafile in Emf o Wmf
linktitle: Converti metafile in Emf o Wmf
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per convertire i metafile nei formati EMF o WMF durante la conversione di un documento in HTML con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---
## introduzione

Benvenuti in un altro tuffo nel mondo di Aspose.Words per .NET. Oggi affrontiamo un trucco interessante: convertire le immagini SVG nei formati EMF o WMF nei tuoi documenti Word. Potrebbe sembrare un po' tecnico, ma non preoccuparti. Alla fine di questo tutorial diventerai un professionista. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato con Aspose.Words per .NET, questa guida ti guiderà attraverso tutto ciò che devi sapere, passo dopo passo.

## Prerequisiti

Prima di immergerci nel codice, assicuriamoci di aver impostato tutto. Ecco cosa ti serve:

1. Aspose.Words per .NET Library: assicurati di avere la versione più recente. Se non ce l'hai, puoi scaricarlo da[Qui](https://releases.aspose.com/words/net/).
2. .NET Framework: assicurati di avere .NET Framework installato sul tuo computer.
3. Ambiente di sviluppo: un IDE come Visual Studio ti semplificherà la vita.
4. Conoscenza di base di C#: non è necessario essere un esperto, ma una conoscenza di base sarà utile.

Hai tutto? Grande! Iniziamo.

## Importa spazi dei nomi

Per prima cosa, dobbiamo importare gli spazi dei nomi necessari. Questo è fondamentale in quanto indica al nostro programma dove trovare le classi e i metodi che utilizzeremo.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Questi spazi dei nomi coprono tutto, dalle funzioni di sistema di base alle funzionalità specifiche di Aspose.Words di cui abbiamo bisogno per questo tutorial.

## Passaggio 1: imposta la directory dei documenti

Iniziamo definendo il percorso della directory dei documenti. Qui è dove verrà salvato il tuo documento Word dopo aver convertito i metafile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui desideri salvare il documento.

## Passaggio 2: crea la stringa HTML con SVG

Successivamente, abbiamo bisogno di una stringa HTML che contenga l'immagine SVG che vogliamo convertire. Ecco un semplice esempio:

```csharp
string html = 
    @"<html>
        <svg xmlns='http://www.w3.org/2000/svg' larghezza='500' altezza='40' viewBox='0 0 500 40'>
            <text x='0' y='35' font-family='Verdana' font-size='35'>Hello world!</text>
        </svg>
    </html>";
```

Questo snippet HTML include un SVG di base che dice "Hello world!".

## Passaggio 3: carica l'HTML con l'opzione ConvertSvgToEmf

 Ora usiamo il file`HtmlLoadOptions` per specificare come vogliamo gestire le immagini SVG nell'HTML. Collocamento`ConvertSvgToEmf` A`true` garantisce che le immagini SVG vengano convertite nel formato EMF.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { ConvertSvgToEmf = true };
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
```

 Questo frammento di codice crea un nuovo file`Document` oggetto caricandovi la stringa HTML con le opzioni di caricamento specificate.

## Passaggio 4: imposta HtmlSaveOptions per il formato metafile

 Per salvare il documento con il formato metafile corretto, utilizziamo`HtmlSaveOptions` . Ecco, ci siamo sistemati`MetafileFormat` A`HtmlMetafileFormat.Png` , ma puoi cambiarlo in`Emf` O`Wmf` a seconda delle vostre esigenze.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Png };
```

## Passaggio 5: salva il documento

Infine, salviamo il documento utilizzando le opzioni di salvataggio specificate.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToPng.html", saveOptions);
```

Ciò salva il documento nella directory specificata con il formato metafile convertito come definito.

## Conclusione

il gioco è fatto! Seguendo questi passaggi, hai convertito con successo le immagini SVG nei formati EMF o WMF nei tuoi documenti Word utilizzando Aspose.Words per .NET. Questo metodo è utile per garantire la compatibilità e mantenere l'integrità visiva dei tuoi documenti su piattaforme diverse. Buona programmazione!

## Domande frequenti

### Posso convertire altri formati di immagine utilizzando questo metodo?
Sì, puoi convertire vari formati di immagine regolando di conseguenza le opzioni di caricamento e salvataggio.

### È necessario utilizzare una versione specifica di .NET Framework?
Aspose.Words per .NET supporta più versioni di .NET Framework, ma è sempre una buona idea utilizzare la versione più recente per la migliore compatibilità e funzionalità.

### Qual è il vantaggio di convertire SVG in EMF o WMF?
La conversione di SVG in EMF o WMF garantisce che la grafica vettoriale venga preservata e renderizzata correttamente in ambienti che potrebbero non supportare completamente SVG.

### Posso automatizzare questo processo per più documenti?
Assolutamente! È possibile scorrere più file HTML, applicando lo stesso processo per automatizzare la conversione per l'elaborazione batch.

### Dove posso trovare ulteriori risorse e supporto per Aspose.Words per .NET?
 È possibile trovare una documentazione completa[Qui](https://reference.aspose.com/words/net/) e ottieni supporto dalla comunità Aspose[Qui](https://forum.aspose.com/c/words/8).