---
title: Clona modulo Vba
linktitle: Clona modulo Vba
second_title: Riferimento all'API Aspose.Words per .NET
description: In questo tutorial, scopri come clonare un modulo VBA da un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-vba-macros/clone-vba-module/
---

In questo tutorial, ti spiegheremo come clonare un modulo VBA da un documento Word con macro utilizzando la libreria Aspose.Words per .NET. La clonazione di un modulo VBA consente di riutilizzare o copiare il codice VBA da un documento di origine a un altro documento. Ti guideremo passo dopo passo per aiutarti a comprendere e implementare il codice nel tuo progetto .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Conoscenza operativa del linguaggio di programmazione C#
- La libreria Aspose.Words per .NET installata nel tuo progetto
- Un documento Word contenente un progetto VBA con il modulo da clonare

## Passaggio 1: definire la directory dei documenti
 Innanzitutto, devi impostare il percorso della directory nella posizione del documento di Word. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso appropriato.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: carica il documento di origine
Successivamente, caricheremo il documento Word sorgente, che contiene il progetto VBA e il modulo che vogliamo clonare.

```csharp
// Carica il documento di origine
Document doc = new Document(dataDir + "VBA project.docm");
```

## Passaggio 3: creare un nuovo documento con il progetto VBA e clonare il modulo
Creeremo un nuovo documento con un progetto VBA vuoto e cloneremo il modulo specificato dal documento di origine.

```csharp
// Crea un nuovo documento con un progetto VBA vuoto
Document destDoc = new Document { VbaProject = new VbaProject() };

// Clonare il modulo
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## Passaggio 4: salvare il documento di destinazione
Infine, salveremo il documento di destinazione con il modulo VBA clonato in un file.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Esempio di codice sorgente per Clone Vba Module utilizzando Aspose.Words per .NET 
```csharp

// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Conclusione
In questo tutorial abbiamo visto come clonare un modulo VBA da un documento Word con macro utilizzando Aspose.Words per .NET. La clonazione dei moduli VBA consente di riutilizzare facilmente il codice VBA da un documento sorgente in un altro documento. Sentiti libero di utilizzare questa funzione per organizzare e gestire le tue macro in diversi documenti.
