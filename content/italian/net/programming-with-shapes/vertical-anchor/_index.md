---
title: Ancoraggio verticale
linktitle: Ancoraggio verticale
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare le posizioni di ancoraggio verticale per le caselle di testo nei documenti di Word utilizzando Aspose.Words per .NET. Facile guida passo passo inclusa.
type: docs
weight: 10
url: /it/net/programming-with-shapes/vertical-anchor/
---
## Introduzione

Ti sei mai trovato a dover controllare esattamente dove appare il testo all'interno di una casella di testo in un documento Word? Forse vuoi che il tuo testo sia ancorato nella parte superiore, centrale o inferiore della casella di testo? Se è così, sei nel posto giusto! In questo tutorial esploreremo come utilizzare Aspose.Words per .NET per impostare l'ancoraggio verticale delle caselle di testo nei documenti Word. Pensa all'ancoraggio verticale come alla bacchetta magica che posiziona il tuo testo esattamente dove desideri all'interno del suo contenitore. Pronti a tuffarvi? Iniziamo!

## Prerequisiti

Prima di addentrarci nei dettagli dell'ancoraggio verticale, dovrai avere a che fare con alcune cose:

1.  Aspose.Words per .NET: assicurati di aver installato la libreria Aspose.Words per .NET. Se non ce l'hai ancora, puoi[scaricalo qui](https://releases.aspose.com/words/net/).
2. Visual Studio: questa esercitazione presuppone che tu stia utilizzando Visual Studio o un altro IDE .NET per la codifica.
3. Conoscenza di base di C#: la familiarità con C# e .NET ti aiuterà a seguire senza problemi.

## Importa spazi dei nomi

Per iniziare, devi importare gli spazi dei nomi necessari nel codice C#. Qui è dove dici alla tua applicazione dove trovare le classi e i metodi che utilizzerai. Ecco come farlo:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Questi spazi dei nomi forniscono le classi necessarie per lavorare con documenti e forme.

## Passaggio 1: inizializzare il documento

Per prima cosa, devi creare un nuovo documento Word. Pensa a questo come ad impostare la tua tela prima di iniziare a dipingere.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Qui,`Document` è la tua tela bianca, e`DocumentBuilder` è il tuo pennello e ti consente di aggiungere forme e testo.

## Passaggio 2: inserisci una forma di casella di testo

Ora aggiungiamo una casella di testo al nostro documento. Qui è dove vivrà il tuo testo. 

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

 In questo esempio,`ShapeType.TextBox` specifica la forma desiderata e`200, 200` sono la larghezza e l'altezza della casella di testo in punti.

## Passaggio 3: imposta l'ancoraggio verticale

Ecco dove avviene la magia! È possibile impostare l'allineamento verticale del testo all'interno della casella di testo. Ciò determina se il testo è ancorato nella parte superiore, centrale o inferiore della casella di testo.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

 In questo caso,`TextBoxAnchor.Bottom`assicura che il testo sarà ancorato alla parte inferiore della casella di testo. Se lo volessi centrato o allineato verso l'alto, utilizzeresti`TextBoxAnchor.Center` O`TextBoxAnchor.Top`, rispettivamente.

## Passaggio 4: aggiungi testo alla casella di testo

Ora è il momento di aggiungere alcuni contenuti alla tua casella di testo. Consideralo come riempire la tua tela con gli ultimi ritocchi.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

 Qui,`MoveTo` assicura che il testo sia inserito nella casella di testo e`Write` aggiunge il testo vero e proprio.

## Passaggio 5: salva il documento

Il passaggio finale è salvare il documento. È come mettere il tuo dipinto finito in una cornice.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

## Conclusione

Ed ecco qua! Hai appena imparato come controllare l'allineamento verticale del testo all'interno di una casella di testo in un documento Word utilizzando Aspose.Words per .NET. Che tu stia ancorando il testo in alto, al centro o in basso, questa funzionalità ti offre un controllo preciso sul layout del tuo documento. Quindi la prossima volta che avrai bisogno di modificare la posizione del testo del tuo documento, saprai esattamente cosa fare!

## Domande frequenti

### Cos'è l'ancoraggio verticale in un documento di Word?
L'ancoraggio verticale controlla la posizione del testo all'interno di una casella di testo, ad esempio l'allineamento superiore, centrale o inferiore.

### Posso utilizzare altre forme oltre alle caselle di testo?
Sì, puoi utilizzare l'ancoraggio verticale con altre forme, sebbene le caselle di testo siano il caso d'uso più comune.

### Come posso modificare il punto di ancoraggio dopo aver creato la casella di testo?
 È possibile modificare il punto di ancoraggio impostando il`VerticalAnchor` proprietà sull'oggetto forma casella di testo.

### È possibile ancorare il testo al centro della casella di testo?
 Assolutamente! Basta usare`TextBoxAnchor.Center` per centrare il testo verticalmente all'interno della casella di testo.

### Dove posso trovare ulteriori informazioni su Aspose.Words per .NET?
 Dai un'occhiata a[Documentazione Aspose.Words](https://reference.aspose.com/words/net/) per maggiori dettagli e guide.