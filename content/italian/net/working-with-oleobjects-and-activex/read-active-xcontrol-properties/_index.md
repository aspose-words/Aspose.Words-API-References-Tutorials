---
title: Leggi le proprietà XControl attive dal file Word
linktitle: Leggi le proprietà XControl attive dal file Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come leggere le proprietà del controllo ActiveX dai file Word utilizzando Aspose.Words per .NET in una guida passo passo. Migliora le tue capacità di automazione dei documenti.
type: docs
weight: 10
url: /it/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---
## Introduzione

Nell'era digitale di oggi, l'automazione è fondamentale per migliorare la produttività. Se lavori con documenti Word che contengono controlli ActiveX, potrebbe essere necessario leggerne le proprietà per vari scopi. I controlli ActiveX, come caselle di controllo e pulsanti, possono contenere dati importanti. Utilizzando Aspose.Words per .NET, puoi estrarre e manipolare in modo efficiente questi dati a livello di codice.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1.  Aspose.Words per .NET Library: puoi scaricarlo da[Qui](https://releases.aspose.com/words/net/).
2. Visual Studio o qualsiasi IDE C#: per scrivere ed eseguire il tuo codice.
3. Un documento Word con controlli ActiveX: ad esempio "controlli ActiveX.docx".
4. Conoscenza di base di C#: è necessaria la familiarità con la programmazione C#.

## Importa spazi dei nomi

Innanzitutto, importiamo gli spazi dei nomi necessari per lavorare con Aspose.Words per .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Ole;
using System;
```

## Passaggio 1: caricare il documento Word

Per iniziare, dovrai caricare il documento Word che contiene i controlli ActiveX.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ActiveX controls.docx");
```

## Passaggio 2: inizializzare una stringa per conservare le proprietà

Inizializzare quindi una stringa vuota per memorizzare le proprietà dei controlli ActiveX.

```csharp
string properties = "";
```

## Passaggio 3: scorrere le forme nel documento

Dobbiamo scorrere tutte le forme nel documento per trovare i controlli ActiveX.

```csharp
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
    if (shape.OleFormat is null) continue;
    
    OleControl oleControl = shape.OleFormat.OleControl;
    if (oleControl.IsForms2OleControl)
    {
        // Elaborare il controllo ActiveX
    }
}
```

## Passaggio 4: estrarre le proprietà dai controlli ActiveX

All'interno del ciclo, controlla se il controllo è un Forms2OleControl. Se lo è, lancialo ed estrai le proprietà.

```csharp
Forms2OleControl checkBox = (Forms2OleControl) oleControl;
properties += "\nCaption: " + checkBox.Caption;
properties += "\nValue: " + checkBox.Value;
properties += "\nEnabled: " + checkBox.Enabled;
properties += "\nType: " + checkBox.Type;

if (checkBox.ChildNodes != null)
{
    properties += "\nChildNodes: " + checkBox.ChildNodes;
}

properties += "\n";
```

## Passaggio 5: contare i controlli ActiveX totali

Dopo aver eseguito l'iterazione di tutte le forme, contare il numero totale di controlli ActiveX trovati.

```csharp
properties += "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
```

## Passaggio 6: visualizzare le proprietà

Infine, stampa le proprietà estratte sulla console.

```csharp
Console.WriteLine("\n" + properties);
```

## Conclusione

Ed ecco qua! Hai imparato con successo come leggere le proprietà del controllo ActiveX da un documento Word utilizzando Aspose.Words per .NET. Questo tutorial ha trattato il caricamento di un documento, l'iterazione delle forme e l'estrazione delle proprietà dai controlli ActiveX. Seguendo questi passaggi, puoi automatizzare l'estrazione di dati importanti dai tuoi documenti Word, migliorando l'efficienza del tuo flusso di lavoro.

## Domande frequenti

### Cosa sono i controlli ActiveX nei documenti di Word?
I controlli ActiveX sono oggetti interattivi incorporati nei documenti di Word, come caselle di controllo, pulsanti e campi di testo, utilizzati per creare moduli e automatizzare le attività.

### Posso modificare le proprietà dei controlli ActiveX utilizzando Aspose.Words per .NET?
Sì, Aspose.Words per .NET consente di modificare le proprietà dei controlli ActiveX a livello di codice.

### Aspose.Words per .NET è gratuito?
 Aspose.Words per .NET offre una prova gratuita, ma dovrai acquistare una licenza per l'uso continuato. Puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/).

### Posso utilizzare Aspose.Words per .NET con altri linguaggi .NET oltre a C#?
Sì, Aspose.Words per .NET può essere utilizzato con qualsiasi linguaggio .NET, inclusi VB.NET e F#.

### Dove posso trovare ulteriore documentazione su Aspose.Words per .NET?
 Puoi trovare documentazione dettagliata[Qui](https://reference.aspose.com/words/net/).