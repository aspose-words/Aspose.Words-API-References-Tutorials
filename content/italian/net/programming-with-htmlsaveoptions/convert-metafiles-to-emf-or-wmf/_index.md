---
title: Convertire i metafile in Emf o Wmf
linktitle: Convertire i metafile in Emf o Wmf
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per convertire i metafile nei formati EMF o WMF durante la conversione di un documento in HTML con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---
## Introduzione

Benvenuti a un altro tuffo nel mondo di Aspose.Words per .NET. Oggi affronteremo un trucco ingegnoso: convertire le immagini SVG in formati EMF o WMF nei documenti Word. Potrebbe sembrare un po' tecnico, ma non preoccupatevi. Alla fine di questo tutorial, sarete dei professionisti. Che siate sviluppatori esperti o che abbiate appena iniziato con Aspose.Words per .NET, questa guida vi guiderà passo dopo passo attraverso tutto ciò che dovete sapere.

## Prerequisiti

Prima di immergerci nel codice, assicuriamoci di aver impostato tutto. Ecco cosa ti serve:

1.  Aspose.Words per la libreria .NET: assicurati di avere la versione più recente. Se non ce l'hai, puoi scaricarla da[Qui](https://releases.aspose.com/words/net/).
2. .NET Framework: assicurati che .NET Framework sia installato sul tuo computer.
3. Ambiente di sviluppo: un IDE come Visual Studio ti semplificherà la vita.
4. Conoscenza di base di C#: non è necessario essere un esperto, ma una conoscenza di base sarà utile.

Hai capito tutto? Ottimo! Cominciamo.

## Importazione degli spazi dei nomi

Prima di tutto, dobbiamo importare i namespace necessari. Questo è fondamentale perché indica al nostro programma dove trovare le classi e i metodi che utilizzeremo.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Questi namespace coprono tutto, dalle funzioni di sistema di base alla funzionalità specifica di Aspose.Words di cui abbiamo bisogno per questo tutorial.

## Passaggio 1: imposta la directory dei documenti

Iniziamo definendo il percorso della directory dei tuoi documenti. È qui che il tuo documento Word verrà salvato dopo aver convertito i metafile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui desideri salvare il documento.

## Passaggio 2: creare la stringa HTML con SVG

Poi, abbiamo bisogno di una stringa HTML che contenga l'immagine SVG che vogliamo convertire. Ecco un semplice esempio:

```csharp
string html = 
    @"<html>
        <svg xmlns='http://www.w3.org/2000/svg' width='500' height='40' viewBox='0 0 500 40'>
            <text x='0' y='35' font-family='Verdana' font-size='35'>Hello world!</text>
        </svg>
    </html>";
```

Questo frammento HTML include un SVG di base che dice "Hello world!".

## Passaggio 3: caricare HTML con l'opzione ConvertSvgToEmf

 Adesso usiamo il`HtmlLoadOptions` per specificare come vogliamo gestire le immagini SVG nell'HTML. Impostazione`ConvertSvgToEmf` A`true` assicura che le immagini SVG vengano convertite nel formato EMF.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { ConvertSvgToEmf = true };
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
```

 Questo frammento di codice crea un nuovo`Document` oggetto caricando al suo interno la stringa HTML con le opzioni di caricamento specificate.

## Passaggio 4: impostare HtmlSaveOptions per il formato Metafile

 Per salvare il documento con il formato metafile corretto, utilizziamo`HtmlSaveOptions` Qui, abbiamo impostato`MetafileFormat` A`HtmlMetafileFormat.Png` , ma puoi cambiarlo in`Emf` O`Wmf` a seconda delle vostre esigenze.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Png };
```

## Passaggio 5: Salvare il documento

Infine, salviamo il documento utilizzando le opzioni di salvataggio specificate.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToPng.html", saveOptions);
```

In questo modo il documento viene salvato nella directory specificata con il formato metafile convertito come definito.

## Conclusione

Ed ecco fatto! Seguendo questi passaggi, hai convertito con successo le immagini SVG in formati EMF o WMF nei tuoi documenti Word usando Aspose.Words per .NET. Questo metodo è utile per garantire la compatibilità e mantenere l'integrità visiva dei tuoi documenti su diverse piattaforme. Buona codifica!

## Domande frequenti

### Posso convertire altri formati di immagine utilizzando questo metodo?
Sì, puoi convertire vari formati di immagine regolando di conseguenza le opzioni di caricamento e salvataggio.

### È necessario utilizzare una versione specifica di .NET Framework?
Aspose.Words per .NET supporta più versioni di .NET Framework, ma è sempre una buona idea utilizzare la versione più recente per ottenere la migliore compatibilità e le migliori funzionalità.

### Qual è il vantaggio di convertire SVG in EMF o WMF?
La conversione da SVG a EMF o WMF garantisce che la grafica vettoriale venga preservata e visualizzata correttamente in ambienti che potrebbero non supportare completamente SVG.

### Posso automatizzare questo processo per più documenti?
Assolutamente! Puoi scorrere più file HTML, applicando lo stesso processo per automatizzare la conversione per l'elaborazione batch.

### Dove posso trovare ulteriori risorse e supporto per Aspose.Words per .NET?
 Puoi trovare una documentazione completa[Qui](https://reference.aspose.com/words/net/) e ricevi supporto dalla comunità Aspose[Qui](https://forum.aspose.com/c/words/8).