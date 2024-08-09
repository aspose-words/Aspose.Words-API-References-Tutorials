---
title: Proporzioni bloccate
linktitle: Proporzioni bloccate
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come bloccare le proporzioni delle forme nei documenti di Word utilizzando Aspose.Words per .NET. Segui questa guida passo passo per mantenere le immagini e le forme proporzionate.
type: docs
weight: 10
url: /it/net/programming-with-shapes/aspect-ratio-locked/
---
## Introduzione

Ti sei mai chiesto come mantenere le proporzioni perfette di immagini e forme nei tuoi documenti Word? A volte è necessario assicurarsi che le immagini e le forme non vengano distorte quando vengono ridimensionate. È qui che il blocco delle proporzioni risulta utile. In questo tutorial esploreremo come impostare le proporzioni per le forme nei documenti di Word utilizzando Aspose.Words per .NET. Lo suddivideremo in passaggi facili da seguire, assicurandoci che tu possa applicare queste competenze ai tuoi progetti con sicurezza.

## Prerequisiti

Prima di immergerci nel codice, esaminiamo ciò di cui hai bisogno per iniziare:

- Libreria Aspose.Words per .NET: è necessario che sia installato Aspose.Words per .NET. Se non l'hai già fatto, puoi[scaricalo qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: assicurati di avere un ambiente di sviluppo .NET configurato. Visual Studio è una scelta popolare.
- Conoscenza di base di C#: sarà utile una certa familiarità con la programmazione C#.

## Importa spazi dei nomi

Per prima cosa, importiamo gli spazi dei nomi necessari. Questi spazi dei nomi ci daranno accesso alle classi e ai metodi di cui abbiamo bisogno per lavorare con documenti e forme di Word.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Passaggio 1: imposta la directory dei documenti

 Prima di iniziare a manipolare le forme, dobbiamo impostare una directory in cui verranno archiviati i nostri documenti. Per motivi di semplicità, utilizzeremo un segnaposto`YOUR DOCUMENT DIRECTORY`. Sostituiscilo con il percorso effettivo della directory dei documenti.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: crea un nuovo documento

Successivamente, creeremo un nuovo documento Word utilizzando Aspose.Words. Questo documento servirà come tela per aggiungere forme e immagini.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Qui creiamo un'istanza di`Document` classe e utilizzare a`DocumentBuilder` per aiutarci a costruire il contenuto del documento.

## Passaggio 3: inserisci un'immagine

 Ora inseriamo un'immagine nel nostro documento. Utilizzeremo il`InsertImage` metodo del`DocumentBuilder`classe. Assicurati di avere un'immagine nella directory specificata.

```csharp
Shape shape = builder.InsertImage(dataDir + "Transparent background logo.png");
```

 Sostituire`dataDir + "Transparent background logo.png"` con il percorso del file immagine.

## Passaggio 4: blocca le proporzioni

Una volta inserita l'immagine, possiamo bloccarne le proporzioni. Il blocco delle proporzioni garantisce che le proporzioni dell'immagine rimangano costanti durante il ridimensionamento.

```csharp
shape.AspectRatioLocked = true;
```

 Collocamento`AspectRatioLocked` A`true` garantisce che l'immagine mantenga le proporzioni originali.

## Passaggio 5: salva il documento

Infine, salveremo il documento nella directory specificata. Questo passaggio scrive tutte le modifiche apportate al file del documento.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

## Conclusione

Congratulazioni! Hai imparato con successo come impostare le proporzioni per le forme nei documenti di Word utilizzando Aspose.Words per .NET. Seguendo questi passaggi, puoi assicurarti che le immagini e le forme mantengano le loro proporzioni, conferendo ai tuoi documenti un aspetto professionale e raffinato. Sentiti libero di sperimentare immagini e forme diverse per vedere come funziona la funzione di blocco delle proporzioni in vari scenari.

## Domande frequenti

### Posso sbloccare le proporzioni dopo averle bloccate?
Sì, puoi sbloccare le proporzioni impostando`shape.AspectRatioLocked = false`.

### Cosa succede se ridimensiono un'immagine con proporzioni bloccate?
L'immagine verrà ridimensionata proporzionalmente, mantenendo il rapporto larghezza-altezza originale.

### Posso applicarlo ad altre forme oltre alle immagini?
Assolutamente! La funzione di blocco delle proporzioni può essere applicata a qualsiasi forma, inclusi rettangoli, cerchi e altro.

### Aspose.Words per .NET è compatibile con .NET Core?
Sì, Aspose.Words per .NET supporta sia .NET Framework che .NET Core.

### Dove posso trovare ulteriore documentazione su Aspose.Words per .NET?
 È possibile trovare una documentazione completa[Qui](https://reference.aspose.com/words/net/).