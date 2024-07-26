---
title: Esporta il campo del modulo di input testo come testo
linktitle: Esporta il campo del modulo di input testo come testo
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come esportare i campi del modulo di input di testo come testo normale utilizzando Aspose.Words per .NET con questa guida completa passo passo.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---
## introduzione

Quindi ti stai immergendo nel mondo di Aspose.Words per .NET? Scelta fantastica! Se stai cercando informazioni su come esportare un campo modulo di input di testo come testo, sei nel posto giusto. Che tu abbia appena iniziato o stia rispolverando le tue abilità, questa guida ti guiderà attraverso tutto ciò che devi sapere. Cominciamo, ok?

## Prerequisiti

Prima di immergerci nel nocciolo della questione, assicuriamoci di avere tutto ciò di cui hai bisogno per procedere senza intoppi:

-  Aspose.Words per .NET: scarica e installa la versione più recente da[Qui](https://releases.aspose.com/words/net/).
- IDE: Visual Studio o qualsiasi ambiente di sviluppo C#.
- Conoscenza di base di C#: comprensione della sintassi di base di C# e dei concetti di programmazione orientata agli oggetti.
- Documento: un documento Word di esempio (`Rendering.docx`) con campi modulo di immissione testo.

## Importa spazi dei nomi

Per prima cosa, devi importare gli spazi dei nomi necessari. Questi sono come gli elementi costitutivi che fanno funzionare tutto senza problemi.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Saving;
```

Bene, ora che abbiamo i nostri spazi dei nomi pronti, passiamo all'azione!

## Passaggio 1: impostare il progetto

Prima di entrare nel codice, assicuriamoci che il nostro progetto sia impostato correttamente.

## Creazione del progetto

1. Apri Visual Studio: inizia aprendo Visual Studio o il tuo ambiente di sviluppo C# preferito.
2.  Crea un nuovo progetto: vai a`File > New > Project` . Selezionare`Console App (.NET Core)` o qualsiasi altro tipo di progetto pertinente.
3.  Dai un nome al tuo progetto: dai al tuo progetto un nome significativo, qualcosa del genere`AsposeWordsExportExample`.

## Aggiunta di Aspose.Words

1.  Gestisci pacchetti NuGet: fai clic con il pulsante destro del mouse sul progetto in Esplora soluzioni e seleziona`Manage NuGet Packages`.
2.  Cerca Aspose.Words: in Gestione pacchetti NuGet cercare`Aspose.Words`.
3.  Installa Aspose.Words: fai clic su`Install` per aggiungere la libreria Aspose.Words al tuo progetto.

## Passaggio 2: caricare il documento Word

Ora che il nostro progetto è configurato, carichiamo il documento Word che contiene i campi del modulo di input del testo.

1. Specificare la directory dei documenti: definire il percorso della directory in cui è archiviato il documento.
2.  Caricare il documento: utilizzare il file`Document` class per caricare il tuo documento Word.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: preparare la directory di esportazione

Prima di esportare, assicuriamoci che la nostra directory di esportazione sia pronta. Qui è dove verranno salvati il nostro file HTML e le immagini.

1. Definire la directory di esportazione: specificare il percorso in cui verranno salvati i file esportati.
2. Controlla e pulisci la directory: assicurati che la directory esista e sia vuota.

```csharp
string imagesDir = Path.Combine(dataDir, "Images");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);
```

## Passaggio 4: configura le opzioni di salvataggio

Ecco dove avviene la magia. Dobbiamo impostare le nostre opzioni di salvataggio per esportare il campo del modulo di input del testo come testo normale.

1.  Crea opzioni di salvataggio: inizializza un nuovo file`HtmlSaveOptions` oggetto.
2.  Imposta l'opzione di esportazione del testo: configura il file`ExportTextInputFormFieldAsText`proprietà a`true`.
3. Imposta cartella immagini: definire la cartella in cui verranno salvate le immagini.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true,
    ImagesFolder = imagesDir
};
```

## Passaggio 5: salva il documento come HTML

Infine, salviamo il documento Word come file HTML utilizzando le nostre opzioni di salvataggio configurate.

1. Definisci il percorso di output: specifica il percorso in cui verrà salvato il file HTML.
2.  Salvare il documento: utilizzare il file`Save` metodo del`Document`classe per esportare il documento.

```csharp
doc.Save(dataDir + "ExportedDocument.html", saveOptions);
```

## Conclusione

E il gioco è fatto! Hai esportato con successo un campo modulo di input di testo come testo normale utilizzando Aspose.Words per .NET. Questa guida dovrebbe fornirti un approccio chiaro e passo passo per raggiungere questo compito. Ricorda, la pratica rende perfetti, quindi continua a sperimentare diverse opzioni e impostazioni per vedere cos'altro puoi fare con Aspose.Words.

## Domande frequenti

### Posso esportare altri tipi di campi modulo utilizzando lo stesso metodo?

 Sì, puoi esportare altri tipi di campi modulo configurando diverse proprietà del file`HtmlSaveOptions` classe.

### Cosa succede se il mio documento contiene immagini?

 Le immagini verranno salvate nella cartella delle immagini specificata. Assicurati di impostare il`ImagesFolder` proprietà nel`HtmlSaveOptions`.

### Ho bisogno di una licenza per Aspose.Words?

 Sì, puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/) o acquistare una licenza[Qui](https://purchase.aspose.com/buy).

### Posso personalizzare l'HTML esportato?

 Assolutamente! Aspose.Words fornisce varie opzioni per personalizzare l'output HTML. Fare riferimento al[documentazione](https://reference.aspose.com/words/net/) per ulteriori dettagli.

### Aspose.Words è compatibile con .NET Core?

Sì, Aspose.Words è compatibile con .NET Core, .NET Framework e altre piattaforme .NET.
