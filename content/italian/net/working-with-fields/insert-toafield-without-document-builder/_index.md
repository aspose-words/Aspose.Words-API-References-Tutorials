---
title: Inserisci campo TOA senza generatore di documenti
linktitle: Inserisci campo TOA senza generatore di documenti
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un campo TOA senza utilizzare un generatore di documenti in Aspose.Words per .NET. Segui la nostra guida passo passo per gestire in modo efficiente le citazioni legali.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-toafield-without-document-builder/
---
## Introduzione

Creare un campo TOA (Tabella delle autorità) in un documento di Word può sembrare come mettere insieme un puzzle complesso. Tuttavia, con l'aiuto di Aspose.Words per .NET, il processo diventa semplice e fluido. In questo articolo ti guideremo attraverso i passaggi per inserire un campo TOA senza utilizzare un generatore di documenti, semplificando la gestione delle citazioni e dei riferimenti legali all'interno dei tuoi documenti Word.

## Prerequisiti

Prima di immergerci nel tutorial, copriamo gli elementi essenziali di cui avrai bisogno:

-  Aspose.Words per .NET: assicurati di avere installata la versione più recente. Puoi scaricarlo da[Sito web Aspose](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: un IDE compatibile con .NET come Visual Studio.
- Conoscenza di base di C#: comprendere la sintassi e i concetti di base di C# sarà utile.
- Documento Word di esempio: crea o tieni pronto un documento di esempio in cui desideri inserire il campo TOA.

## Importa spazi dei nomi

Per iniziare, dovrai importare gli spazi dei nomi necessari dalla libreria Aspose.Words. Questa configurazione garantisce l'accesso a tutte le classi e i metodi richiesti per la manipolazione dei documenti.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Suddividiamo il processo in passaggi semplici e facili da seguire. Ti guideremo attraverso ogni fase, spiegando cosa fa ogni pezzo di codice e come contribuisce a creare il campo TOA.

## Passaggio 1: inizializzare il documento

 Per prima cosa è necessario creare un'istanza del file`Document` classe. Questo oggetto rappresenta il documento Word su cui stai lavorando.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

Questo codice inizializza un nuovo documento di Word. Puoi considerarlo come la creazione di una tela bianca a cui aggiungere i tuoi contenuti.

## Passaggio 2: creare e configurare il campo TA

Successivamente, aggiungeremo un campo TA (Tabella delle autorità). Questo campo contrassegna le voci che appariranno nel TOA.

```csharp
Paragraph para = new Paragraph(doc);

// Vogliamo inserire i campi TA e TOA in questo modo:
// { TA \c 1 \l "Valore 0" }
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);
```

Ecco una ripartizione:
- Paragraph para = new Paragraph(doc);: crea un nuovo paragrafo all'interno del documento.
-  FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);: Aggiunge un campo TA al paragrafo. IL`FieldType.FieldTOAEntry` specifica che questo è un campo di immissione TOA.
- fieldTA.EntryCategory = "1";: imposta la categoria della voce. Ciò è utile per classificare diversi tipi di voci.
- fieldTA.LongCitation = "Valore 0";: specifica il testo della citazione lunga. Questo è il testo che apparirà nel TOA.
- doc.FirstSection.Body.AppendChild(para);: aggiunge il paragrafo con il campo TA al corpo del documento.

## Passaggio 3: aggiungi il campo TOA

Ora inseriremo il campo TOA effettivo che compila tutte le voci TA in una tabella.

```csharp
para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);
```

In questo passaggio:
- FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);: Aggiunge un campo TOA al paragrafo.
- fieldToa.EntryCategory = "1";: Filtra le voci per includere solo quelle contrassegnate con la categoria "1".

## Passaggio 4: aggiorna il campo TOA

Dopo aver inserito il campo TOA, è necessario aggiornarlo per garantire che rifletta le voci più recenti.

```csharp
fieldToa.Update();
```

Questo comando aggiorna il campo TOA, assicurando che tutte le voci contrassegnate siano visualizzate correttamente nella tabella.

## Passaggio 5: salva il documento

Infine, salva il documento con il campo TOA appena aggiunto.

```csharp
doc.Save(dataDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

 Questa riga di codice salva il documento nella directory specificata. Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui desideri salvare il file.

## Conclusione

Ed ecco qua! Hai aggiunto correttamente un campo TOA a un documento Word senza utilizzare un generatore di documenti. Seguendo questi passaggi, puoi gestire in modo efficiente le citazioni e creare tabelle complete delle autorità nei tuoi documenti legali. Aspose.Words per .NET rende questo processo fluido ed efficiente, offrendoti gli strumenti per gestire facilmente attività complesse relative ai documenti.

## Domande frequenti

### Posso aggiungere più campi TA con categorie diverse?
 Sì, puoi aggiungere più campi TA con categorie diverse impostando il file`EntryCategory`proprietà di conseguenza.

### Come posso personalizzare l'aspetto del TOA?
È possibile personalizzare l'aspetto del TOA modificando le proprietà del campo TOA, come la formattazione della voce e le etichette delle categorie.

### È possibile aggiornare automaticamente il campo TOA?
 Sebbene sia possibile aggiornare manualmente il campo TOA utilizzando il file`Update` metodo, Aspose.Words attualmente non supporta gli aggiornamenti automatici sulle modifiche al documento.

### Posso aggiungere campi TA a livello di codice in parti specifiche del documento?
Sì, puoi aggiungere campi TA in posizioni specifiche inserendoli nei paragrafi o nelle sezioni desiderati.

### Come posso gestire più campi TOA in un singolo documento?
 È possibile gestire più campi TOA assegnando campi diversi`EntryCategory` valori e garantendo che ogni campo TOA filtri le voci in base alla sua categoria.