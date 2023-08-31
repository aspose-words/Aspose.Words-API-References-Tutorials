---
title: Clonare il modulo Vba da un documento Word
linktitle: Clonare il modulo Vba da un documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: In questo tutorial, scopri come clonare un modulo VBA da un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-vba-macros/clone-vba-module/
---

In questo tutorial ti spiegheremo come clonare un modulo VBA da un documento Word con macro utilizzando la libreria Aspose.Words per .NET. La clonazione di un modulo VBA consente di riutilizzare o copiare il codice VBA da un documento sorgente a un altro documento. Ti guideremo passo dopo passo per aiutarti a comprendere e implementare il codice nel tuo progetto .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Una conoscenza pratica del linguaggio di programmazione C#
- La libreria Aspose.Words per .NET installata nel tuo progetto
- Un documento Word contenente un progetto VBA con il modulo che desideri clonare

## Passaggio 1: definire la directory dei documenti
 Innanzitutto, devi impostare il percorso della directory sulla posizione del tuo documento Word. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso appropriato.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento di origine
Successivamente, caricheremo il documento Word sorgente, che contiene il progetto VBA e il modulo che vogliamo clonare.

```csharp
// Carica il documento di origine
Document doc = new Document(dataDir + "VBA project.docm");
```

## Passaggio 3: crea un nuovo documento con il progetto VBA e clona il modulo
Creeremo un nuovo documento con un progetto VBA vuoto e cloneremo il modulo specificato dal documento sorgente.

```csharp
// Crea un nuovo documento con un progetto VBA vuoto
Document destDoc = new Document { VbaProject = new VbaProject() };

// Clonare il modulo
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## Passaggio 4: salva il documento di destinazione
Infine, salveremo il documento di destinazione con il modulo VBA clonato in un file.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Codice sorgente di esempio per il modulo Clone Vba utilizzando Aspose.Words per .NET 
```csharp

//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Conclusione
In questo tutorial abbiamo visto come clonare un modulo VBA da un documento Word con macro utilizzando Aspose.Words per .NET. La clonazione dei moduli VBA consente di riutilizzare facilmente il codice VBA da un documento sorgente in un altro documento. Sentiti libero di utilizzare questa funzione per organizzare e gestire le tue macro in diversi documenti.

### Domande frequenti

#### D: Cos'è la duplicazione di un modulo VBA?

R: La duplicazione di un modulo VBA consiste nel copiare un modulo contenente codice VBA da un documento Word di origine a un altro documento. Ciò consente di riutilizzare il codice VBA in contesti diversi o condividerlo con altri documenti.

#### D: Quali sono i prerequisiti per clonare un modulo VBA da un documento Word?

R: Prima di poter clonare un modulo VBA da un documento Word, devi avere una conoscenza pratica del linguaggio di programmazione C#. È inoltre necessario installare la libreria Aspose.Words per .NET nel progetto. Inoltre, hai bisogno di un documento Word contenente un progetto VBA con il modulo che desideri clonare.

#### D: Come impostare la directory dei documenti nel codice?

 A: Nel codice fornito, è necessario sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso appropriato della directory in cui si trova il documento Word contenente il progetto VBA.

#### D: Come salvare il documento di destinazione con il modulo VBA clonato?

 R: Per salvare il documento di destinazione con il modulo VBA clonato, puoi utilizzare il file`Save` metodo del`Document` classe specificando il percorso di destinazione e il nome file desiderati.