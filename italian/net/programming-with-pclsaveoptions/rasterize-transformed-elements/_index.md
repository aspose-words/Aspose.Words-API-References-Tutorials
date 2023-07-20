---
title: Rasterizza elementi trasformati
linktitle: Rasterizza elementi trasformati
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come disabilitare la rasterizzazione degli elementi trasformati durante la conversione in formato PCL con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words per .NET è una potente libreria per creare, manipolare e convertire documenti Word in un'applicazione C#. Tra le funzionalità offerte da Aspose.Words c'è la capacità di rasterizzare gli elementi trasformati durante la conversione di documenti in diversi formati. In questa guida, ti mostreremo come utilizzare il codice sorgente C# di Aspose.Words per .NET per disabilitare la rasterizzazione degli elementi trasformati durante la conversione di un documento in formato PCL.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una libreria popolare che rende l'elaborazione di testi con documenti Word semplice ed efficiente. Offre un'ampia gamma di funzionalità per la creazione, la modifica e la conversione di documenti Word, incluso il supporto per la rasterizzazione degli elementi trasformati durante la conversione.

## Caricamento del documento Word

Il primo passo è caricare il documento Word che desideri convertire in formato PCL. Utilizzare la classe Document per caricare il documento dal file di origine. Ecco un esempio:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

In questo esempio, stiamo caricando il documento "Rendering.docx" che si trova nella directory dei documenti.

## Configurazione delle opzioni di backup

Il passaggio successivo consiste nel configurare le opzioni di salvataggio per la conversione in formato PCL. Utilizzare la classe PclSaveOptions e impostare la proprietà RasterizeTransformedElements su false. Ecco come farlo:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

Creiamo un nuovo oggetto PclSaveOptions e impostiamo la proprietà SaveFormat su SaveFormat.Pcl per specificare che vogliamo salvare il documento in formato PCL. Successivamente, impostiamo la proprietà RasterizeTransformedElements su false per disabilitare la rasterizzazione degli elementi trasformati.

## Conversione del documento in formato PCL

Ora che abbiamo configurato le opzioni di salvataggio, possiamo procedere alla conversione del documento in formato PCL. Utilizzare il metodo Save della classe Document per salvare il documento convertito in formato PCL specificando le opzioni di salvataggio. Ecco un esempio:

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

In questo esempio, salviamo il documento convertito come "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" utilizzando le opzioni di salvataggio specificate.

### Esempio di codice sorgente per la funzione "Rasterizza elementi trasformati" con Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento di Word


Document doc = new Document(dataDir + "Rendering.docx");

// Configurare le opzioni di backup per la conversione in formato PCL
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// Convertire il documento in formato PCL
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## Conclusione

In questa guida, abbiamo illustrato come utilizzare Aspose.Words per .NET per disabilitare la rasterizzazione degli elementi trasformati durante la conversione di un documento in formato PCL utilizzando il codice sorgente C# fornito. Seguendo i passaggi forniti, puoi facilmente controllare il comportamento di rasterizzazione degli elementi trasformati durante la conversione dei tuoi documenti Word in diversi formati. Aspose.Words offre un'enorme flessibilità e potenza per lavorare con gli elementi trasformati, consentendoti di creare documenti convertiti esattamente in base alle tue esigenze specifiche.