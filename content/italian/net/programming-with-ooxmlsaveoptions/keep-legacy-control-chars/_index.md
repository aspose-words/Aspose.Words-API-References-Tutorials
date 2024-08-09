---
title: Mantieni i caratteri di controllo legacy
linktitle: Mantieni i caratteri di controllo legacy
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come preservare i caratteri di controllo legacy nei documenti Word utilizzando Aspose.Words per .NET con questa guida passo passo.
type: docs
weight: 10
url: /it/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---
## Introduzione

Sei mai stato perplesso da quegli strani caratteri di controllo invisibili nei tuoi documenti Word? Sono come piccoli gremlin nascosti che possono rovinare la formattazione e la funzionalità. Fortunatamente, Aspose.Words per .NET fornisce una funzionalità utile per mantenere intatti questi caratteri di controllo legacy durante il salvataggio dei documenti. In questo tutorial, approfondiremo come gestire questi caratteri di controllo utilizzando Aspose.Words per .NET. Lo analizzeremo passo dopo passo, assicurandoti di cogliere ogni dettaglio lungo il percorso. Pronti per iniziare? Immergiamoci!

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1.  Aspose.Words per .NET: scarica e installa da[Qui](https://releases.aspose.com/words/net/).
2.  Una licenza Aspose valida: è possibile ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
3. Ambiente di sviluppo: Visual Studio o qualsiasi altro IDE che supporti .NET.
4. Conoscenza di base di C#: sarà utile la familiarità con il linguaggio di programmazione C#.

## Importa spazi dei nomi

Prima di scrivere il codice, devi importare gli spazi dei nomi necessari. Aggiungi le seguenti righe all'inizio del tuo file C#:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Passaggio 1: impostazione del progetto

Innanzitutto, dovrai configurare il tuo progetto in Visual Studio (o il tuo IDE preferito). 

1. Creare un nuovo progetto C#: aprire Visual Studio e creare un nuovo progetto di applicazione console C#.
2. Installare Aspose.Words per .NET: utilizzare NuGet Package Manager per installare Aspose.Words per .NET. Fai clic con il pulsante destro del mouse sul progetto in Esplora soluzioni, seleziona "Gestisci pacchetti NuGet", cerca "Aspose.Words" e installalo.

## Passaggio 2: carica il documento

Successivamente, caricherai il documento di Word che contiene i caratteri di controllo legacy.

1. Specificare il percorso del documento: imposta il percorso della directory dei documenti.
   
   ```csharp
   string dataDir = "YOUR DOCUMENT DIRECTORY";
   ```

2.  Caricare il documento: utilizzare il file`Document` class per caricare il documento.

   ```csharp
   Document doc = new Document(dataDir + "Legacy control character.doc");
   ```

## Passaggio 3: configura le opzioni di salvataggio

Ora configuriamo le opzioni di salvataggio per mantenere intatti i caratteri di controllo legacy.

1.  Crea opzioni di salvataggio: inizializza un'istanza di`OoxmlSaveOptions` e impostare il`KeepLegacyControlChars`proprietà a`true`.

   ```csharp
   OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc)
   {
       KeepLegacyControlChars = true
   };
   ```

## Passaggio 4: salva il documento

Infine, salva il documento con le opzioni di salvataggio configurate.

1.  Salvare il documento: utilizzare il file`Save` metodo del`Document` classe per salvare il documento con le opzioni di salvataggio specificate.

   ```csharp
   doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
   ```

## Conclusione

Ed ecco qua! Seguendo questi passaggi, puoi assicurarti che i caratteri di controllo legacy vengano preservati quando lavori con documenti Word in Aspose.Words per .NET. Questa funzionalità può essere un vero toccasana, soprattutto quando si ha a che fare con documenti complessi in cui i caratteri di controllo svolgono un ruolo cruciale. 

## Domande frequenti

### Cosa sono i caratteri di controllo legacy?

I caratteri di controllo legacy sono caratteri non stampabili utilizzati nei documenti più vecchi per controllare la formattazione e il layout.

### Posso rimuovere questi caratteri di controllo invece di mantenerli?

Sì, puoi utilizzare Aspose.Words per .NET per rimuovere o sostituire questi caratteri, se necessario.

### Questa funzionalità è disponibile in tutte le versioni di Aspose.Words per .NET?

Questa funzionalità è disponibile nelle versioni recenti. Assicurati di utilizzare la versione più recente per accedere a tutte le funzionalità.

### Ho bisogno di una licenza per utilizzare Aspose.Words per .NET?

 Sì, è necessaria una licenza valida. È possibile ottenere una licenza temporanea a scopo di valutazione[Qui](https://purchase.aspose.com/temporary-license/).

### Dove posso trovare ulteriore documentazione su Aspose.Words per .NET?

 Puoi trovare documentazione dettagliata[Qui](https://reference.aspose.com/words/net/).
 