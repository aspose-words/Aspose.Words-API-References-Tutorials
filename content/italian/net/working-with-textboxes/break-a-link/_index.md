---
title: Interrompi il collegamento in avanti nel documento di Word
linktitle: Interrompi il collegamento in avanti nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come interrompere i collegamenti in avanti in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-textboxes/break-a-link/
---

Aspose.Words per .NET è una potente libreria che offre varie funzionalità per l'elaborazione di parole con documenti Microsoft Word a livello di codice. Una delle sue caratteristiche utili è la possibilità di interrompere i collegamenti in avanti in un documento Word. In questo tutorial esploreremo il codice sorgente in C# che dimostra come interrompere il collegamento in avanti nel documento Word utilizzando Aspose.Words per .NET.

## Passaggio 1: anteprima del codice sorgente C#

Il codice sorgente C# fornito si concentra sulla funzionalità "Interrompi un collegamento" di Aspose.Words per .NET. Mostra come interrompere un collegamento in una forma TextBox all'interno di un documento. Il codice presenta diversi scenari per l'interruzione dei collegamenti e fornisce istruzioni chiare su come ottenere i risultati desiderati.

## Passaggio 2: impostazione del documento e creazione di una forma TextBox

 Per iniziare, dobbiamo impostare il documento e creare una forma TextBox. Il codice seguente inizializza una nuova istanza di`Document` class e crea una forma di casella di testo:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Passaggio 3: interrompere il collegamento in avanti in TextBox

 Per interrompere un collegamento in avanti nella casella di testo, possiamo utilizzare il comando`BreakForwardLink()` metodo. Questo metodo interrompe il collegamento alla forma successiva nella sequenza. Il codice seguente mostra come interrompere un collegamento di inoltro:

```csharp
textBox.BreakForwardLink();
```

## Passaggio 4: interrompere un collegamento in avanti impostando un valore nullo

 In alternativa, possiamo interrompere un collegamento in avanti impostando TextBox's`Next`proprietà a`null`. Ciò rimuove effettivamente la connessione alla forma successiva. Il codice seguente illustra questo approccio:

```csharp
textBox. Next = null;
```

## Passaggio 5: interrompere un collegamento che porta al TextBox

 In alcuni casi, dobbiamo interrompere un collegamento che porta alla forma TextBox. Possiamo raggiungere questo obiettivo chiamando il`BreakForwardLink()` metodo sul`Previous` form, che interrompe il collegamento al TextBox. Ecco un esempio di come interrompere un collegamento di questo tipo:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Codice sorgente di esempio per interrompere un collegamento con Aspose.Words per .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Interrompi il collegamento in avanti.
textBox.BreakForwardLink();

// Interrompere un collegamento in avanti impostando un valore nullo.
textBox. Next = null;

// Interrompere un collegamento che porta a questa casella di testo.
textBox.Previous?.BreakForwardLink();
```

## Conclusione

Congratulazioni! Ora hai imparato come interrompere i collegamenti di reindirizzamento in un documento Word utilizzando la libreria Aspose.Words per .NET. Seguendo i passaggi di questa guida, sei stato in grado di impostare il documento, creare una forma TextBox e interrompere i collegamenti di reindirizzamento utilizzando metodi diversi.

### Domande frequenti sul collegamento di interruzione dell'inoltro nel documento Word

#### D: Qual è la libreria utilizzata per interrompere i collegamenti di reindirizzamento in un documento Word utilizzando Aspose.Words per .NET?

R: Per interrompere i collegamenti di reindirizzamento in un documento Word utilizzando Aspose.Words per .NET, la libreria utilizzata è Aspose.Words per .NET.

#### D: Come interrompere un collegamento di reindirizzamento in una casella di testo?

 R: Per interrompere un collegamento in avanti in una casella di testo, puoi utilizzare il file`BreakForwardLink()` metodo. Questo metodo interrompe il collegamento alla forma successiva nella sequenza.

#### D: Come interrompere un collegamento di reindirizzamento impostando un valore nullo?

R: In alternativa, puoi interrompere un collegamento di reindirizzamento impostando il file`Next` proprietà del TextBox a`null`. Ciò rimuove effettivamente la connessione alla forma successiva.

#### D: Come interrompere un collegamento che porta al TextBox?

 R: In alcuni casi è necessario interrompere un collegamento che porta al TextBox. Puoi raggiungere questo obiettivo chiamando il`BreakForwardLink()` metodo sul`Previous` form, che interrompe il collegamento al TextBox.

#### D: Possiamo interrompere i collegamenti di reindirizzamento su elementi diversi dai TextBox?

R: Sì, con Aspose.Words per .NET è possibile interrompere i collegamenti di reindirizzamento su diversi elementi come paragrafi, tabelle, immagini, ecc. Il processo può variare a seconda dell'elemento specifico su cui si desidera interrompere il collegamento.