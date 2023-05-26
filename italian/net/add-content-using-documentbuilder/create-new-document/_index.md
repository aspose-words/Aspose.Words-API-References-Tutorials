---
title: Crea nuovo documento
linktitle: Crea nuovo documento
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare un nuovo documento Word e aggiungere contenuto utilizzando Aspose.Words per .NET. Guida passo dopo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/create-new-document/
---

In questo tutorial passo-passo imparerai come creare un nuovo documento Word da zero usando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di generare un nuovo documento e aggiungervi contenuto utilizzando la classe DocumentBuilder.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: crea un nuovo documento
Per iniziare, crea un nuovo documento utilizzando la classe Document:

```csharp
Document doc = new Document();
```

## Passaggio 2: aggiungere contenuto al documento
Successivamente, utilizza un oggetto DocumentBuilder per aggiungere contenuto al documento. Inizializza DocumentBuilder con il documento appena creato:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");
```

## Passaggio 3: salvare il documento
Dopo aver aggiunto il contenuto desiderato, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Esempio di codice sorgente per la creazione di un nuovo documento utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per la creazione di un nuovo documento utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document();

// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Conclusione

Congratulazioni! Hai imparato con successo come creare un nuovo documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata e utilizzando il codice sorgente fornito, ora puoi generare nuovi documenti a livello di programmazione e aggiungervi contenuto utilizzando la classe DocumentBuilder.

Ora puoi creare e personalizzare con sicurezza documenti Word in base alle tue esigenze specifiche.

### Codice sorgente di esempio per la creazione di un nuovo documento utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document();

// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

Ricorda di modificare il percorso e il nome del file nel codice per salvare il documento nella posizione desiderata sul tuo sistema.

