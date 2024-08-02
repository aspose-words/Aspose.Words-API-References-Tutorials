---
title: Aggiungi forma di gruppo
linktitle: Aggiungi forma di gruppo
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere forme di gruppo ai documenti di Word utilizzando Aspose.Words per .NET con questo tutorial completo e passo passo.
type: docs
weight: 10
url: /it/net/programming-with-shapes/add-group-shape/
---
## introduzione

Creare documenti complessi con ricchi elementi visivi a volte può essere un compito arduo, soprattutto quando si ha a che fare con forme di gruppo. Ma non temere! Aspose.Words per .NET semplifica questo processo, rendendolo facile come una torta. In questo tutorial ti guideremo attraverso i passaggi per aggiungere forme di gruppo ai tuoi documenti Word. Pronti a tuffarvi? Iniziamo!

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1.  Aspose.Words per .NET: puoi scaricarlo dal file[Pagina delle versioni di Aspose](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: Visual Studio o qualsiasi altro IDE compatibile con .NET.
3. Comprensione di base di C#: la familiarità con la programmazione C# è un vantaggio.

## Importa spazi dei nomi

Per iniziare, dobbiamo importare gli spazi dei nomi necessari nel nostro progetto. Questi spazi dei nomi forniscono l'accesso alle classi e ai metodi richiesti per manipolare i documenti Word con Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Passaggio 1: inizializzare il documento

Per prima cosa, inizializziamo un nuovo documento Word. Pensa a questo come alla creazione di una tela bianca in cui aggiungeremo le forme del nostro gruppo.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.EnsureMinimum();
```

 Qui,`EnsureMinimum()` aggiunge un insieme minimo di nodi richiesti per il documento.

## Passaggio 2: crea l'oggetto GroupShape

 Successivamente, dobbiamo creare un file`GroupShape`oggetto. Questo oggetto servirà da contenitore per altre forme, permettendoci di raggrupparle insieme.

```csharp
GroupShape groupShape = new GroupShape(doc);
```

## Passaggio 3: aggiungi forme a GroupShape

 Ora aggiungiamo forme individuali al nostro`GroupShape` contenitore. Inizieremo con una forma del bordo accentuato e quindi aggiungeremo una forma del pulsante di azione.

### Aggiunta di una forma di bordo in accento

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1)
{
    Width = 100,
    Height = 100
};
groupShape.AppendChild(accentBorderShape);
```

 Questo frammento di codice crea una forma di bordo accentuato con larghezza e altezza di 100 unità e la aggiunge al file`GroupShape`.

### Aggiunta di una forma per il pulsante di azione

```csharp
Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

 Qui creiamo la forma di un pulsante di azione, la posizioniamo e la aggiungiamo al nostro`GroupShape`.

## Passaggio 4: definire le dimensioni di GroupShape

 Per garantire che le nostre forme si adattino bene al gruppo, dobbiamo impostare le dimensioni del file`GroupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

 Questo definisce la larghezza e l'altezza del file`GroupShape` come 200 unità e imposta di conseguenza la dimensione delle coordinate.

## Passaggio 5: inserire GroupShape nel documento

 Adesso inseriamo il ns`GroupShape` nel documento utilizzando`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

`DocumentBuilder` fornisce un modo semplice per aggiungere nodi, comprese le forme, al documento.

## Passaggio 6: salva il documento

Infine, salva il documento nella directory specificata.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

il gioco è fatto! Il tuo documento con forme di gruppo è pronto.

## Conclusione

L'aggiunta di forme di gruppo ai documenti di Word non deve essere un processo complicato. Con Aspose.Words per .NET, puoi creare e manipolare forme con facilità, rendendo i tuoi documenti più visivamente accattivanti e funzionali. Segui i passaggi descritti in questo tutorial e diventerai un professionista in pochissimo tempo!

## Domande frequenti

### Posso aggiungere più di due forme a GroupShape?
 Sì, puoi aggiungere tutte le forme di cui hai bisogno a`GroupShape` . Basta usare il`AppendChild` metodo per ciascuna forma.

### È possibile modellare le forme all'interno di GroupShape?
 Assolutamente! È possibile personalizzare lo stile di ciascuna forma utilizzando le proprietà disponibili nel file`Shape` classe.

### Come posso posizionare GroupShape all'interno del documento?
 È possibile posizionare il`GroupShape` impostando il suo`Left`E`Top` proprietà.

### Posso aggiungere testo alle forme all'interno di GroupShape?
 Sì, puoi aggiungere testo alle forme utilizzando il file`AppendChild` metodo per aggiungere a`Paragraph` contenente`Run` nodi con testo.

### È possibile raggruppare le forme dinamicamente in base all'input dell'utente?
Sì, puoi creare e raggruppare dinamicamente forme in base all'input dell'utente regolando di conseguenza le proprietà e i metodi.