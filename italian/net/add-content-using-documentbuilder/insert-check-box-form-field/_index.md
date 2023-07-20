---
title: Inserisci il campo del modulo della casella di controllo nel documento di Word
linktitle: Inserisci il campo del modulo della casella di controllo nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
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

### FAQ

#### D: Posso inserire più campi modulo casella di controllo in un singolo documento?

R: Assolutamente! È possibile inserire tutti i campi del modulo della casella di controllo necessari in un documento di Word utilizzando Aspose.Words per .NET. Ripeti semplicemente il processo di inserimento per aggiungere più caselle di controllo interattive.

#### D: Posso impostare lo stato iniziale (selezionato o deselezionato) del campo del modulo della casella di controllo?

R: Sì, hai il pieno controllo sullo stato iniziale del campo del modulo della casella di controllo. Impostando il parametro di stato controllato su true o false, è possibile definire se la casella di controllo è inizialmente selezionata o deselezionata.

#### D: I campi dei moduli delle caselle di controllo sono compatibili con altri formati di file, come PDF?

A: Sì, i campi del modulo casella di controllo inseriti utilizzando Aspose.Words per .NET sono compatibili con vari formati di file, tra cui DOCX e PDF. Ciò ti consente di esportare i tuoi documenti in diversi formati mantenendo le caselle di controllo interattive.

#### D: Posso regolare le dimensioni del campo del modulo della casella di controllo?

R: Certamente! È possibile specificare la dimensione del campo del modulo della casella di controllo utilizzando il parametro size nel metodo InsertCheckBox. Ciò consente di controllare le dimensioni della casella di controllo in base alle proprie preferenze di progettazione.

#### D: Aspose.Words per .NET è adatto sia per applicazioni desktop che web?

R: Sì, Aspose.Words per .NET è una libreria versatile adatta sia per applicazioni desktop che web. Che tu stia creando un'applicazione Windows o un sistema basato sul Web, puoi integrare la libreria senza problemi.