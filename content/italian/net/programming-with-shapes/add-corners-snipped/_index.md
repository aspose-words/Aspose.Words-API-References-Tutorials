---
title: Aggiungi angoli tagliati
linktitle: Aggiungi angoli tagliati
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere una forma con angoli ritagliati ai tuoi documenti Word utilizzando Aspose.Words per .NET. Questa guida passo passo ti consente di migliorare facilmente i tuoi documenti.
type: docs
weight: 10
url: /it/net/programming-with-shapes/add-corners-snipped/
---
## Introduzione

Aggiungere forme personalizzate ai tuoi documenti Word può essere un modo divertente e visivamente accattivante per evidenziare informazioni importanti o aggiungere un tocco di stile ai tuoi contenuti. In questo tutorial, approfondiremo come inserire forme "Angoli tagliati" nei documenti di Word utilizzando Aspose.Words per .NET. Questa guida ti guiderà attraverso ogni passaggio, assicurandoti di poter aggiungere facilmente queste forme e personalizzare i tuoi documenti come un professionista.

## Prerequisiti

Prima di addentrarci nel codice, assicuriamoci di avere tutto il necessario per iniziare:

1.  Aspose.Words per .NET: se non l'hai già fatto, scarica l'ultima versione da[Pagina delle versioni di Aspose](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: configura il tuo ambiente di sviluppo. Visual Studio è una scelta popolare, ma puoi utilizzare qualsiasi IDE che supporti .NET.
3.  Licenza: se stai solo sperimentando, puoi utilizzare a[prova gratuita](https://releases.aspose.com/) o prendi un[licenza temporanea](https://purchase.aspose.com/temporary-license/) per sbloccare la piena funzionalità.
4. Comprensione di base di C#: la familiarità con la programmazione C# ti aiuterà a seguire gli esempi.

## Importa spazi dei nomi

Prima di poter iniziare a lavorare con Aspose.Words per .NET, dobbiamo importare gli spazi dei nomi necessari. Aggiungi questi nella parte superiore del tuo file C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Ora suddividiamo il processo di aggiunta di una forma "Angoli tagliati" in più passaggi. Segui attentamente questi passaggi per assicurarti che tutto funzioni senza intoppi.

## Passaggio 1: inizializzare il documento e DocumentBuilder

 La prima cosa che dobbiamo fare è creare un nuovo documento e inizializzare un file`DocumentBuilder` oggetto. Questo builder ci aiuterà ad aggiungere contenuto al nostro documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 In questo passaggio, abbiamo impostato il nostro documento e generatore. Pensa a`DocumentBuilder` come la tua penna digitale, pronta per scrivere e disegnare nel tuo documento Word.

## Passaggio 2: inserire la forma ritagliata degli angoli

 Successivamente, utilizzeremo il file`DocumentBuilder` per inserire una forma "Angoli tagliati". Questo tipo di forma è predefinito in Aspose.Words e può essere facilmente inserito con una singola riga di codice.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

Qui stiamo specificando il tipo di forma e le sue dimensioni (50x50). Immagina di posizionare un piccolo adesivo angolare perfettamente ritagliato sul tuo documento. 

## Passaggio 3: definire le opzioni di salvataggio con conformità

Prima di salvare il nostro documento, dobbiamo definire le opzioni di salvataggio per garantire che il nostro documento sia conforme a standard specifici. Utilizzeremo il`OoxmlSaveOptions` lezione per questo.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
```

Queste opzioni di salvataggio garantiscono che il nostro documento aderisca allo standard ISO/IEC 29500:2008, che è fondamentale per la compatibilità e la longevità del documento.

## Passaggio 4: salva il documento

Infine, salviamo il nostro documento nella directory specificata utilizzando le opzioni di salvataggio definite in precedenza.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

E proprio così, il tuo documento ora contiene una forma personalizzata "Angoli tagliati", salvata con le opzioni di conformità necessarie.

## Conclusione

Ecco qua! Aggiungere forme personalizzate ai tuoi documenti Word utilizzando Aspose.Words per .NET è semplice e può migliorare notevolmente l'attrattiva visiva dei tuoi documenti. Seguendo questi passaggi, puoi inserire facilmente una forma "Angoli tagliati" e garantire che il tuo documento soddisfi gli standard richiesti. Buona programmazione!

## Domande frequenti

### Posso personalizzare la dimensione della forma "Angoli tagliati"?
Sì, puoi regolare le dimensioni modificando le dimensioni nel file`InsertShape` metodo.

### E' possibile aggiungere altri tipi di forme?
 Assolutamente! Aspose.Words supporta varie forme. Basta cambiare il`ShapeType` alla forma desiderata.

### Ho bisogno di una licenza per utilizzare Aspose.Words?
Sebbene sia possibile utilizzare una prova gratuita o una licenza temporanea, per un utilizzo senza restrizioni è necessaria una licenza completa.

### Come posso modellare ulteriormente le forme?
È possibile utilizzare proprietà e metodi aggiuntivi forniti da Aspose.Words per personalizzare l'aspetto e il comportamento delle forme.

### Aspose.Words è compatibile con altri formati?
Sì, Aspose.Words supporta più formati di documenti tra cui DOCX, PDF, HTML e altri.