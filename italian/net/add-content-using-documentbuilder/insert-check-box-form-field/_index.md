---
title: Inserisci campo modulo casella di controllo
linktitle: Inserisci campo modulo casella di controllo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire campi modulo casella di controllo nei documenti di Word utilizzando Aspose.Words per .NET. Guida passo dopo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-check-box-form-field/
---

In questo tutorial completo, imparerai come inserire un campo modulo casella di controllo in un documento Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di aggiungere campi modulo con caselle di controllo con proprietà personalizzabili ai tuoi documenti.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserire un campo modulo casella di controllo
Utilizzare quindi il metodo InsertCheckBox della classe DocumentBuilder per inserire un campo modulo casella di controllo. Fornire il nome, lo stato controllato, lo stato predefinito e i parametri di dimensione come argomenti:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## Passaggio 3: salvare il documento
Dopo aver inserito il campo form check box, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### Esempio di codice sorgente per Inserisci campo modulo casella di controllo utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di un campo modulo casella di controllo utilizzando Aspose.Words per .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertCheckBox("CheckBox", true, true, 0);

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
	
```

Ricorda di adattare il codice in base alle tue esigenze specifiche e di migliorarlo con funzionalità aggiuntive secondo necessità.

## Conclusione
Congratulazioni! Hai imparato con successo come inserire un campo modulo casella di controllo in un documento Word utilizzando Aspose.Words per .NET. Seguendo la guida passo-passo e utilizzando il codice sorgente fornito, ora puoi migliorare i tuoi documenti con campi modulo con caselle di controllo interattive.
