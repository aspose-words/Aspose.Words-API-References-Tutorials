---
title: Revisione della forma
linktitle: Revisione della forma
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come gestire le revisioni delle forme nei documenti Word utilizzando Aspose.Words per .NET con questa guida completa. Padroneggia il monitoraggio delle modifiche, l'inserimento di forme e altro ancora.
type: docs
weight: 10
url: /it/net/working-with-revisions/shape-revision/
---
## Introduzione

La modifica dei documenti di Word a livello di codice può essere un compito arduo, soprattutto quando si tratta di gestire le forme. Che tu stia creando report, progettando modelli o semplicemente automatizzando la creazione di documenti, la capacità di tenere traccia e gestire le revisioni delle forme è fondamentale. Aspose.Words per .NET offre una potente API per rendere questo processo semplice ed efficiente. In questo tutorial, approfondiremo le specifiche della revisione delle forme nei documenti di Word, assicurandoci di avere gli strumenti e le conoscenze per gestire facilmente i tuoi documenti.

## Prerequisiti

Prima di immergerci nel codice, assicuriamoci di avere tutto ciò di cui hai bisogno:

-  Aspose.Words per .NET: assicurati di avere la libreria Aspose.Words installata. Puoi[scaricalo qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: è necessario disporre di un ambiente di sviluppo configurato, ad esempio Visual Studio.
- Comprensione di base di C#: familiarità con il linguaggio di programmazione C# e concetti di base della programmazione orientata agli oggetti.
- Documento Word: un documento Word con cui lavorare oppure puoi crearne uno durante il tutorial.

## Importa spazi dei nomi

Per prima cosa importiamo gli spazi dei nomi necessari. Questi ci forniranno l'accesso alle classi e ai metodi necessari per gestire documenti e forme di Word.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Passaggio 1: impostazione della directory dei documenti

Prima di iniziare a lavorare con le forme, dobbiamo definire il percorso della nostra directory dei documenti. Qui è dove salveremo i nostri documenti modificati.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creazione di un nuovo documento

Creiamo un nuovo documento Word in cui inseriremo e rivedremo le forme.

```csharp
Document doc = new Document();
```

## Passaggio 3: inserimento di una forma in linea

Inizieremo inserendo una forma in linea nel nostro documento senza tenere traccia delle revisioni. Una forma in linea è una forma che scorre con il testo.

```csharp
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Passaggio 4: iniziare a tenere traccia delle revisioni

Per tenere traccia delle modifiche nel nostro documento, dobbiamo abilitare il monitoraggio delle revisioni. Ciò è essenziale per identificare le modifiche apportate alle forme.

```csharp
doc.StartTrackRevisions("John Doe");
```

## Passaggio 5: inserimento di un'altra forma con revisioni

Ora che il rilevamento delle revisioni è abilitato, inseriamo un'altra forma. Questa volta, eventuali modifiche verranno monitorate.

```csharp
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Passaggio 6: recupero e modifica delle forme

Possiamo recuperare tutte le forme nel documento e modificarle secondo necessità. Qui otterremo le forme e rimuoveremo la prima.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
shapes[0].Remove();
```

## Passaggio 7: salvataggio del documento

Dopo aver apportato le modifiche, dobbiamo salvare il documento. Ciò garantisce che tutte le revisioni e le modifiche vengano archiviate.

```csharp
doc.Save(dataDir + "Revision shape.docx");
```

## Passaggio 8: gestione delle revisioni dello spostamento della forma

Quando una forma viene spostata, Aspose.Words ne tiene traccia come una revisione. Ciò significa che ci saranno due istanze della forma: una nella posizione originale e l'altra nella nuova posizione.

```csharp
doc = new Document(dataDir + "Revision shape.docx");
shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
```

## Conclusione

Ed ecco qua! Hai imparato con successo come gestire le revisioni delle forme nei documenti Word utilizzando Aspose.Words per .NET. Che tu stia gestendo modelli di documenti, automatizzando report o semplicemente tenendo traccia delle modifiche, queste competenze sono inestimabili. Seguendo questa guida passo passo, non solo avrai acquisito padronanza delle nozioni di base, ma avrai anche acquisito informazioni sulle tecniche di gestione dei documenti più avanzate.

## Domande frequenti

### Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una potente libreria che consente agli sviluppatori di creare, modificare e convertire documenti Word a livello di codice utilizzando C#.

### Posso tenere traccia delle modifiche apportate ad altri elementi in un documento di Word?
Sì, Aspose.Words per .NET supporta il monitoraggio delle modifiche a vari elementi, inclusi testo, tabelle e altro.

### Come posso ottenere una prova gratuita di Aspose.Words per .NET?
 Puoi ottenere una prova gratuita di Aspose.Words per .NET[Qui](https://releases.aspose.com/).

### È possibile accettare o rifiutare le revisioni a livello di codice?
Sì, Aspose.Words per .NET fornisce metodi per accettare o rifiutare le revisioni a livello di codice.

### Posso utilizzare Aspose.Words per .NET con altri linguaggi .NET oltre a C#?
Assolutamente! Aspose.Words per .NET può essere utilizzato con qualsiasi linguaggio .NET, inclusi VB.NET e F#.