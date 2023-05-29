---
title: Inserisci riga orizzontale
linktitle: Inserisci riga orizzontale
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire regole orizzontali nei documenti di Word utilizzando Aspose.Words per .NET. Guida passo dopo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-horizontal-rule/
---

In questo esempio completo, imparerai come inserire una regola orizzontale in un documento di Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di aggiungere regole orizzontali ai tuoi documenti per la separazione visiva e l'organizzazione.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserire una regola orizzontale
Successivamente, utilizza il metodo Writeln della classe DocumentBuilder per aggiungere un testo descrittivo e quindi inserire una riga orizzontale:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Passaggio 3: salvare il documento
Dopo aver inserito il filetto orizzontale, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Esempio di codice sorgente per inserire una regola orizzontale utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di una regola orizzontale utilizzando Aspose.Words per .NET:
Le regole orizzontali sono utili per vari scenari, come la divisione di sezioni, la creazione di interruzioni visive o l'evidenziazione di informazioni importanti.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Ricorda di adattare il codice in base alle tue esigenze specifiche e di migliorarlo con funzionalità aggiuntive secondo necessità.

## Conclusione
Congratulazioni! Hai imparato con successo come inserire una regola orizzontale in un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi separare visivamente e organizzare i tuoi documenti utilizzando regole orizzontali.

