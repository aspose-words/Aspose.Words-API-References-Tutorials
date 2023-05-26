---
title: Rompere un collegamento
linktitle: Rompere un collegamento
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come interrompere i collegamenti in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-textboxes/break-a-link/
---

Aspose.Words per .NET è una potente libreria che offre varie funzionalità per lavorare con i documenti di Microsoft Word a livello di programmazione. Una delle sue funzioni utili è la capacità di interrompere i collegamenti all'interno di un documento. In questo tutorial, esploreremo il codice sorgente in C# che dimostra come interrompere un collegamento utilizzando Aspose.Words per .NET.

## Passaggio 1: anteprima del codice sorgente C#

Il codice sorgente C# fornito si concentra sulla funzionalità "Break A Link" di Aspose.Words per .NET. Mostra come interrompere un collegamento in una forma TextBox all'interno di un documento. Il codice presenta diversi scenari per interrompere i collegamenti e fornisce istruzioni chiare su come ottenere i risultati desiderati.

## Passaggio 2: impostazione del documento e creazione di una forma TextBox

 Per iniziare, dobbiamo impostare il documento e creare una forma TextBox. Il codice seguente inizializza una nuova istanza di`Document` class e crea una forma di casella di testo:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Passaggio 3: interrompere il collegamento in avanti nella casella di testo

 Per interrompere un collegamento in avanti nel TextBox, possiamo usare il`BreakForwardLink()`metodo. Questo metodo interrompe il collegamento alla forma successiva nella sequenza. Il codice seguente mostra come interrompere un collegamento in avanti:

```csharp
textBox.BreakForwardLink();
```

## Passaggio 4: interrompere un collegamento in avanti impostando un valore nullo

 In alternativa, possiamo interrompere un collegamento in avanti impostando il TextBox`Next` proprietà a`null`. Questo rimuove efficacemente la connessione alla forma successiva. Il codice seguente illustra questo approccio:

```csharp
textBox. Next = null;
```

## Passaggio 5: interrompere un collegamento che porta alla casella di testo

 In alcuni casi, è necessario interrompere un collegamento che porta alla forma TextBox. Possiamo raggiungere questo obiettivo chiamando il`BreakForwardLink()` metodo sul`Previous` form, che interrompe il collegamento al TextBox. Ecco un esempio di come interrompere tale collegamento:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Esempio di codice sorgente per interrompere un collegamento con Aspose.Words per .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Interrompere il collegamento in avanti.
textBox.BreakForwardLink();

// Interrompi un collegamento in avanti impostando un valore nullo.
textBox. Next = null;

// Interrompere un collegamento che porta a questa casella di testo.
textBox.Previous?.BreakForwardLink();
```

