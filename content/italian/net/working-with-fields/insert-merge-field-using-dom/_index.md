---
title: Inserisci campo unione utilizzando DOM
linktitle: Inserisci campo unione utilizzando DOM
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire e configurare i campi di unione nei documenti di Word utilizzando Aspose.Words per .NET con questo tutorial completo e passo passo.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-merge-field-using-dom/
---
## introduzione

Se lavori con l'elaborazione di documenti in .NET, probabilmente ti sei imbattuto in Aspose.Words. Questa potente libreria offre un'ampia gamma di funzionalità per la manipolazione dei documenti Word a livello di codice. In questo tutorial, ci concentreremo su una funzionalità specifica: l'inserimento di un campo di unione utilizzando il Document Object Model (DOM) in Aspose.Words per .NET. Questa guida ti guiderà attraverso ogni passaggio, dalla configurazione del tuo ambiente all'inserimento e all'aggiornamento di un campo di unione in un documento di Word.

## Prerequisiti

Prima di immergerti nel codice, assicuriamoci di avere tutto ciò di cui hai bisogno per seguire questo tutorial.

1. Conoscenza di base di C#: dovresti avere dimestichezza con la programmazione in C#.
2. Visual Studio installato: assicurati di avere Visual Studio o qualsiasi altro IDE C# installato sul tuo computer.
3.  Aspose.Words per .NET: scarica e installa l'ultima versione di Aspose.Words per .NET dal[Rilasci](https://releases.aspose.com/words/net/).
4.  Licenza valida: se non disponi di una licenza, puoi ottenerne una[licenza temporanea](https://purchase.aspose.com/temporary-license/) Per la valutazione.

## Passaggio 1: imposta il tuo progetto

Per prima cosa, configuriamo un nuovo progetto in Visual Studio.

1. Apri VisualStudio.
2. Crea un nuovo progetto: vai su File > Nuovo > Progetto. Selezionare un'app console C#.
3. Dai un nome al tuo progetto: dai al tuo progetto un nome significativo e fai clic su Crea.

## Passaggio 2: installa Aspose.Words

Per utilizzare Aspose.Words, devi aggiungerlo al tuo progetto. Questa operazione può essere eseguita tramite Gestione pacchetti NuGet.

1. Apri Gestione pacchetti NuGet: fai clic con il pulsante destro del mouse sul progetto in Esplora soluzioni, quindi seleziona Gestisci pacchetti NuGet.
2. Cerca Aspose.Words: in Gestione pacchetti NuGet cercare "Aspose.Words".
3. Installa il pacchetto: fai clic su Installa per aggiungere Aspose.Words al tuo progetto.

## Passaggio 3: importare gli spazi dei nomi

Per iniziare a utilizzare Aspose.Words, devi importare gli spazi dei nomi necessari nel tuo progetto. Ecco come puoi farlo:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

## Passaggio 4: inizializza il documento

Ora che tutto è impostato, creiamo un nuovo documento Word e inizializziamo DocumentBuilder.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 5: sposta il cursore sul paragrafo specifico

Successivamente, dobbiamo spostare il cursore su un paragrafo specifico del documento in cui vogliamo inserire il campo di unione.

```csharp
Paragraph para = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);
builder.MoveTo(para);
```

## Passaggio 6: inserire il campo Unisci

 L'inserimento di un campo di unione è semplice. Utilizzeremo il`InsertField` metodo del`DocumentBuilder` classe.

```csharp
// Inserisci campo unione campo.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

## Passaggio 7: configurare il campo di unione

Dopo aver inserito il campo unione è possibile impostare varie proprietà per configurarlo in base alle proprie esigenze.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field.TextAfter = "Test3";
field.IsMapped = true;
field.IsVerticalFormatting = true;
```

## Passaggio 8: aggiorna e salva il documento

Infine, aggiorna il campo per assicurarti che tutte le impostazioni siano applicate e salva il documento.

```csharp
// Aggiorna il campo.
field.Update();

// Salva il documento.
doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

## Conclusione

Seguendo questi passaggi, puoi facilmente inserire e configurare i campi di unione in un documento di Word utilizzando Aspose.Words per .NET. Questo tutorial ha coperto i passaggi essenziali dalla configurazione dell'ambiente al salvataggio del documento finale. Con Aspose.Words puoi automatizzare attività complesse di elaborazione dei documenti, rendendo le tue applicazioni .NET più potenti ed efficienti.

## Domande frequenti

###  Cos'è un campo unione?
Un campo di unione è un segnaposto in un documento che può essere sostituito dinamicamente con dati provenienti da un'origine dati, ad esempio un database o un file CSV.

###  Posso usare Aspose.Words gratuitamente?
 Aspose.Words offre una prova gratuita che puoi scaricare[Qui](https://releases.aspose.com/). Per un utilizzo a lungo termine, sarà necessario acquistare una licenza.

###  Come posso ottenere una licenza temporanea per Aspose.Words?
 È possibile ottenere una licenza temporanea dal sito Web Aspose[Qui](https://purchase.aspose.com/temporary-license/).

### Quali versioni di .NET sono supportate da Aspose.Words?
Aspose.Words supporta più versioni di .NET, inclusi .NET Framework, .NET Core e .NET Standard.

###  Dove posso trovare la documentazione API per Aspose.Words?
 La documentazione dell'API è disponibile[Qui](https://reference.aspose.com/words/net/).